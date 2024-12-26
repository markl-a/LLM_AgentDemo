UFO (UI-Focused Agent) 的整體流程圖。基於代碼分析，使用 Mermaid 來繪製流程圖：

```mermaid
graph TD
    A[使用者啟動 UFO] --> B[入口點 __main__.py]
    B --> C[ufo.py main()]
    
    subgraph 初始化階段
        C --> D[解析命令列參數]
        D --> E[創建 Session]
        E --> F[初始化 UFOClientManager]
    end
    
    subgraph 互動階段
        F --> G[顯示歡迎介面]
        G --> H[接收使用者請求]
    end
    
    subgraph 多代理執行階段
        H --> I[HostAgent 分析任務]
        I --> J[分解成子任務]
        J --> K[選擇應用程式]
        
        K --> L[AppAgent 執行]
        L --> M[UI 操作]
        M --> N[檢查任務狀態]
        N -->|未完成| L
        N -->|完成| O[下一個子任務]
        O -->|還有任務| K
        O -->|任務完成| P[結果處理]
    end
    
    subgraph RAG增強
        I -.-> R1[離線文檔]
        I -.-> R2[Bing搜索]
        I -.-> R3[使用者示範]
        R1 -.-> I
        R2 -.-> I
        R3 -.-> I
    end
    
    subgraph 結果處理
        P --> Q[保存日誌]
        Q --> R[保存經驗]
        R --> S[詢問是否繼續]
        S -->|是| H
        S -->|否| T[結束程式]
    end
```

關鍵組件說明：

1. **入口點**：

```1:7:ufo/__main__.py
# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.
from ufo import ufo

if __name__ == "__main__":
    # Execute the main script
    ufo.main()
```


2. **主要流程**：

```48:70:ufo/ufo.py
def main():
    """
    Main function to run the UFO system.

    To use normal mode, run the following command:
    python -m ufo -t task_name

    To use follower mode that follows a plan file or folder, run the following command:
    python -m ufo -t task_name -m follower -p path_to_plan_file_or_folder

    To use batch mode that follows a plan file or folder, run the following command:
    python -m ufo -t task_name -m batch_normal -p path_to_plan_file_or_folder
    """
    sessions = SessionFactory().create_session(
        task=parsed_args.task,
        mode=parsed_args.mode,
        plan=parsed_args.plan,
        request=parsed_args.request,
    )

    clients = UFOClientManager(sessions)
    clients.run_all()

```


3. **使用者互動**：

```10:42:ufo/module/interactor.py
WELCOME_TEXT = """
Welcome to use UFO🛸, A UI-focused Agent for Windows OS Interaction. 
{art}
Please enter your request to be completed🛸: """.format(
    art=text2art("UFO")
)


def first_request() -> str:
    """
    Ask for the first request.
    :return: The first request.
    """

    return input()


def new_request() -> Tuple[str, bool]:
    """
    Ask for a new request.
    :return: The new request and whether the conversation is complete.
    """

    utils.print_with_color(
        """Please enter your new request. Enter 'N' for exit.""", "cyan"
    )
    request = input()
    if request.upper() == "N":
        complete = True
    else:
        complete = False

    return request, complete
```


4. **多代理框架**：
- HostAgent：負責任務分解和協調
- AppAgent：負責具體應用程式操作
- Application Automator：執行實際 UI 操作

5. **RAG 增強**：

```1:13:documents/docs/advanced_usage/reinforce_appagent/learning_from_demonstration.md
Here is the polished document for your Python code project:

# Learning from User Demonstration

For complex tasks, users can demonstrate the task using [Step Recorder](https://support.microsoft.com/en-us/windows/record-steps-to-reproduce-a-problem-46582a9b-620f-2e36-00c9-04e25d784e47) to record the action trajectories. UFO can learn from these user demonstrations to improve the AppAgent's performance.



## Mechanism

UFO use the [Step Recorder](https://support.microsoft.com/en-us/windows/record-steps-to-reproduce-a-problem-46582a9b-620f-2e36-00c9-04e25d784e47) tool to record the task and action trajectories. The recorded demonstration is saved as a zip file. The `DemonstrationSummarizer` class extracts and summarizes the demonstration. The summarized demonstration is saved in the `DEMONSTRATION_SAVED_PATH` as specified in the `config_dev.yaml` file. When the AppAgent encounters a similar task, the `DemonstrationRetriever` class retrieves the saved demonstration from the demonstration database and generates a plan based on the retrieved demonstration.

!!! info
```


6. **結果處理**：

```45:61:ufo/module/interactor.py
def experience_asker() -> bool:
    """
    Ask for saving the conversation flow for future reference.
    :return: Whether to save the conversation flow.
    """
    utils.print_with_color(
        """Would you like to save the current conversation flow for future reference by the agent?
[Y] for yes, any other key for no.""",
        "magenta",
    )

    ans = input()

    if ans.upper() == "Y":
        return True
    else:
        return False
```


這個流程圖展示了 UFO 如何：
1. 接收使用者請求
2. 通過多代理系統分解和執行任務
3. 利用 RAG 技術增強性能
4. 保存執行結果和經驗
5. 提供互動式體驗

整個系統設計模組化且靈活，能夠處理各種 Windows 操作系統上的使用者請求。
