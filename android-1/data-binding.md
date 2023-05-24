# Data binding

Databinding 優點：\
在編譯期間就可以先確認變數及操作行為能夠正確呼叫，避免過去在運行期間呼叫失敗後直接crash。





QA:

使用DataBindingUtil 呼叫setContentView 或是 inflate 常常會失敗，看起來是\<View>Binding型別不同，無法透過呼叫DataBindingUtil回傳的類型轉變回ViewBinding的類型？

ANS:\
DataBindingUtil 透過 setContentView 或是 inflate 的回傳型別為 ViewDataBinding，這個型別只有在layout.xml裡面已經實作 data binding 才會回傳為 ViewDataBinding；如果layout沒有實作data binding，那麼layout.xml自動生成的\<View>Binding檔案會是ViewBinding型別，而ViewDataBinding 繼承了 ViewBinding，因此view binding的回傳型別不可以直接使用DataBindingUtil 。

而view binding 和 data binding，產生的檔案名稱皆為\<View>Binding，但卻可能繼承自不同型別，因此要使用DataBindingUtil需要特別注意是否已經在layout.xml裡面實作data binding。

方便起見，\<View>Binding 型別已經在layout.xml生成時確定，直接使用\<View>Binding.inflate會自動回傳正確的型別，就不會像是DataBindingUtil有錯誤的狀況產生。（理想的狀況還是要在開發時確認好每個layout對應的binding）



DataBindingUtil.java :

<figure><img src="../.gitbook/assets/CleanShot 2023-05-23 at 21.40.58.jpg" alt=""><figcaption><p>DataBindingUtil.setContentView()</p></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2023-05-23 at 21.40.38.jpg" alt=""><figcaption><p>DataBindingUtil.inflate()</p></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2023-05-23 at 17.32.08@2x (1).jpg" alt=""><figcaption><p>Data binding generated.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2023-05-23 at 17.31.49@2x (1).jpg" alt=""><figcaption><p>View binding generated.</p></figcaption></figure>

