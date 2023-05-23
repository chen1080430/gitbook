# Data binding

Databinding 優點：\
在編譯期間就可以先確認變數及操作行為能夠正確呼叫，避免過去在運行期間呼叫失敗後直接crash。





QA:

使用DataBindingUtil 呼叫setContentView 或是 inflate 常常會失敗，看起來是\<View>Binding型別不同，無法透過呼叫DataBindingUtil回傳的類型轉變回ViewBinding的類型？

