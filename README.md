# 大同大學選課軍師｜RAG 對話機器人

TAICA《生成式 AI：文字與圖像生成的原理與實務》第七週作業：打造自己的 RAG 對話機器人。

把大同大學的選課相關規章整理成 27 篇知識文件，建立向量資料庫，再讓「選課軍師」根據查到的規章回答加簽、超修、期中退選、暑修、通識學分等問題，並附上出處。

| 程式 | 做什麼 | 開啟 |
|---|---|---|
| RAG01 | 讀入 `rag-data.zip`，用 EmbeddingGemma 2 + FAISS 建立向量資料庫，輸出 `vector_embedding.zip` | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/otis222/genai-week7-rag/blob/main/RAG01_%E9%81%B8%E8%AA%B2%E8%BB%8D%E5%B8%AB_%E5%BB%BA%E7%AB%8B%E5%90%91%E9%87%8F%E8%B3%87%E6%96%99%E5%BA%AB.ipynb) |
| RAG02 | 自動下載 `vector_embedding.zip`，以「選課軍師」人設回答，最後開啟 Gradio 聊天室 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/otis222/genai-week7-rag/blob/main/RAG02_%E9%81%B8%E8%AA%B2%E8%BB%8D%E5%B8%AB_RAG%E5%B0%8D%E8%A9%B1%E6%A9%9F%E5%99%A8%E4%BA%BA.ipynb) |

## 執行 RAG02

1. 點上方的 **Open in Colab**。
2. 在 Colab 左側鑰匙圖示「密鑰」新增名稱為 `Groq` 的密鑰（值為 Groq API key），並開啟存取權。
3. 「執行階段 → 全部執行」。向量資料庫會從這個 repo 自動下載，不需要上傳任何檔案；最後一格會開啟聊天室。

## 檔案

| 檔案 | 說明 |
|---|---|
| `rag-data/` | 27 篇知識文件，一篇一個 TXT：上方是 metadata，`【內容】` 是要做 embedding 的正文 |
| `rag-data.zip` | 上面 27 篇打包，RAG01 讀入 |
| `vector_embedding.zip` | RAG01 的輸出：`index.faiss`、`documents.json`、`index_doc_ids.json`、`config.json` |

## 資料來源

皆為大同大學官方公開資料：

- [大同大學學生選課辦法](https://tturule.ttu.edu.tw/rulelist/showcontent.php?rid=398)
- [大同大學期中退選課程辦法](https://tturule.ttu.edu.tw/rulelist/showcontent.php?rid=329)
- [大同大學學生暑期補修課程規定](https://tturule.ttu.edu.tw/rulelist/showcontent.php?rid=607)
- [大同大學校訂共同必修基礎課程暨博雅通識課程修課規定](https://tturule.ttu.edu.tw/rulelist/showcontent.php?rid=1116)
- [註冊課務組選課 Q&A](https://curri.ttu.edu.tw/p/412-1033-482.php)
- [115 學年度行事曆](https://reg.ttu.edu.tw/p/405-1032-42221,c910.php)、[115 學年度新生選課專區](https://b0225.ttu.edu.tw/p/406-1078-36651,r11.php?Lang=zh-tw)

> 知識文件是規章的白話改寫摘要，不是法規全文，也不是學校的官方解釋；正式規定以大同大學最新公告為準。

## 參考

- 老師範例：[yenlung/Generative-AI](https://github.com/yenlung/Generative-AI)（RAG_01、RAG_02）
- 資料整理與程式修改有使用生成式 AI（Claude）協助。
