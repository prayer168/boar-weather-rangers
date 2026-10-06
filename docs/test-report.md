# Boar Weather Rangers v0.3.8 瀏覽器測試報告

- 日期：2026-10-06（Asia/Taipei）
- 測試網址：https://prayer168.github.io/boar-weather-rangers/
- 版本：v0.3.8，commit eaada97
- 測試方式：Chrome 151 可見瀏覽器，以 agent-browser CLI 執行互動；錄影不是 Playwright runner。
- 主要視窗：1600×900；另檢查 800×700 平板及 390×844 手機排版。

## 結果摘要

三個任務均可從簡報部署、選擇預測、發射連線、掃描資料、撤離結算並前往下一關。完整完成後返回基地會正確關閉結算層。繁中、英文、韓文切換正常；全螢幕可以開啟，按 Esc 會退出全螢幕並回到主畫面。測試期間沒有發現阻止遊玩的程式錯誤。

| 檢查項目 | 結果 | 證據 |
|---|---|---|
| 左右 HUD 字級與寬度 | 通過；桌機兩側各 400px，左側任務說明 28px、目標／狀態 20px，右側資料 17px、裝備標題 18px | [20-hud-fonts-v038.png](test-evidence/20-hud-fonts-v038.png) |
| 任務 1：天氣要素 | 通過；掃描讀得氣溫、雲量、風向、風速、降雨，撤離結算完成 | [21-mission1-scan-v038.png](test-evidence/21-mission1-scan-v038.png)、[22-mission1-result-v038.png](test-evidence/22-mission1-result-v038.png) |
| 任務 2：天氣預測 | 通過；選擇預測後掃描連續觀測值並完成結算 | [23-mission2-scan-v038.png](test-evidence/23-mission2-scan-v038.png) |
| 任務 3：長期訊號 | 通過；掃描五年摘要，完成全部任務；介面標示教育示意資料 | [24-mission3-scan-v038.png](test-evidence/24-mission3-scan-v038.png)、[25-all-missions-result-v038.png](test-evidence/25-all-missions-result-v038.png) |
| 返回主畫面 | 通過；最終結算層關閉，基地首頁可見 | [26-return-to-menu-v038.png](test-evidence/26-return-to-menu-v038.png) |
| 語言切換 | 通過；英文顯示 DEPLOY，韓文顯示 출동，任務首頁標籤維持 24px | 透過瀏覽器 DOM 讀值檢查 |
| 全螢幕與 Escape | 通過；全螢幕開啟，Escape 後退出並回主畫面 | [27-final-home-escape-v038.png](test-evidence/27-final-home-escape-v038.png) |
| 平板 800×700 | 通過；左右欄 255/265px，發射控制位於頁尾上方且可見 | [28-tablet-layout-v038.png](test-evidence/28-tablet-layout-v038.png) |
| 手機 390×844 | 通過；側欄文字 16px，場景可垂直捲動，操作按鈕仍在版面內 | [29-mobile-layout-v038.png](test-evidence/29-mobile-layout-v038.png) |

## 錄影

完整桌機操作錄影長約 68 秒、1600×900： [boar-weather-full-playthrough-v038.webm](test-evidence/boar-weather-full-playthrough-v038.webm)。影片涵蓋開場、三關掃描及結算、語言切換、全螢幕與 Escape 返回主畫面。測試畫面可依上表截圖查看。

## 備註

- 舊檔 [boar-weather-test-v033.webm](test-evidence/boar-weather-test-v033.webm) 是早期中斷錄影，不作為正式測試證據。
- 此次依使用者要求完成瀏覽器互動測試；使用 agent-browser 控制 Chrome，沒有宣稱使用 Playwright test runner。
- 天氣／長期摘要是遊戲內教學資料。課本適用年級及官方課程細節仍待教師核對。
