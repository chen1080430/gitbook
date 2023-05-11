# Unit Test

在進行viewmoodel 的 livedata測試時一直遇到問題，出現isMainThread的錯誤導致無法單元測試：

<figure><img src="../.gitbook/assets/CleanShot 2023-05-11 at 15.50.31@2x.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/CleanShot 2023-05-11 at 15.50.56@2x.jpg" alt=""><figcaption></figcaption></figure>

爬文後找到應該要補上這段，讓livedata的執行緒在unit test時跑在main thread上：

```
    @get:Rule
    var instantExecutorRule = InstantTaskExecutorRule()
```

但補上之後還是有錯誤。



後來follow google codelabs ([Advanced Android in Kotlin 05.1: Testing Basics](https://developer.android.com/codelabs/advanced-android-kotlin-training-testing-basics?index=..%2F..index)) 做單元測試，viewModel 搭配 livedata 沒有問題，可以順利 pass，對照後找到問題是arch.test這個lib要使用 **androidX** 的，就沒問題了

<figure><img src="../.gitbook/assets/CleanShot 2023-05-11 at 15.46.26@2x.jpg" alt=""><figcaption></figcaption></figure>

```
testImplementation "androidx.arch.core:core-testing:2.2.0"
```

