# 一加專案經驗



## OnePlus一加桌面

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption><p><a href="https://play.google.com/store/apps/details?id=net.oneplus.launcher">https://play.google.com/store/apps/details?id=net.oneplus.launcher</a></p></figcaption></figure>



一加桌面基於原生桌面進行客製化修改，提供電信商的客製化功能，包括自動下載電信商應用程式、桌面排版和客製化小工具。

項目中我主要負責多任務模塊(Recents)，提供用戶流暢及良好的後台應用體驗。

1. Recent (多任務頁面)

多任務頁面（Recent）在點擊SystemUI中的多任務按鈕或上滑手勢時立即顯示，該頁面的應用程式圖片由Framework讀取，需要在進入頁面瞬間載入每個應用程式的縮圖。因此，與SystemUI和Framework的密切合作是必需的。桌面作為用戶使用的第一個應用程式，當遇到問題時，用戶通常會先反映到桌面，然後由我們分析問題並確定問題出現在哪個模塊。

在 Recent 模塊中，我們實現了深層清除應用的功能。該功能根據用戶在一定時間內移除應用程式兩次的操作，判斷用戶確實希望從後台刪除該應用程式，然後呼叫Framework API將應用程式從進程中完全清除。詳細資訊請參考Google的介紹：[https://developer.android.com/guide/components/activities/recents](https://developer.android.com/guide/components/activities/recents)

2. Facade：運營商

Facade模塊允許運營商直接讀取整個桌面佈局並直接更新佈局。我們通過串接資料庫並提供運營商API，讓運營商能夠開發相應的應用程式並獲得相應的限制權限。這樣，運營商的應用程式就能夠讀取和寫入整個Launcher的佈局，實現對客製化用戶桌面的控制。Facade模塊的設計基於Facade模式，同時也是物件導向（OOP）中封裝概念的重要實踐。

3. OOS11 OOS12 主題 Porting

OOS11和OOS12的主題Porting專案旨在實現系統視覺的升級。每年都會隨著Android原生系統的升級而進行相應的更新。我們專注於客製化OneplusOS的主題和色調，並精心調整桌面上的每個元件，以打造最適合用戶的元件設計。

4. Firebase Analytics 埋點分析

我們將Firebase Analytics的埋點分析功能集成到應用程式中。通過串接Analytics埋點分析，我們能夠分析應用程式中每個功能的使用率和使用完整度等指標，準確記錄用戶的偏好。這些數據將用於應用程式未來的改進和創新。

5. NFC 客製化桌布

我們與視覺設計師合作推出了一個定制化的小彩蛋，稱為NFC客製化桌布。當用戶購買限定款手機殼並使用NFC感應卡片時，將彈出設計師專屬打造的壁紙。這為用戶提供了一種獨特的使用體驗。





## Canvas AOD

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption><p><a href="https://play.google.com/store/apps/details?id=com.oneplus.canvasresources">https://play.google.com/store/apps/details?id=com.oneplus.canvasresources</a></p></figcaption></figure>

Canvas AOD是一個應用程式，將任何照片描繪為美麗的輪廓，提供使用者在息屏到解鎖和桌面等場景中獲得一致的視覺效果，並具備出色的動畫設計，讓用戶從解鎖到桌面都能感受到桌布和動態桌布帶來的絕佳體驗。\
這款應用程式使用三方SDK來實現桌布的人像、動物和物品描繪。我們團隊負責從0到1的開發、架構設計以及應用程式的持續更新。
