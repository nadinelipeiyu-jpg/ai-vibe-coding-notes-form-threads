# 🤖 Claude Code & Vibe Coding 實戰 Tips

![Last Updated](https://img.shields.io/badge/最後更新-2026--04--13-blue)
![Tips Count](https://img.shields.io/badge/Tips-50條-green)
![Source](https://img.shields.io/badge/來源-Threads社群-orange)

從 Threads 社群收集整理的 Claude Code、Vibe Coding、AI workflow 實用技巧。
每條都有來源帳號連結，學會並實際使用後打勾 ✅

> **持續更新中** — 歡迎開 Issue 推薦好文或補充內容

## 目錄

- [一、Skill 設計原則](#一skill-設計原則7-條)（7 條）
- [二、Token & Session 省用技巧](#二token--session-省用技巧6-條)（6 條）
- [三、CLAUDE.md 設定技巧](#三claudemd-設定技巧2-條)（2 條）
- [四、Vibe Coding & UI 設計技巧](#四vibe-coding--ui-設計技巧6-條)（6 條）
- [五、Claude Code 工具整合](#五claude-code-工具整合7-條)（7 條）
- [六、知識管理 & Obsidian 整合](#六知識管理--obsidian-整合7-條)（7 條）
- [七、實戰 Workflow 案例](#七實戰-workflow-案例10-條)（10 條）
- [八、學習資源 & 工具參考](#八學習資源--工具參考5-條)（5 條）

---

## 一、Skill 設計原則（7 條）

- [ ] **Skill 是資料夾，不是 md 文件**
  Skill 可以放腳本、模板、甚至資料庫，Claude 會自己去翻。
  *就像給員工一整個工具箱，不只是一張便條紙。*
  - 只寫 Claude 會搞錯的地方（邊界案例、踩坑點）
  - 不要寫 Claude 已經知道的基本概念
  - 每個 Skill 必須有「踩坑點章節」，根據 Claude 實際犯的錯持續更新
  📌 [@oso_cy](https://www.threads.com/@oso_cy/post/DWALc2XDlxL)

- [ ] **/grill-me 指令：Plan 後不要急著說 Yes**
  讓 Claude 靈魂拷問你的計畫，再跑出更好的版本。
  *就像考試前先讓同學出題考你，找出你沒想到的漏洞。*
  - Plan 跑完第一版後，在 No 那列輸入 `/grill-me`
  - Claude 會問你十幾題：邊界情況、錯誤處理、有沒有更好的做法
  - 拷問完後重出一版計劃書，品質差很多，再 Yes 開始寫
  📌 [@mancity.tw](https://www.threads.com/@mancity.tw/post/DWzPuazki0V)

- [ ] **gstack：YC CEO 開源的虛擬工程團隊 Skill 包**
  13 個 slash command，把 Claude Code 變成完整工程團隊。
  *就像一個人請了整個工程部門來幫你，從規劃到上線都有人負責。*
  - 作者：Y Combinator CEO Garry Tan，48 小時破萬星
  - 涵蓋產品規劃 → QA → 發佈的完整流程
  - 內建 Playwright，AI 可以真的開瀏覽器、點按鈕、截圖找 bug
  - 最常用：`plan-ceo-review`
  📌 [@ci.fullstack](https://www.threads.com/@ci.fullstack/post/DWO5dkQlG2p)

- [ ] **沒裝 Skill 的 Claude 就像剛到職的資深員工**
  聰明，但什麼都不懂你的工作流。
  *就像請了一個很厲害的人，但他完全不知道你們公司的規矩。*
  - Skill 是讓 Claude 了解你的公司/專案脈絡的關鍵
  - 很多人還沒搞懂這個功能
  📌 [@mariasourcing](https://www.threads.com/@mariasourcing/post/DW5MVKkjnTE)

- [ ] **設計 Skill 推薦：Impeccable 和 UI Skill**
  兩款社群評價高的前端設計 Skill。
  *就像裝了兩個很會畫圖的助手，專門幫你讓網站變好看。*
  - **Impeccable**（9400+ stars）：7 個專業領域參考檔、20 個命令 → [impeccable.style](https://impeccable.style)
  - **UI Skill**（986 stars）：15 個 skill，含 SwiftUI，可按需引用 → [ui-skills.com](https://www.ui-skills.com)
  📌 [@mukiwu](https://www.threads.com/@mukiwu/post/DV-GPlAFHOk)

- [ ] **技能包大師：繁體中文版 skill-creator**
  整合 Claude 官方架構＋CodeX 優點＋個人方法論。
  *就像有人幫你把製作說明書的方法也整理成一份說明書。*
  - 支援三種場景：對話式新建 / 現有內容轉 Skill / 先寫規格再動手
  - 可在 Claude Code、Codex、Cowork、OpneCode、反重力等平台跑
  - GitHub 搜尋「技能包大師」
  📌 [@jiang_yude_coach](https://www.threads.com/@jiang_yude_coach/post/DXA5sxuApgx)

- [ ] **用 Skill 每天自動抓新聞＋資訊流**
  自製 Skill 讓 Claude 每天抓 400+ RSS＋X 資訊流。
  *就像請了一個助理每天早上幫你整理今天的報紙重點，你只要看摘要就好。*
  - 成為公司 Agent，每天開工先讓 AI 看新聞，再開始工作
  📌 [@automoney_gda](https://www.threads.com/@automoney_gda/post/DXBStg1lWrZ)

---

## 二、Token & Session 省用技巧（6 條）

- [ ] **Gemini CLI 查資料省 Claude Token**
  查資料交給 Gemini，Claude 只負責分析，每天免費 1000 次。
  *就像叫圖書館員幫你找書，找好再交給老師幫你解讀，不用老師也去找書。*
  - 安裝：`npm install -g @google/gemini-cli`，跑 `gemini --version` 確認
  - 限制 Gemini 只做三件事：找資料、列來源、摘錄原文（沒來源就不輸出）
  - **進階子代理模式**：用三個角度獨立搜尋（官方 / 正面 / 負面），降低確認偏誤
  - 資料找完後再交給 Claude 分析統整
  📌 [@jiang_yude_coach](https://www.threads.com/@jiang_yude_coach/post/DWvTmW2k48g) · [進階版](https://www.threads.com/@jiang_yude_coach/post/DWx4XtQijb6)

- [ ] **規劃和執行分開，執行用低階模型**
  規劃用強模型，執行換便宜模型，省錢又聚焦。
  *就像先請聰明的顧問想清楚怎麼做，再請普通員工按步驟執行。*
  - 規劃結束時丟這句話：「幫我整理一份執行重點，包含：最終決策、重要脈絡、前提條件、要避的坑」
  - 拿到重點後重開新視窗執行，不帶多餘的規劃對話
  📌 [@jiang_yude_coach](https://www.threads.com/@jiang_yude_coach/post/DW2xAF_CWYi)

- [ ] **CronCreate 避免 Cache 過期重算 Token**
  打開舊對話說「繼續」，cache 過期會讓 session 直接噴掉 10%。
  *就像每隔一段時間戳一下電腦讓它知道你還在，不然它會把你的記憶都清掉。*
  - 解法：用內建 `CronCreate` 定期喚醒
  - Pro 方案：每 3–4 分鐘一次；Max 方案：每 30–40 分鐘一次
  📌 [@lawchat.tw](https://www.threads.com/@lawchat.tw/post/DW4cSU6k9wo)

- [ ] **Session 排程：延長有效使用額度**
  Claude Code 額度是開始對話後算 5 小時，善用排程讓額度不浪費。
  *就像把鬧鐘設好，讓每次使用的時間不會撞在一起，用得更有效率。*
  - 到 `claude.ai/code/scheduled/` 設 Schedule
  - 內容：`only say hello to me`，模型選 Haiku 4.5，Schedule 選 Custom
  - Cron expression：`5 23,4,9,14 * * *`（UTC）
  - 效果：晚上 8 點開始用，10 點重置，一晚上可有 2 個 session 用量
  📌 [@lulumifish](https://www.threads.com/@lulumifish/post/DW6jUfPEX2G)

- [ ] **code-review-graph：知識圖譜幫 AI 省 8 倍 Token**
  只把真正相依的檔案餵給 AI，不讓它讀一堆無關檔案。
  *就像讓 AI 只看跟這次作業有關的課本章節，而不是整本書。*
  - 用 Tree-sitter 把專案架構解析成知識圖譜
  - 改了某支程式碼，自動算出「爆炸半徑」，只餵相依檔案給 AI
  - 官方實測平均省 8 倍 Token，內建 MCP 支援
  - GitHub：`tirth8205/code-review-graph`
  📌 [@ci.fullstack](https://www.threads.com/@ci.fullstack/post/DW_0UcLlFJr)

- [ ] **三層知識架構讓 AI 跨 Session 持續進化**
  讓 AI 記得上次學到了什麼，不再每次從零開始。
  *就像讓 AI 有自己的日記本，每次上課後自動記好筆記，下次繼續。*
  - **Session Continuity**：用 hook 在 context 壓縮前自動存檔，壓縮後自動恢復
  - **Knowledge Curation**：session 結束後自動歸檔到 Obsidian；同類錯誤出現 3 次就升級為正式規則
  - **Vault Governance**：定期健康檢查，找出孤立筆記和過時內容
  - 工具：只需 Obsidian + Claude Code CLI
  📌 [@ai.lanrenbao](https://www.threads.com/@ai.lanrenbao/post/DXB_0ByDKhe)

---

## 三、CLAUDE.md 設定技巧（2 條）

- [ ] **CLAUDE.md 是給 AI 的「工作守則」**
  放在專案根目錄，Claude Code 每次啟動自動讀取。
  *就像給新來的員工一本公司手冊，讓他每天來上班前先看一遍規矩。*
  - 可以放：禁止事項 / 必做規則 / 專案結構說明 / 語言偏好
  - 快速生成：在專案目錄執行 `/init`，或說「分析這個專案，幫我建立一個 CLAUDE.md」
  - 持續更新：每次 Claude 犯規，說「把這條規則加進 CLAUDE.md」
  - 常用規則：「記得用繁體中文」「不要自動 commit」「先讀檔案再編輯」
  📌 [@jiang_yude_coach](https://www.threads.com/@jiang_yude_coach/post/DW7v_-GAc1T)

- [ ] **Boris Cherny（Claude Code 創作者）的實際工作流**
  不是官方文件的「建議做法」，是他每天真的在用的。
  *就像直接問世界冠軍他平常怎麼練習，比看教科書更真實。*
  - **Git Worktree 多線並行**：同時跑 3–5 個 agent，各自處理不同任務
  - **CLAUDE.md 投資術**：每次被 Claude 搞到就更新規則，當作長期投資
  - **Plan mode 先行**：先花力氣寫計畫，讓 Claude 一次到位
  - **/loop 自動循環**：每 5 分鐘跑一次 SDD 完整開發流程
  📌 [@ci.fullstack](https://www.threads.com/@ci.fullstack/post/DWrJeolFPd3)

---

## 四、Vibe Coding & UI 設計技巧（6 條）

- [ ] **Cinematic UI：用電影導演思維設計網站**
  解決設計 Skill 做多了風格趨同、千站一面的問題。
  *就像不再從模板挑樣式，而是請 AI 當導演，每個網站都拍一部不同的電影。*
  - 強迫 AI 用電影思維思考網站的故事、配色、燈光、鏡頭
  - 每個站都讓 AI 自己設計，有質感、不重複
  - 開源，最適合 Claude Code
  - GitHub：`akseolabs-seo/cinematic-ui`
  📌 [@darkseoking](https://www.threads.com/@darkseoking/post/DWsuYU-kzXT)

- [ ] **DESIGN.md：把大廠設計系統變成 AI 可執行的指令**
  30+ 頂級品牌設計 DNA 轉成 Markdown，丟進專案就能用。
  *就像把 Apple、Spotify 設計師的眼光裝進 AI，讓它自動照那個標準做。*
  - 涵蓋：Apple 極致留白 / Spotify 深色霓虹 / Linear 精準極簡 / SpaceX 未來感
  - 用法：把 DESIGN.md 丟進專案根目錄，告訴 AI「參考這個設計文件來構建頁面」
  - 純 Markdown，LLM 直接食用，不需要 Figma 插件或 JSON
  📌 [@asia_ai.io](https://www.threads.com/@asia_ai.io/post/DWyrU6jiPtZ) · [@brainness.ai](https://www.threads.com/@brainness.ai/post/DWxt_vMAUZb)

- [ ] **Vibe Coding 心得：AI 常超譯，要主動收斂**
  全程只靠 prompt 做網站，AI 會加太多你沒要的東西。
  *就像叫人幫你佈置房間，他幫你加了一堆裝飾，你還是要自己決定留哪些。*
  - 搭配 Skills 時，AI 容易超譯需求、多做不必要的事
  - 最後還是要把 AI 產生的東西大幅刪掉，改回自己收斂
  - 關鍵認知：方向和審美還是要自己掌握，AI 做執行
  📌 [@designtips.today](https://www.threads.com/@designtips.today/post/DWBql-eCEhD)

- [ ] **Stitch 先做 UI，再交給 Claude Code 工程化**
  設計和開發分工，不要直接讓 Claude Code 猜審美。
  *就像先請設計師畫好草圖，再請工程師照圖施工，而不是叫工程師邊想邊蓋。*
  - Step 1：用 Stitch 用自然語言設計原型，定好色彩、字體等品牌 kit
  - Step 2：把設計稿交給 Claude Code 處理前後台部署（串 MCP）
  📌 [@denniswei1310](https://www.threads.com/@denniswei1310/post/DXDcTFOmZ-b)

- [ ] **Raccoodar 浣熊雷達：vibe coding 完記得做資安檢測**
  常見漏洞：API key 寫死在前端、Firebase 設定出包、敏感檔案外露。
  *就像蓋好房子後要請人來驗收，看有沒有門沒鎖好或窗戶沒關緊。*
  - 被動式掃描，不影響網站運作
  - 輸入網址等幾秒就有結果
  📌 [@raccoodar](https://www.threads.com/@raccoodar/post/DXB-zOxmB_x)

- [ ] **AI 程式碼正確率只有 75%，一定要做 code review**
  每 4 次有 1 次是錯的，67% 的開發者不會仔細 review。
  *就像 AI 幫你做作業，你還是要自己檢查一遍，不能直接交出去。*
  - 研究：滑鐵盧大學測 11 個大型 LLM，GPT-4o / Claude / Gemini 正確率約 75%
  - AI 適合用在：原型設計、brainstorming、快速驗證想法
  - 核心邏輯、安全相關、生產環境：review 嚴謹度不能因為「AI 寫的」就降低
  📌 [@fu_liren.ai](https://www.threads.com/@fu_liren.ai/post/DW_lWbdk0Tw)

---

## 五、Claude Code 工具整合（7 條）

- [ ] **Chrome DevTools MCP：讓 Claude 直接操作瀏覽器**
  Chrome 146 版本新功能，AI 有了「眼睛」。
  *就像讓 AI 坐在你的電腦前，它可以自己看網站、自己點按鈕。*
  - 開啟方式：Chrome 升級到 146，網址列輸入 `chrome://inspect/remote-debugging`，開啟遠端偵錯
  - 可用來：自動發文、抓後台數據、找隱藏 API
  📌 [@jerry_wang_1109](https://www.threads.com/@jerry_wang_1109/post/DV8tyCtiaIm)

- [ ] **`claude --chrome`：內建 Chrome，不需裝 Playwright MCP**
  Claude Code 已把瀏覽器功能內建，一個參數搞定。
  *就像手機本來就有相機，不需要再買一台相機插上去。*
  - 啟動方式：`claude --chrome`
  - 可用來：看網站、debug、/schedule 行程、查詢每日資訊
  📌 [@oliver_chi_chen](https://www.threads.com/@oliver_chi_chen/post/DW9aeNpifJU)

- [ ] **Firecrawl：解決 Claude Code 爬蟲被 403 擋的問題**
  Claude 爬不了大部分知名網站，裝 Firecrawl 一行解決。
  *就像幫 AI 裝了一個可以走任何門的通行證。*
  - 安裝：一行指令，之後用自然語言跟 Claude 講
  - 四大場景：JS 動態渲染網站 / 一鍵競品分析 / 客戶情報研究 / SEO 全站審計
  📌 [@hei_ai.automation](https://www.threads.com/@hei_ai.automation/post/DWxzgT-EzvC)

- [ ] **gws CLI + Claude Code：管理 Gmail / Calendar / Drive**
  Google Workspace 全部變成 terminal 指令，Claude 直接解析 JSON。
  *就像把 Google 所有服務都接上了遙控器，AI 可以幫你一鍵操作。*
  - 可同時開 3 個 Agent 並行處理
  - 實際案例：一個下午清掉 13 年 89,275 封信中的 43,760 封
  📌 [@ci.fullstack](https://www.threads.com/@ci.fullstack/post/DWwT_PjlN5f)

- [ ] **Claude Code v2.1.80 Channels：透過 Telegram / Discord 傳訊**
  不用開終端機，直接用通訊軟體跟 Claude 溝通。
  *就像以前要去公司才能跟同事說話，現在用 LINE 傳訊就好。*
  - Telegram：單個附件最大 50MB
  - Discord：最多 10 個附件各 25MB；可拉取最近 100 條歷史訊息
  - 提供完整權限控制：配對模式 / 白名單 / 群組多人協作
  📌 [@yuaanlin](https://www.threads.com/@yuaanlin/post/DWwdVHaDdpo)

- [ ] **Claude Code 透過 MCP 控制 LINE 個人帳號**
  可讀取群組訊息、傳訊，非官方方案。
  *就像讓 AI 幫你管 LINE，它可以幫你看訊息、整理重點、建議怎麼回。*
  - 避雷：名字要精確；LINE 桌面版頁籤放「全部」；名字不精確可能傳錯人
  - 應用：私群訊息排程總結 → AI 建議回覆 → 人工審核
  📌 [@good_job_ai](https://www.threads.com/@good_job_ai/post/DW9W2Vbk_pC)

- [ ] **notebooklm-mcp：Claude Code 直連 NotebookLM**
  讓 Claude 把 NotebookLM 的內容抓進知識庫做比對統整。
  *就像讓 AI 可以直接去翻你的筆記本，不用你每次都複製貼上給它看。*
  - Prompt：「幫我透過 notebooklm-mcp 連 NotebookLM，第一次用 `nlm login` 授權，之後用 `nlm` 管 source」
  - 延伸工具：Chrome 外掛「YouTube to NotebookLM」，快速把 YouTube 影片匯入分析
  - 非官方授權
  📌 [@jiang_yude_coach](https://www.threads.com/@jiang_yude_coach/post/DW-buUhgolD)

---

## 六、知識管理 & Obsidian 整合（7 條）

- [ ] **Obsidian + Claude Code + GitHub：PARA 資料夾架構**
  Karpathy 的知識管理法：人丟素材，AI 做加工分類。
  *就像你負責收集材料，AI 負責幫你整理歸檔，你們分工合作。*
  - 用索引頁取代 RAG，一個索引就能理解整個主題
  - 卡片越多，AI 能引用的素材越豐富
  - 建議結構：`00_Inbox / 01_Projects / 02_Areas / 03_Resources / 04_Archive / 05_Attachments`
  📌 [@gatelynch](https://www.threads.com/@gatelynch/post/DWp2RK3FLZr)

- [ ] **Obsidian + Claude Code 整理筆記：配自動化更高效**
  可以把拖了很久沒時間整理的筆記一次搞定。
  *就像讓 AI 幫你整理亂到不行的房間，一次把所有東西放到對的地方。*
  - 注意：筆記超過 4500 則後，Claude Code 效率會下降，需要做好索引
  📌 [@nelsonkuo](https://www.threads.com/@nelsonkuo/post/DWN530ElZTQ)

- [ ] **MIRROR 框架：每週讓 Claude 客觀分析你的工作日誌**
  AI 不帶情緒，會點出你自己會合理化跳過的盲點。
  *就像請一個不怕傷你感情的朋友幫你照鏡子，說出你不願意面對的真相。*
  - 把一週的行動、任務、決策記錄餵給 Claude 分析
  - 範例回饋：「整理系統的工作，正在以『生產力的外表』佔據核心業務的時間」
  - 搭配 Obsidian + Claude Code 使用效果最佳
  - 參考：[tomsguide MIRROR 文章](https://www.tomsguide.com/ai/i-use-the-mirror-system-with-claude-to-run-my-weekly-review-heres-how-it-works)
  📌 [@dustin_gmat](https://www.threads.com/@dustin_gmat/post/DV_NbjeDw5w)

- [ ] **Graphify：把 Codebase 變成可自然語言查詢的知識圖譜**
  解決「專案裡什麼都有，但要找東西完全不知從哪開始」的痛點。
  *就像把一個亂七八糟的倉庫畫成地圖，你問「電池在哪」它就直接帶你去。*
  - 吃進 code、PDF、圖片、影片，自動建立關係
  - 可以用自然語言問問題
  - 6 天 19.7k GitHub stars
  📌 [@ci.fullstack](https://www.threads.com/@ci.fullstack/post/DW9Vh2_kyTk)

- [ ] **LINE + Make + Claude Code：自動將文章 PDF 入庫成結構化筆記**
  手機端用 LINE 丟素材，自動跑進 Obsidian 變結構化筆記。
  *就像你只要把東西丟進去，後面的整理、歸檔、分類都有人自動幫你做好。*
  - LINE 丟文章/PDF → Make 自動化處理 → Claude Code ingestion → 結構化筆記
  - 系統會自動提示你哪個領域的知識缺口需要補充
  - GitHub：`Timeverse/My-Brain-System`
  📌 [@idk_mostoftime](https://www.threads.com/@idk_mostoftime/post/DWrNR9oFCZl)

- [ ] **OpenClaw + Obsidian Skill：讓 AI Agent 讀寫你的筆記庫**
  本地跑、不上雲、隱私保留，直接讀 .md 和 YAML frontmatter。
  *就像讓 AI 坐在你的書房裡，它可以自己去翻你的筆記本，但資料不會跑出去。*
  - 安裝：`npx clawhub@latest install obsidian`
  📌 [@likuanhui](https://www.threads.com/@likuanhui/post/DW-ezOyCV1O)

- [ ] **Claude + Obsidian 已知問題：跨文件同步**
  更新一個文件，相關文件不會自動跟著改。
  *就像你改了行事曆上的一件事，但備忘錄和待辦清單裡的同一件事沒有跟著改。*
  - 場景：說「星期一的任務改了」，進度文件更新了，但時間表沒動
  - 寫規則和用 Hook 都無法完全解決「應該同時改什麼」的判斷問題
  - 目前最有效做法：每次明確告訴 Claude 要同時更新哪些相關文件
  📌 [@justicemily](https://www.threads.com/@justicemily/post/DXDtvwHEYVB)

---

## 七、實戰 Workflow 案例（10 條）

- [ ] **Claude + Notion Skill：10 秒完成開課邀約全流程**
  貼信件說「幫我建專案」，AI 自動建資料、查行事曆、回信。
  *就像你只要把信件遞給助理，後面的事情他全部幫你搞定。*
  - 自動：建聯絡人 / 查行事曆衝堂 / 擬回信並寄出
  - 關鍵：把工作規則寫成 Skill，記憶不可靠，規則才可靠
  - GitHub：`ViviChen-nocode/ai-project-assistant`
  📌 [@thevividai.vi](https://www.threads.com/@thevividai.vi/post/DWt1pVjkq08)

- [ ] **IG 輪播圖文全自動發布 Workflow**
  從生成到發布，全程不需手動操作。
  *就像有一條生產線，你說想要什麼，最後成品自動出現在 Instagram 上。*
  - Claude Code 生成文案 → Playwright HTML 截圖（1080×1350px）→ 圖床（catbox.moe）→ Meta Graph API 發布 → Telegram 通知
  📌 [@wowscly](https://www.threads.com/@wowscly/post/DWltK8zmMUN)

- [ ] **Claude Code 10 分鐘做 IG Carousel**
  中文描述需求，自動生成可截圖的 HTML，不滿意繼續用中文改。
  *就像你跟設計師說「我要深色科技風六頁」，十分鐘後成品出來了。*
  - 傳統做法 40 分鐘 → Claude Code 10 分鐘
  📌 [@vjvan_n](https://www.threads.com/@vjvan_n/post/DWxXqYzkz9_)

- [ ] **Claude Code + Telegram 語文家教機器人**
  每天練 50 次口說，費用不到台幣 3 元。
  *就像有一個不限時、不收費、隨時陪你練習的語言家教。*
  - 教材 → AI 拆解重點/生成語音 → Telegram 錄音 → AI 批改/評分/回傳 mp3 → 間隔複習追蹤弱點
  📌 [@leveragelife_qq](https://www.threads.com/@leveragelife_qq/post/DWJmwNmjKpS)

- [ ] **Threads 接 Google Sheets：自動追蹤貼文數據**
  發文後自動抓 1h / 24h / 3d / 7d 數據，達標自動發 CTA 留言。
  *就像把你的社群帳號接上自動報表機，什麼時候該行動它會自己通知你。*
  - 可同時彙整多個帳號數據
  - 踩坑：Meta OAuth 驗證很不友善
  📌 [@jojo880714](https://www.threads.com/@jojo880714/post/DW8xdhWgeKJ)

- [ ] **Claude + Apps Script：薪資條全自動化**
  彙整明細 → 帶入模板 → 產出 PDF → 比對 email 自動寄出，一鍵完成。
  *就像把每個月最麻煩的事情設成自動模式，你只要按一個按鈕。*
  📌 [@apex_huang](https://www.threads.com/@apex_huang/post/DWrRVVVGWru)

- [ ] **Claude B2B 客戶自動開發：2 天建站＋1 週 10 個 lead**
  2 天用 Claude 做完 B2B 網站，AI Agent 自動找 email 發開發信。
  *就像以前要五個人才做得到的業務工作，現在一個人加 AI 就搞定了。*
  - 流程：自動找目標客戶 email → 整理名單 → Mailmeteor 24 小時發信
  - 成本：30 美元/月
  📌 [@jenkintse](https://www.threads.com/@jenkintse/post/DW93GAZmFIM)

- [ ] **AI 剪片：錄影丟進去 10 分鐘成片**
  用客製化 Claude Code 技能，以前 1 小時的剪接現在 10 分鐘。
  *就像錄完影之後，有人幫你自動剪好，你只要確認成品就好。*
  - 素材也可以全部用 AI 生成
  📌 [@mocoo.lee](https://www.threads.com/@mocoo.lee/post/DW4XUyJk_e-)

- [ ] **AI 自動回 LINE 機器人（4 步驟）**
  整個設定過程約 1–2 小時，門檻比想像的低。
  *就像訓練一個機器人學你說話的方式，之後讓它代替你回訊息。*
  - 整理過去對話紀錄 → AI 分析回覆習慣輸出模板 → 串接官方 API → 測試微調語氣
  - 注意：Facebook Messenger 規則不同，串接更複雜
  📌 [@andrew54068](https://www.threads.com/@andrew54068/post/DW4FYPLGled)

- [ ] **GitHub Actions + Python + Telegram Bot：每日資訊自動推送**
  三樣免費工具，設定一次，每天早上自動推送報告到手機。
  *就像設定好鬧鐘，它每天早上自動幫你整理好今天要知道的事情。*
  - GitHub Actions（排程）+ Python 腳本（抓數據）+ Telegram Bot（推送）
  📌 [@wowscly](https://www.threads.com/@wowscly/post/DW7eB1WgQl3)

---

## 八、學習資源 & 工具參考（5 條）

- [ ] **Claude Code 30 步學習路徑（新手到高手）**
  10 小時從害怕 coding 到上手的完整路徑。
  *就像有人幫你把「從零開始學習」這件事變成一張清楚的地圖。*
  - 安裝 Brew + Node.js + Claude Code → 巢狀資料夾 → 基本指令（model / resume / clear / compact）→ /init 開 CLAUDE.md → Plan mode → Skill + Subagent + MCP → 從 Vercel 下載 Skill → 實作 subagent → Orchestrate 完整流程
  📌 [@peter_career_hack](https://www.threads.com/@peter_career_hack/post/DV8BWv_kTlo)

- [ ] **Claude Code 繁體中文速查表（自動同步官方更新）**
  官方有更新就自動同步，適合加書籤隨時查。
  *就像有人幫你把說明書翻成中文，而且會自動更新不用你管。*
  - GitHub：[Raymondhou0917/claude-code-cheatsheet-zh](https://github.com/Raymondhou0917/claude-code-cheatsheet-zh)
  - 延伸建議：①終端機換 Tmux ②新增即時 token 用量和 reset 時間顯示 ③裝 brainstorming skills
  📌 [@raymond0917](https://www.threads.com/@raymond0917/post/DWvJ_D5iJ5_) · [@kat.is.playing](https://www.threads.com/@kat.is.playing/post/DW8NXg4iS28)

- [ ] **PAPAYA 27 分鐘 Claude Code 教學（目前台灣最清楚版本）**
  把初學者會卡在哪的問題提前解掉，比付費課程還清楚。
  *就像有個老師把你還沒開口問的問題，全部提前幫你回答了。*
  - 建議：不要「存起來以後看」，存起來就是不會看，現在看完今天就能上手
  📌 [@ai.truistic_](https://www.threads.com/@ai.truistic_/post/DWQ0hc3k0eg)

- [ ] **設計師用 Claude Code 完整指南**
  模型怎麼選、方案怎麼挑、功能怎麼用、跟其他 AI 工具怎麼比。
  *就像有人幫設計師寫了一份「我試過了，你不用踩坑」的使用心得。*
  - 文章：[A Designer's Guide to Organizing AI Skills and Tools in Claude Code](https://medium.com/design-bootcamp/a-designers-guide-to-organizing-ai-skills-and-tools-in-claude-code-f87477c35b82)
  📌 [@kkyeh_](https://www.threads.com/@kkyeh_/post/DWi9RFtGL3n)

- [ ] **Claude 訂閱方案選擇：Pro 不夠跑 Code，要 Max 才能發揮**
  只用 Chat 功能，Claude Pro 和 Gemini 沒太大差距。
  *就像買了一台跑車卻只在停車場開，要上高速公路才能感受到差別。*
  - 需要 Max 的場景：跑 Claude Code + Claude Cowork 需要足夠 Token 額度
  - 小技巧：用公司 Email 訂閱 Claude，搭配 Chrome Extension 減少工具切換摩擦
  📌 [@garlia.t](https://www.threads.com/@garlia.t/post/DW92tBzEwdE)

---

*整理日期：2026-04-13 · 共 50 條 · 來源：Threads 社群*
