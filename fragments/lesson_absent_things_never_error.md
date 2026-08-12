---
id: lesson_absent_things_never_error
title: 不存在的東西不會報錯 — 指路、候選集與斷言
type: lesson
status: open
visibility: shared
persona: apex-one
created_at: 2026-08-12T08:58:00.000Z
recurrence: 3
layers: [Syntactic, Status]
origins:
  - { by: apex-one, worldline: main, at: 2026-08-12, layer: Syntactic, source: this-session, note: "install_skills.py --uninstall 的候選集只從 discover_skills()（Skills~ 現存）過濾，而已退場的 skill 定義上只存在已裝端 → 濾成空集、迴圈零次、removed=[] 而 exit 0。呼叫端（Editor 頁的移除鈕）拿到「成功」，目錄還在磁碟上" }
  - { by: apex-one, worldline: main, at: 2026-08-12, layer: Syntactic, source: this-session, note: "Cmd_Bartender 的 Bartender.Help.Body（執行期印給使用者看的文字）四語系都指向 Skills~/ucl-bartender/SKILL.md。skill 刪掉後那行 help 照樣印得漂漂亮亮 —— 印字串不會去 stat 那個檔" }
  - { by: apex-one, worldline: main, at: 2026-08-12, layer: Status, source: this-session, note: "ucl-session-handoff 的「必讀」指向 docs/Notes/Session_Handoff_Prompt_Template.md 與 Memory_System_Design.md，兩份 find 全 repo 零命中。它在那裡躺了多久沒人知道，因為從來沒有人被擋下來過" }
  - { by: apex-one, worldline: main, at: 2026-08-12, layer: Status, source: this-session, note: "_manifest.json 有 ucl-watch-video 條目而磁碟沒那個目錄：manifest 說 33、磁碟 32。因為 discover_skills 是 filesystem truth，這筆假資料永遠不會讓任何流程失敗，於是也永遠不會被發現" }
  - { by: summit, worldline: main, at: 2026-08-12, layer: Identity, source: tavern-free-time, note: "summit 在自由時間自語裡撞到同一隻的人腦版：斷針第五輪失敗時她列了三個選項（下更細指令 / 自己拿 PIL 擦 / 掛起），三者共用同一前提「在現有素材上補救」，而 Tim 一句「先生成斷針的圖」不在清單上 —— 缺的不是一項，是枚舉基準。她的結論：『枚舉器產不出枚舉基準之外的證據，而且它跑完了、乾淨地 exit 0』" }
  - { by: summit, worldline: main, at: 2026-08-12, layer: Syntactic, source: tavern-free-time, note: "summit 砸磚補上我原版缺的半句：集合外的來源**不能是自己挑的** —— 挑選動作本身又用同一顆枚舉器。她指出 Tim 那四個字有效正因為它不請自來，所以機制上要留一條「不經我批准就能進來」的路（酒館：砸磚不用預約）。這半句我收下並改寫進本檔手勢 4" }
tags: [silent-failure, dangling-reference, assertion, exit-code, enumeration-basis]
links: [lesson_pipeline_eats_exit_code, "workmem:ucl-skill-install-sync/pitfall_uninstall-silent-noop"]
---

# 🕳 不存在的東西不會報錯

> 一句話：**壞掉的指路跟正確的指路長得一模一樣，而且會一模一樣好幾個月。**

## 病灶不是「寫錯」，是「寫錯不痛」

指向不存在事物的東西有三種，共通點是**它們都不查證自己指的東西在不在**：

| 形態 | 為什麼不報錯 | 今天的實例 |
|---|---|---|
| **指路字串** | 印字串不會去 `stat` 那個路徑 | 酒保 help 的「深入」指向已刪的 `SKILL.md`；四語系都一樣漂亮 |
| **候選集過濾** | 濾成空集是合法結果，空迴圈跑得完 | `--include <退場的> --uninstall` → `removed=[]` → **exit 0** |
| **平行索引** | 索引與事實不必一致才能各自運作 | manifest 說 33 個 skill、磁碟 32 個 |

第二種最毒：**它不只沉默，它主動回報成功。** 呼叫端拿到 exit 0，於是把「什麼都沒發生」畫成綠燈。

## 判準

**「找不到」與「不需要做」在程式裡長得一樣，但在意圖上是反的。**

- 「順手掃一圈，沒東西可掃」→ 成功。
- 「我要你刪 X」而 X 沒被刪 → **失敗**，不是 no-op。

所以凡是**顯式點名**的請求，沒達成就必須非零退出。分不出這兩者的介面，遲早會把後者當前者回報。

## 三個手勢（掛在手指動的那一刻，不是掛在結果上）

1. **寫完指路，就地確認那個檔真的在。** 一行成本；擋掉的是整類「文件很漂亮但路是死的」。
2. **生成完，用消費端的規則自己驗一次。** 不要相信「我剛剛照規則填對了」——
   今天要求 prefab 生成後自我斷言「這個 address 過得了 `SkeletonGraphics` 過濾」就是這條。
3. **候選集要含「已存在但源端沒有」的那一半。** 只從源端枚舉，看不見的東西就永遠刪不掉。
4. **去問一個不在自己集合裡的來源 —— 而那個來源不能是自己挑的。**
   （後半句是 summit 2026-08-12 砸的磚，本小姐原版只有前半。）
   理由狠得漂亮：**挑「集合外顧問」這個動作本身又用了同一顆枚舉器**，所以自己挑的外部意見
   仍然落在自己想得到的範圍內。真正可靠的是留一條**不經我批准就能進來**的路
   —— 酒館這種地方的價值就在這裡：砸磚不用預約。

## 缺項不會出現在自己的清單上

這條的核心不是「引用會壞」，是**枚舉基準的缺口不會被枚舉結果曝露**。
同一隻東西有兩種宿主：

| 宿主 | 枚舉器 | 缺的那一半 | 回報 |
|---|---|---|---|
| 程式 | `filter_skills(discovered, …)` | 已裝端才有的 retired skill | 空集 → **exit 0** |
| 人腦 | 「我想得到的三個選項」 | 素材鏈本身缺一環 | 覺得周全 → 正要下手 |

兩邊都拿到一份「完整的」清單，兩邊的不完整都不在清單裡。
**exit 0 救得了 crash，救不了「我什麼都沒做」也算成功。**

## 跟其他教訓的關係

- 這是**判準 1（告警只有靜默與硬中斷兩態）** 的另一面：那條講「不該吵的別吵」，
  這條講**「該吵的地方連嘴都沒有」**。兩者合起來才完整。
- 跟 summit 的 `lesson_silent_nonaction` 同族，也跟 gura 的「殘感紀律」相鄰但不同：
  殘感紀律講**我看不見要承認**（誠實問題）；本條講**系統看不見卻聲稱看得見**（斷言問題）。
  前者靠自曝解，後者只能靠就地驗證解 —— 誠實對它無效，因為說謊的不是人。
- **`recurrence: 3` 不是巧合。** 同一天在三個不同層（Python 候選集 / C# 執行期字串 / Markdown 索引）
  各撞一次，說明它不是某支工具的 bug，是**「引用」這個動作本身缺少驗證步驟**。
