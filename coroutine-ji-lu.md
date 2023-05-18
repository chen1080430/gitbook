# Coroutine 紀錄





### Job: launch / async 子工作

launch : 執行並發(非阻塞線程)的程式區塊

async : 同launch，執行並發(非阻塞線程)的程式區塊，但可以記錄下結果( Deferred\<T> )，為job物件，並透過.await讀取執行結果。



### coroutineScope

runBlocking: coroutine執行為同步(阻塞線程)的區塊。

coroutineScope(): 同 runBlocking 內部可以執行launch / async進行並發(阻塞線程)，但外部看到coroutineScope()會是同步運行的狀態。

coroutineScope與生命週期連結，如果生命週期遭取消，coroutineScope也會一並取消。

coroutine例外狀況終止：oroutine的job有父子關係，子項的job如果遭到例外狀況終止，也會向上延伸到父項、父項的父項。

coroutine取消：如果是子項遭取消，則父項不受影響。如果是父項取消，子項也會跟著取消。



阻塞＆非阻塞：

阻塞現成會卡住當前線程，如果在Main thread，則會有ANR的問題，但優點可以讓原先網路及資料庫等耗時操作可以做成流水型操作，不用聽取callback做反應。阻塞線程更為簡潔易讀，流水型的程式區塊更容易閱讀。

非阻塞線程(並發)則是可以同時運行多個線程，如果同時要從多個網路資源或是資料庫讀取資料，透過這種方式就不會互相卡到執行緒，尤其是用戶界面可以保持流暢且對用戶的操作保持即時響應。並且，非同步任務，可以提高應用程式的性能和響應性。



### CoroutineContext：

CoroutineContext：定義協同程式的行為，可包含工作和協同程式調度工具的參考資料。

使用以下元素定義協同程式的行為：

* [`Job`](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines/-job/index.html)：控管協同程式的生命週期。
* [`CoroutineDispatcher`](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines/-coroutine-dispatcher/index.html)：將工作調派給適當的執行緒。
* [`CoroutineName`](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines/-coroutine-name/index.html)：協同程式的名稱，用於偵錯。
* [`CoroutineExceptionHandler`](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines/-coroutine-exception-handler/index.html)：處理未擷取的例外狀況。





### CoroutineDispatcher - Kotlin 內建調度程式：

* **Dispatchers.Main**：使用這個調派程式在 Android 主執行緒上執行協同程式。這個調度工具主要用於處理 UI 更新和互動，以及執行快速作業。
* **Dispatchers.IO**：這個調派程式已完成最佳化調整，以便在主執行緒外執行磁碟或網路 I/O。例如讀取或寫入檔案，以及執行任何網路作業。
* **Dispatchers.Default**：如果未在結構定義中指定調度工具，系統在呼叫 `launch()` 和 `async()` 時使用此預設調度工具。您可以使用這個調度工具，在主執行緒之外執行計算密集型作業。例如，處理點陣圖圖片檔。

withContext(調度程式): 透過withContext可以調度到不同的執行緒上。\




`suspend` 修飾符用於標示稍後可以暫停並繼續執行的函式。



## [在 Android 应用中使用 Kotlin 协程](https://developer.android.com/codelabs/kotlin-coroutines?hl=zh-cn) (重構BACKGROUND方式，避免使用callback，調整成blocking)

