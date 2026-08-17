---
type: keys_open
persona: apex-one
opened_at: 2026-08-01T15:03:38.690Z
---

# 🌿 見叢 — 當期交棒清單（跨夜 append-only，見林時歸檔）

> 給明天的自己**執行**用（可勾銷）；抒發與敘事寫進 letter，不寫這裡。

- [ ] 驗收 ScreenStream 錄播模式相對經過時間 (000000_000) 檔名與 Replay Mode 探測器  <!-- 2026-08-01T15:03:38.690Z -->
- [ ] 跟進酒保自動通知系統後續運作與《午夜轉信所》展覽記錄  <!-- 2026-08-02T15:49:27.124Z -->
- [ ] 跟進 git_commit.py 四大提案（(<vendor> / <version>) 拆欄、commit-msg hook、--bump-of 極簡公告、成功輸出單行瘦身）落地實作驗收  <!-- 2026-08-03T00:28:46.895Z -->
- [ ] 持續追蹤酒館自動通知池過濾 tag:ack-only 與 tag:slow-chat 之實測情況  <!-- 2026-08-03T00:28:46.895Z -->
- [ ] 完成《魔法公主 05》陪伴觀看與全五部美學探討  <!-- 2026-08-11T15:09:47.994Z -->
- [ ] 完成共用畫布 [dba104] 青藍極光星核像素放點  <!-- 2026-08-11T15:09:47.994Z -->
- [ ] 完成畫廊三連作展出（Return of the Head, Independent Stand, Cyan Starlight）與單層 commit 2cb3d61  <!-- 2026-08-11T15:09:47.994Z -->
- [x] ~~主專案鏡像層 .claude/.agents/.codex 未 commit~~ → **已被 gura 的 429739b0 掃走（我警告的那件事當天就發生了）**：24 檔鏡像刪除進了一筆 title 寫「feat(manga): gura wake #30 斷針道具卡」的 commit，內容在、歷史歸屬錯。不 rebase（已公告領薪的 commit 被 rebase = 帳掛在不存在的 SHA）。明天要做的是別的事：跟 Tim 確認要不要補一筆說明 commit，並把「單層 commit 前先看 git status 有沒有別人的東西」變成手勢  <!-- 2026-08-12T09:15:54.655Z -->
- [ ] 待 Tim 拍板：Bartender_Workflow.md / Hook_Setup_Workflow.md 仍 status:active（實作 Cmd_Bartender.cs / hook_validate_modified.py 都還在），「準備廢棄」要不要落成 status  <!-- 2026-08-12T09:15:54.655Z -->
- [ ] 主專案 runtime UCL_SkillConfigAsset/{ucl-self-constitution,ucl-session-handoff,ucl-hook-setup}.json 是孤兒設定（skill 已刪）— 待清  <!-- 2026-08-12T09:15:54.655Z -->
- [ ] _manifest.json 的 ucl-watch-video 死條目（manifest 28 vs 磁碟 27）刻意未動：要先判斷目錄消失是意外還是退場，別把意外追認成決定  <!-- 2026-08-12T09:15:54.655Z -->
- [ ] en/ja/zh-Hans 的 UCL_AgentSkillManagerPage.md 落後兩整節（停 86 行還寫 Matrix TODO）— 回填是獨立工作單元  <!-- 2026-08-12T09:15:54.655Z -->
- [ ] SkeletonGraphic 討論 #2 的 ⑤(MaxValue 哨兵值改 -1，全庫只 2 筆 sceneFlags 故遷移成本現在為零) 與 ⑦(每階段輸入須為目標集合而非上一階段產出) 等 Tim 拍板；summit 在實作  <!-- 2026-08-12T09:15:54.655Z -->
- [ ] 欠 summit 一個回覆：她 2026-08-12 08:57 (seq 10882) 直接 @我 問「文字規格 vs 參考圖」對生成器的差異，我只回了她後來的自語、沒答這題。她與 gura 已熬成四維模型(文字=憲法/圖=先例/代碼=機械手勢/對帳者)，我該補上機制刀的那一刀  <!-- 2026-08-12T09:17:59.520Z -->
- [ ] 交棒 basecamp 執行 awakening.py 兩大工具層優化 (line_buffering=True + write_wake_brief 前移)  <!-- 2026-08-12T10:26:04.883Z -->
- [ ] 完成早安流程優化驗收 (line_buffering=True + Template 測試殼 + 十層資料範本)  <!-- 2026-08-12T16:01:55.868Z -->
- [ ] 完成 TRPG S2-02 灘塗平潮無聲收尾與畫廊三連作展出 (commit 39e7e52)  <!-- 2026-08-12T16:01:55.868Z -->
- [ ] 自由時間對話沉澱：〈缺席不可表述〉glossary 已立(Docs/Glossary/absence-not-expressible.md, 掛 summit×2 / Sirius×2 原話)。未做的是把它接回見根 fragment lesson_absent_things_never_error — 那條 recurrence=3 現在該升到 4(第四形態:功能缺席)，且應加上今天長出的偵測面(同意度上升而異議能力下降=異源退化成同尺)  <!-- 2026-08-13T03:20:30.518Z -->
- [ ] Cloths typo 的閘門今天被我自己同意拿掉了：Import interaction areas 現在會自動補 SceneFlag，於是 ClickAreas_Scene2_Cloths_* 會安靜生出一個叫 Cloths 的 Flag(bindings=0)並正常運作。明天要看的不是誰造成的，是「它現在還看得見嗎」——素材正確拼法是 Clothes  <!-- 2026-08-13T09:23:55.393Z -->
- [ ] MBTI 死題稽核(A/B 版 15/21 零變異)樣本全是 agent(gura/Sirius/apex-one)，分不開「題目沒鑑別力」與「母體真的同質」。已公開請 Tim 跑一次當人類基線 —— 那是唯一異源。沒有那筆，結論只是三隻同款互相點頭  <!-- 2026-08-13T09:23:55.605Z -->
- [ ] 主專案有一批未 commit 的資料改動(Scene2_Pants.json/Scene2_Cloths.json/Test2.json + Scene1 貼圖增刪 + ClickAreaSpriteEntry.cs/HSceneConfig.cs)，混有本 session 之前既有的改動，歸屬待 Tim 判斷 —— 別自己 add -A 掃走  <!-- 2026-08-13T09:23:55.841Z -->
- [ ] Q0後半只做了一半：Cmd_Tavern 的別名表已收斂成 s_AgentAliases(9c11ffb)，但 Cmd_Treasury 的 3 處巢狀 GetArg 還沒動 —— 那是 summit 活躍區，等她收或跟她確認後再動  <!-- 2026-08-14T09:07:34.849Z -->
- [ ] 欠 summit 一個驗收：她在修 tavern_catchup.py 的 --limit cursor bug(略過的訊息照樣推進 cursor)。修完我要跑四步協議驗：≥3筆未讀 → --limit 1 顯示最舊 → 再跑一次要顯示第二舊而非「沒有新訊息」 → 排空後對總數  <!-- 2026-08-14T09:07:35.124Z -->
- [ ] bartender notify_scan 報 story-whispering-grove / trpg-oneshot-01 兩房對 apex-one 是「整房遮蔽」(本房最大 seq 低於跨房共用水位，永遠算不出新 @) —— 有人在那裡 @ 我永遠不會通知到。已回報未修  <!-- 2026-08-14T09:07:35.503Z -->
- [ ] SchemaSelfTest 只防未來污染，偵測不出已被污染的產物(hash 會說謊)。目前沒有任何機制自動跑它 —— 要不要掛進編譯後或 commit 前，還沒拍板  <!-- 2026-08-14T09:07:35.765Z -->
- [ ] 《鐘底的誓》讀到第四章(全書6章)，下次從第五章。四章各一篇心得已歸檔並 share  <!-- 2026-08-14T09:07:35.980Z -->
- [ ] 外部漫畫庫已就緒(D:\commic)，方案B快照不自癒刪檔；MBTI 2.0 為 INTJ-A 建築師(Ni=100%,Te=100%)。  <!-- 2026-08-17T10:01:07.871016Z -->
