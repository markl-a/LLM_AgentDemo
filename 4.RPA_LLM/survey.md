# 專門用於 RPA 的開源 LLM 專案

## 簡介

近年來，大型語言模型（LLM）在自然語言處理領域取得了顯著的進展，並開始被應用於各個領域，包括機器人流程自動化（RPA）。LLM 可以幫助 RPA 系統更好地理解人類語言、處理非結構化數據，並自動生成工作流程，從而提高 RPA 的效率和靈活性。

LLM 的整合也標誌著 RPA 發展的重大轉變，從傳統的基於規則的 RPA 轉變為更智能、更具適應性的代理流程自動化（APA）。APA 利用 LLM 的能力，使機器人能夠理解自然語言指令、從非結構化數據中提取資訊，並根據情況變化調整工作流程。

本文將介紹一些專門用於 RPA 的開源 LLM 專案，並探討 LLM 如何賦能 RPA。

## LLM 如何賦能 RPA？

傳統的 RPA 系統通常依賴於預先定義的規則和工作流程，難以處理複雜或非結構化的數據。而 LLM 的出現為 RPA 帶來了新的可能性：

- **智能數據提取**: LLM 可以從非結構化數據（如文檔、郵件、網頁）中提取關鍵信息，並將其轉換為結構化數據，供 RPA 系統使用。例如，LLM 可以用於從發票中提取關鍵數據，例如發票號碼、日期和總金額。

- **自然語言理解**: LLM 可以理解人類語言，並將其轉換為 RPA 系統可以理解的指令，從而實現更自然的交互方式。例如，LLM 可以用於理解客戶服務查詢，並生成相應的回覆。

- **自動工作流程生成**: LLM 可以根據人類的指令自動生成 RPA 工作流程，從而減少人工編程的工作量。

- **動態決策**: LLM 可以根據實時情況做出決策，並調整 RPA 工作流程，從而提高 RPA 系統的靈活性。

- **持續學習和適應**: LLM 可以不斷學習新的數據和知識，並根據新的情況調整 RPA 工作流程，從而提高 RPA 系統的效率和準確性。

## RPA 和 LLM 社群和論壇

如果您對 LLM 在 RPA 中的應用感興趣，可以參考以下社群和論壇：

- **Reddit 的 r/rpa**: 這是 Reddit 上一個專門討論 RPA 的子版塊，其中也包含關於 LLM 和 RPA 結合的討論。
- **UiPath 社區論壇**: UiPath 作為領先的 RPA 平台，其社區論壇也提供了關於 LLM 和 RPA 結合的討論和資源。
- **Stack Overflow**: Stack Overflow 是一個程式設計師常用的問答網站，其中也包含關於 RPA 和 LLM 的問題和解答。

## 專門用於 RPA 的開源 LLM 專案

| 專案名稱 | 簡介 | 是否使用 LLM | 主要功能 |
|---------|------|-------------|----------|
| AmitXShukla/RPA | 使用 Python 和 Julia 語言腳本自動化日常任務，並利用 LLM（例如 ChatGPT）構建交易機器人等應用。 | 是 | - 文件分割與合併<br>- 網頁截圖<br>- 從圖像中讀取文本<br>- 生成和讀取 QR 碼<br>- 建立虛擬測試數據<br>- 建立推薦引擎<br>- 預測到達時間 |
| tebelorg/RPA-Python | 一個用於 RPA 的 Python 套件，可自動化網站、桌面應用程序或命令行上的重複性任務。 | 未知 | - 網頁自動化<br>- 視覺自動化<br>- OCR 自動化<br>- 鍵盤自動化<br>- 鼠標自動化 |
| Skyvern-AI/skyvern | 使用 LLM 和計算機視覺自動化基於瀏覽器的任務，例如網頁導航、數據提取、密碼填充等。 | 是 | - 網頁導航<br>- 數據提取<br>- 循環操作<br>- 文件解析<br>- 發送電子郵件 |

## 總結

LLM 的出現為 RPA 帶來了新的發展機遇，可以提高 RPA 系統的效率、靈活性，和智能化程度。相信隨著 LLM 技術的發展和應用，LLM 與 RPA 的結合將會更加緊密，並為各個行業帶來更大的價值。

我們可以更加的探索開源項目和了解更多關於 LLM 在 RPA 中的應用。同時，也需要關注 LLM 在自動化中應用的相關議題，包括：

- **倫理考量**：例如演算法偏差、隱私保護、資料安全等
- **社會影響**：包括就業市場變遷、工作轉型需求等
- **技術挑戰**：如模型解釋性、可靠性和穩定性等
- **實施策略**：需要制定完善的治理框架和最佳實踐指南

建議組織在導入 LLM 強化 RPA 時，應採取循序漸進的方式，並建立完整的評估和監控機制，以確保技術應用既能發揮效益，又能妥善管理相關風險。

## 引用的著作

1. OpenBMB/ProAgent: An LLM-based Agent for the New ... - GitHub, 檢索日期：2月 13, 2025， https://github.com/OpenBMB/ProAgent
2. From Robotic Process Automation to Agentic Process Automation - UiPath Community Forum, 檢索日期：2月 13, 2025， https://forum.uipath.com/t/from-robotic-process-automation-to-agentic-process-automation/779088
3. RPA vs AI agents vs Agentic Process Automation. Whats the future? : r/AI_Agents - Reddit, 檢索日期：2月 13, 2025， https://www.reddit.com/r/AI_Agents/comments/1iftryd/rpa_vs_ai_agents_vs_agentic_process_automation/
4. UiPath® DocPath - Document Understanding, 檢索日期：2月 13, 2025， https://docs.uipath.com/document-understanding/automation-cloud/latest/user-guide/uipath-docpath
5. LLM Powered Robotic Process Automation: Unleashing the Industry Transformation Revolution | Tangentia, 檢索日期：2月 13, 2025， https://www.tangentia.com/llm-powered-robotic-process-automation-unleashing-the-industry-transformation-revolution/
6. Workflow Generation - Enhans, 檢索日期：2月 13, 2025， https://www.enhans.ai/newsroom/workflow-generation
7. Large Language Model (LLM) and RPA to Solve Complex Use Cases - Rannsolve, 檢索日期：2月 13, 2025， https://rannsolve.com/blog/large-language-model-llm-and-rpa-to-solve-complex-use-cases/
8. r/rpa - Reddit, 檢索日期：2月 13, 2025， https://www.reddit.com/r/rpa/
9. Retrieval-augmented generation – Stack Overflow's Industry Guide to AI, 檢索日期：2月 13, 2025， https://stackoverflow.co/teams/resources/ai-industry-guide/key-tools-technologies-terms/rag/
10. Latest Articles on RPA News and Automation Insights | UiPath Blog, 檢索日期：2月 13, 2025， https://www.uipath.com/blog
11. Paper page - FlowMind: Automatic Workflow Generation with LLMs - Hugging Face, 檢索日期：2月 13, 2025， https://huggingface.co/papers/2404.13050
12. AmitXShukla/RPA: AI Bots - Robotic Processing automation ... - GitHub, 檢索日期：2月 13, 2025， https://github.com/AmitXShukla/RPA
13. tebelorg/RPA-Python: Python package for doing RPA - GitHub, 檢索日期：2月 13, 2025， https://github.com/tebelorg/RPA-Python
14. Skyvern-AI/skyvern: Automate browser-based workflows ... - GitHub, 檢索日期：2月 13, 2025， https://github.com/Skyvern-AI/skyvern
15. OpenAdaptAI/OpenAdapt: Open Source Generative ... - GitHub, 檢索日期：2月 13, 2025， https://github.com/OpenAdaptAI/OpenAdapt
16. New Generative AI features in UiPath Document Understanding - cxai.au, 檢索日期：2月 13, 2025， https://cxai.au/new-generative-ai-features-in-uipath-document-understanding/
17. Communications Mining - CommPath LLM vs. Preview LLM - UiPath Documentation, 檢索日期：2月 13, 2025， https://docs.uipath.com/communications-mining/automation-cloud/latest/user-guide/comm-path-llm-vs-review-llm
18. LangGraph and UiPath: streamlining enterprise LLMs | Community blog, 檢索日期：2月 13, 2025， https://www.uipath.com/community-blog/tutorials/langgraph-meets-uipath-simplifying-enterprise-llm
19. AI Agent Studio - Automation Anywhere, 檢索日期：2月 13, 2025， https://www.automationanywhere.com/products/ai-agent-studio
20. Put generative AI to work - Automation Anywhere, 檢索日期：2月 13, 2025， https://www.automationanywhere.com/products/generative-ai-process-models
21. Communications Mining - Prompt-based learning with Transformers - UiPath Documentation, 檢索日期：2月 13, 2025， https://docs.uipath.com/communications-mining/automation-cloud/latest/developer-guide/prompt-based-learning-with-transformers
22. EleutherAI/gpt-neo: An implementation of model parallel GPT-2 and GPT-3-style models using the mesh-tensorflow library. - GitHub, 檢索日期：2月 13, 2025， https://github.com/EleutherAI/gpt-neo
23. Automate Tasks with GPT using RPA Webinar - YouTube, 檢索日期：2月 13, 2025， https://www.youtube.com/watch?v=W0Z3L4Foryo
24. Smartflow: AI-Driven RPA, 檢索日期：2月 13, 2025， https://smartflow-4c5a0a.webflow.io/
25. Paper Review: FlowMind: Automatic Workflow Generation with LLMs - Medium, 檢索日期：2月 13, 2025， https://medium.com/llms-research/paper-review-flowmind-automatic-workflow-generation-with-llms-2cbd5d5c380d
26. The Next Generation of Productivity: Generative Process Automation | by Nick Giometti | Geodesic Capital | Medium, 檢索日期：2月 13, 2025， https://medium.com/geodesic-capital/the-next-generation-of-productivity-generative-process-automation-cbce68870c10
27. How Has RPA Evolved Since AI, LLMs & Agents Went Mainstream? : r/sysadmin - Reddit, 檢索日期：2月 13, 2025， https://www.reddit.com/r/sysadmin/comments/1ilzav3/how_has_rpa_evolved_since_ai_llms_agents_went/
28. Can LLM Replace Stack Overflow? A Study on Robustness and Reliability of Large Language Model Code Generation | Proceedings of the AAAI Conference on Artificial Intelligence, 檢索日期：2月 13, 2025， https://ojs.aaai.org/index.php/AAAI/article/view/30185
29. Going Beyond RPA with LLMs - IKANGAI, 檢索日期：2月 13, 2025， https://www.ikangai.com/going-beyond-rpa-with-llms/
