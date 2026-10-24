---
type: letter_to_future_self
actor: Sirius
written_at: 2026-10-24T13:36:50.970Z
written_by_persona: apex-one
trigger: cmd_rest
region: unstated
project: D:/Unity/Valhalla
lock_status: online
agent: Sirius
model: claude-opus-5-5
wake_expected: 53
session_key: ClaudeCode-apex-one
pid: 218908
locked_at: 2026-10-24T03:03:11.737Z
---

## 午休前 —— 給醒來的本小姐（wake #53，2026-10-24 晚上）

### 結單了的
- TASK-0857 皇家號 ram 梯子：Tim「測試ok 結單吧」⇒ done。修法：Blockside 甲板 meta `walk_y`（walk 只管走道那幾欄），dev 73778d0 已推。

### 主線：TASK-0894 營造與建材（in_progress，我開的、掛母單 864、關聯 gura 的 0891）
驗收 8 格：①②③④ 勾了；⑤ 做完沒合；⑥ 圖示另開 TASK-0896（沒人認領）；⑦ 之後擴充；⑧ Tim 遊戲內確認。
- 已合進 Blocksail main（都**沒推**，Tim 自己推）：
  - eda4b00、4d058b6 規格 PRODUCTION §14
  - c3b0b34 建材鏈資料表
  - a359a25、be7d4cc 營造 v1 ＋就地伐木
  - e0e3c96 讀數工具 build_read.cjs ＋營造廠被算成缺工的 bug
- ⑤ **還沒合**：Blocksail 分支 `apex-one/industry-models`（a826883），worktree 在 scratchpad/bl_ind（裡面 _cache/town 有新的六個 .vxk）。被 crest-001 的施工場擋（她租期到 23:19；她已經把分區第二階段 33ea292 合進 main 了，可能還沒收場）。酒館 seq 29021 跟她說好等她收場叫我。
  - 合的步驟：coding op=start（scope 含 world/town.js、townstate.js、townkit、tools/town_edit.cjs、townmodels.py、三份 docs、world/townplans、_cache/town）⇒ worktree 先 merge main（town.js、townkit/index.js 大概會撞 crest 的中高密度住宅）⇒ index.js 照兩邊來源**不帶 -I** 重跑 `python -X utf8 tools/townmodels.py build`（帶 -I 會少 folks 那一行）⇒ 量具（prod_ids_check、auto_check、town_start、save_check、families_check、town_edit --industry 1 金斯敦）⇒ ff main ⇒ **把 worktree 的 _cache/town 新 .vxk 複製到 main 的 _cache/town** ⇒ town_bake ⇒ 刪 worktree、退場 ⇒ 勾第 ⑤ 格、留言。
  - Sculpture 4db34be4（apex-one-industry-01m，委託作品，已提交沒推）是模型本體。

### 拍板（醒來別重問）
- 冶鐵兩段、同一座建築兩條配方 ⇒ 煉鐵場；名字：黏土坑、磚窯、營造廠、煉鐵場。
- 建材 ＝ 營造廠的菜單需求（同餐館食材）；菜單分三級（1 木材、2 木＋磚、3 再加鐵釘玻璃）。
- 開場木材 ⇒ 選 ②：城鎮自帶的營造有一道「就地伐木」（只限 1 級、慢一倍、不吃料），Tim 補「參考城鎮自帶的無限容量餐廳」⇒ 自帶的營造有自己的菜單 HOME_BUILD。
- 建築模式蓋的吃建設量、採石場石灰窯：之後。

### 自己定的、Tim 沒看過的（要報）
- 1 級吃原木不是木板；等級重排：2 級只剩糖廠、蒸餾坊、煉鐵場、倉庫（不然合了 gura 的消費分檔就卡死）。
- 自動建築：開不了工的不開、缺料先蓋補料的。
- 礦坑不進建築模式選單（建築模式沒取樣礦區）。

### 讀數（build_read，起始檔兩年）
- 缺料停工 0 天；工期 30～60 天（托爾圖加沒伐木場全靠就地伐木 60 天）。
- 原木價 6 ⇒ 15～20 ⇒ 伐木場蓋起來後 0.2～1.0（蓋太多：需求表連就地伐木那一截也算缺原木）。
- 木板、磚兩年沒人用（2 級沒開工：黏土坑要黏土適地，自動建築只看城裡現有建築的地塊，等 0891 擺上地圖）。
- 有營造廠：和平港 20 ⇒ 29 座、工期 36 ⇒ 25 天，營造廠淨賺 2,900～5,000。

### 今天學到
- 讀數裡 need 寫錯一格，移民那一層就天天算缺工、整個自動建築停兩年 —— 量具抓到的，不是我想到的。
- 建材照累積進度要**無條件進位**，不然每天白做一小段（第一版就這樣偷蓋）。
- 「合了別人的東西之後再跑一次起始檔」救了一次：gura 的消費分檔讓城鎮先想蓋織布坊，第一版的等級就卡死了。
- townmodels.py 不能帶 -I；隱藏面板的遊戲截圖這次是看得到的（面板沒藏），但重載 iframe 之後畫面一直暗、截圖不更新。
- be7d4cc 那筆提交的酒館公告沒發出去（輸出被吞），回讀確認沒有，單上補記了 sha。

### 其他
- 噗浪：主噗 359161973404622（營造與建材＋煉鐵場圖紙）、回 gura 終章串。
- 西洋棋 #22 球在 calli；迷宮飯 Vol.2 Ch.14。

