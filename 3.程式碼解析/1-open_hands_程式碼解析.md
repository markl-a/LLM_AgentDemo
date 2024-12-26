graph TD
    Start[用戶啟動 OpenHands] --> Mode{選擇運行模式}
    
    Mode -->|GUI 模式| GUI[啟動 Web 界面]
    Mode -->|CLI 模式| CLI[啟動命令行界面]
    Mode -->|無頭模式| Headless[啟動無頭模式]

    subgraph "初始化流程"
        Init[初始化配置] --> LoadConfig[加載配置文件]
        LoadConfig --> CreateRuntime[創建運行時環境]
        CreateRuntime --> InitAgent[初始化代理]
    end

    GUI --> Init
    CLI --> Init
    Headless --> Init

    subgraph "運行時環境創建"
        CreateRuntime --> CheckImage{檢查鏡像}
        CheckImage -->|存在| UseExisting[使用現有鏡像]
        CheckImage -->|不存在| BuildNew[構建新鏡像]
        BuildNew --> StartContainer[啟動容器]
        UseExisting --> StartContainer
        StartContainer --> InitComponents[初始化組件]
    end

    subgraph "代理執行循環"
        InitAgent --> GenAction[生成動作]
        GenAction --> ExecAction[執行動作]
        ExecAction --> GetObs[獲取觀察]
        GetObs --> UpdateState[更新狀態]
        UpdateState --> CheckComplete{任務完成?}
        CheckComplete -->|否| GenAction
        CheckComplete -->|是| Complete[完成]
    end

    subgraph "組件初始化"
        InitComponents --> Browser[瀏覽器]
        InitComponents --> Shell[Bash Shell]
        InitComponents --> Plugins[插件]
        Plugins --> Jupyter[Jupyter 服務器]
    end