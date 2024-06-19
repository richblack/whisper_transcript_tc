# 說明
[English ReadMe](README_EN.md)

OpenAI Whisper 可以用來聽打錄音，在研究時需要聽打逐字稿時卻不合用，因為 Whisper 的逐字稿沒有加上標點符號的功能，如果有一篇一個鐘頭的逐字稿，要在每句話後面加上逗號也很辛苦。

這個程式做很簡單的工作：
1. 把語音檔轉成文字；
2. 把簡體中文轉成正體中文；
3. 在每句話後面加上逗號；
4. 把結果轉成 txt 檔供下載。

你可以將檔案下載後再來加工，例如刪除不需要的部分、分段、加上句號或驚歎號。

## 使用方式
* 下載所有檔案，其中 Whisper_TraditionalChinese.ipynb 為主要程式，是 JupyterNotebook 格式
* 在本機使用
  * 在本機電腦安裝 Anaconda 後可以開啓 JupyterLab 使用；
  * 在本機電腦使用其他編輯器，例如 Visual Studio Code 會自動安裝 JupyterNotebook 的插件讓你編輯；
  * 本機要安裝 Python 環境。
* 在雲端使用
  * 可以考慮在 [Google Colab](https://colab.research.google.com/?hl=zh-tw) 執行，方法是從 Google Drive 進去產生連接。
* 把要轉檔的檔案放進「convert_files/」檔案夾中，即可執行。
 
## 測試
我測試的是一個長達 40.42 分、13.2 mb 的訪談錄音，測試結果如下：

| 處理器        | 記憶體 (GB)  | 模型    | 處理時間 (秒)  | 處理時間 (HH:MM'SS) |
|--------------|-------------|--------|--------------|-------------------|
| Windows Intel i7   | 16          | Medium | 2645.06      | 00:44'05          |
| Windows Intel i7   | 16          | Large  | 4497.24      | 01:14'57          |
| MacBook Air M2       | 8           | Medium | 1948.41      | 00:32'28          |
| MacBook Air M2       | 8           | Large  | 27601.83     | 07:40'02          |
| Colab CPU    | 15          | Medium  | 5803.99     | 01:36'44          |
| Colab CPU    | 15          | Large  | 11324.32     | 03:08'44          |

* 使用 Medium 模型的效果就已經很好了。
* 模型要求執行設備的記憶體，例如：MBA M2 只有 8G 記憶體，在 Medium 模型表現非常好，但 Large 模型就非常吃力。
* Colab 的記憶體是查到的。

## 版本
* 20240612: 解決 PC 無法使用相對路徑問題。
* 20240613: 增加自動將音檔轉換成 MP3 格式能力，測試過 WAV（錄音筆）, MP4（會議軟體錄製影音檔）, M4A（手機錄音格式）幾種格式。
* 20240614: 增加 MP4 影片轉 MP3 能力，更新簡化檢查程式庫功能
* 20240618: 增加辨識來源為影片或聲音檔的能力，加快轉檔速度，增加 convert_files/ 檔案夾讓轉檔文件與程式碼分離避免誤刪。