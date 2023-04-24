---
description: 紀錄
---

# Firebase AdMob 開發紀錄

依照 Admob 流程導入 AdMob SDK ，並在AndroidManifest 新增meta-data相關資訊。

{% embed url="https://developers.google.com/admob/android/quick-start?hl=zh-TW" %}

{% embed url="https://developers.google.com/admob/android/test-ads?hl=zh-TW" %}

啟用測試廣告後app一直彈初始化失敗：

<figure><img src=".gitbook/assets/CleanShot 2023-04-25 at 01.54.00@2x.jpg" alt=""><figcaption></figcaption></figure>



猜測是因為app顯示還在準備中，可能還不能使用，後來AdMob控制台就跳要填寫付款資訊：

<figure><img src=".gitbook/assets/CleanShot 2023-04-25 at 01.49.38@2x.jpg" alt=""><figcaption></figcaption></figure>

應該是Google還在審查中，要驗證身份，但流程還在跑，驗證選項裡面還沒有需要填寫的表格，目前空空如也。

<figure><img src=".gitbook/assets/CleanShot 2023-04-25 at 01.55.44@2x.jpg" alt=""><figcaption></figcaption></figure>



待續...
