# READ ME
[中文版](README_ZH.md)

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

## Versions
* 20240612: Resolved the issue with relative paths not being usable on PC.
* 20240613: Added the ability to automatically convert audio files to MP3 format. Tested with WAV (voice recorder), MP4 (video recordings from meeting software), and M4A (Apple recording format).