# Android Livedata

{% embed url="https://blog.csdn.net/qq_15059163/article/details/112351401" %}

在livedata使用 Transformations時，發現找不到這個class，進到lifecycle-livedata:2.6.1中去找有找到[androidx.lifecycle.Transformations](https://developer.android.com/reference/androidx/lifecycle/Transformations)，但是是class檔案，無法直接使用。

<figure><img src=".gitbook/assets/CleanShot 2023-05-11 at 14.20.54@2x.jpg" alt=""><figcaption></figcaption></figure>

後來在官網上把語言切到kotlin，發現Transformations已經更換用法，直接作為ｌlivedata擴展函數使用，livedata.map / switchMap / distinctUntilChanged 使用即可。

<figure><img src=".gitbook/assets/CleanShot 2023-05-11 at 14.18.02@2x.jpg" alt=""><figcaption></figcaption></figure>
