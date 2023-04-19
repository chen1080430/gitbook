# Kotlin Scope function

這幾個都是kotlin裡面常用的Scope functions，讓呼叫的object額外執行一些程式碼，在kotlin語法使用更便利。

過去我們宣告了變數，或是從其他地方獲取了參數，可能都會打印來看看詳細資訊，透過scope function，就可以更簡便地進行這些操作。

|       | object reference | return value                  | extenstion function | 常見用途                                                                               |
| ----- | ---------------- | ----------------------------- | ------------------- | ---------------------------------------------------------------------------------- |
| let   | it               | Lambda (最後一行 or return value) | v                   | <p>1.確認NPE之後執行程式碼片段</p><p>2.回傳lambda不限於object reference本身，因此可以對object操作後回傳新的參數</p> |
| apply | this             | this                          | v                   | 變數宣告之後對內部成員或內部方法操作                                                                 |
| also  | it               | this                          | v                   | 同apply，但使用的是object是it                                                              |
| run   | this             | Lambda (最後一行 or return value) | v                   | 運行一段程式碼                                                                            |
| with  | this             | Lambda (最後一行 or return value) | n                   | 變數宣告時設定member                                                                      |



### run

跟let相似，常用做宣告變數或計算return value值，因為使用的是object reference，因此使用起來不用先呼叫it才進行操作，視覺更清晰也更方便。

non-extention function 和 extention function 皆可使用。



### with

唯一的 non-extention function



### apply

最常應用在設置變數



