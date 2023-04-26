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

————————————————————————————————————

下午在看fragment時，嘗試了使用Google  AdMob Fragment來測試廣告，廣告依舊顯示不出來，log顯示應該是帳戶還沒approved，[官網常見問題](https://support.google.com/admob/answer/9905175#1\&zippy=%2C%E5%B8%B3%E6%88%B6%E5%B0%9A%E6%9C%AA%E7%8D%B2%E5%87%86)寫到，通常帳戶創建之後需要24小時以上才會審核完成，繼續等下去．．．

<figure><img src=".gitbook/assets/CleanShot 2023-04-25 at 15.08.30@2x.jpg" alt=""><figcaption></figcaption></figure>



————————————————————————————————————

04.26:\
查看到會crash原因是因為meta-data沒有寫完整，誤以為要把Application\_ID換成自己應用ＩＤ。

<figure><img src=".gitbook/assets/CleanShot 2023-04-27 at 01.07.46@2x.jpg" alt=""><figcaption></figcaption></figure>

目前已可以成功顯示測試廣告。



待續...
