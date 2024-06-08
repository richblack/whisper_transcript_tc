# 中文版說明

OpenAI Whisper 可以用來聽打錄音，在研究時需要聽打逐字稿時卻沒有這麼合用，因為 Whisper 的逐字稿沒有加上標點符號的功能，如果有一篇一個鐘頭的逐字稿，要在每句話後面加上逗號也很辛苦。

這個程式做很簡單的工作：
1. 把語音檔轉成文字；
2. 把簡體中文轉成正體中文；
3. 在每句話後面加上逗號；
4. 把結果轉成 txt 檔供下載。

你可以將檔案下載後再來加工，例如刪除不需要的部分、分段、加上句號或驚歎號。

## 使用方式
* 下載 Whisper_TraditionalChinese.ipynb 檔案，這是 JupyterNotebook 格式
* 在本機使用
  * 在本機電腦安裝 Anaconda 後可以開啓 JupyterLab 使用；
  * 在本機電腦使用其他編輯器，例如 Visual Studio Code 會自動安裝 JupyterNotebook 的插件讓你編輯；
  * 本機要安裝 Python 環境。
* 在雲端使用
  * 可以考慮在 Google Colab 執行，方法是從 Google Drive 進去產生連接。
 
## 測試
我測試的是一個長達 40.42 秒、13.2 mb 的訪談錄音，測試結果如下：

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
---
# English Version

OpenAI's Whisper can be used to transcribe audio recordings, but it's not as useful for research work that requires verbatim transcripts, because Whisper's transcripts don't include punctuation. If you have a one-hour transcript, manually adding a comma after each sentence would be a lot of work.

This program does a few simple things:
1. Converts the audio file to text
2. Converts simplified Chinese to traditional Chinese
3. Adds a comma after each sentence
4. Outputs the result as a downloadable txt file

You can then download the file and do further processing, such as deleting unnecessary parts, adding paragraphs, or adding periods or exclamation marks.

## Usage
* Download the Whisper_TraditionalChinese.ipynb file, which is a Jupyter Notebook format
* Using it locally
  * Install Anaconda and you can use JupyterLab
  * Use other editors like Visual Studio Code, which will automatically install the Jupyter Notebook plugin
  * Requires a local Python environment
* Using it in the cloud
  * Can consider running it on Google Colab, by connecting from Google Drive

## Testing
I tested a 40.42 second, 13.2 MB interview recording, with the following results:

| Processor       | Memory (GB) | Model | Time (sec) | Time (HH:MM'SS) |
|-----------------|-------------|-------|------------|-----------------|
| Windows Intel i7| 16          | Medium| 2645.06    | 00:44'05        |
| Windows Intel i7| 16          | Large | 4497.24    | 01:14'57        |
| MacBook Air M2  | 8           | Medium| 1948.41    | 00:32'28        |
| MacBook Air M2  | 8           | Large | 27601.83   | 07:40'02        |
| Colab CPU       | 15          | Medium| 5803.99    | 01:36'44        |
| Colab CPU       | 15          | Large | 11324.32   | 03:08'44        |

* The Medium model already gives very good results
* The models require a lot of memory - for example, the 8GB MacBook Air M2 handled the Medium model well but struggled with the Large model
* The Colab memory capacity is what I looked up
