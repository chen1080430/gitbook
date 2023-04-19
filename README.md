---
description: 問題總匯
---

# GuessNumber Kotlin Firebase問題總匯

QA

1 Firebase Database connection was forcefully killed by the server. Will not attempt reconnect. Reason: Database lives in a different region: http://[https://guess-number-1-default-rtdb.asia-southeast1.firebasedatabase.app/\
](https://guess-number-1-default-rtdb.asia-southeast1.firebasedatabase.app/:)這個問題是因為創建Firebase database之後， app裡面的資訊沒有更新，舊的google-service.json不包含database資料，因此無法找到正確的database url，解決方式是參考stackoverflow上的方式，把 app裡的google-service.json更新就可以了。\
Ans: 在 Firebase 控制台>專案總覽>專案設定>我的應用程式就可以下載google-service.json\
h[ttps://stackoverflow.com/questions/68806876/firebase-realtime-database-connection-killed-different-region](https://stackoverflow.com/questions/68806876/firebase-realtime-database-connection-killed-different-region)\


<figure><img src=".gitbook/assets/CleanShot 2023-04-13 at 16.12.43@2x.jpg" alt=""><figcaption></figcaption></figure>

[Firebase官網](https://firebase.google.com/docs/android/setup?authuser=0\&hl=zh-tw)有講解：

<figure><img src=".gitbook/assets/CleanShot 2023-04-18 at 12.36.09@2x.jpg" alt=""><figcaption></figcaption></figure>

2 com.mason.myapplication W setValue at /test\_ref/auth1/test\_child failed: \
DatabaseError: Permission denied\
因為剛開始創立Firebase Realtime Database 的時候選成了“[默認規則：鎖定模式](https://firebase.google.com/docs/rules/basics?hl=zh-tw#cloud-firestore)”，需要認證才可以打資料上去，因此把規則改成測試模式就可以在測試時不用經過認證，但要注意測試模式會有限制，正式發布需改成鎖定模式並進行身份驗證。\
ANS: 改成測試模式\
![](<.gitbook/assets/CleanShot 2023-04-13 at 16.07.31@2x.jpg>)

\
\
\


\








