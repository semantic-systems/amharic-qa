# AmQA: Amharic Question Answering Dataset
## Abstract
Question Answering (QA) returns concise answers or answer lists from natural language text given a context document. To advance robust models' development, many resources go into curating QA datasets. There is a surge of QA datasets for languages like English, however, this is not the case for Amharic. Amharic, the official language of Ethiopia, is the second most spoken Semitic language in the world. There is no published or publicly available Amharic QA dataset. Hence, to foster the research in Amharic QA, we present the first Amharic QA (AmQA) dataset. We crowdsourced 2628 question-answer pairs over 378 Wikipedia articles. Additionally, we run an XLMR<sub>Large</sub>-based baseline model to spark open-domain QA research interest. The best-performing baseline achieves an F-score of 69.58 and 71.74 in reader-retriever QA and reading comprehension settings respectively.
## Dataset
In Amharic, interrogative sentences can be formulated using information-seeking pronouns like “ምን” (what), “መቼ” (when), “ማን” (who), “የት” (where), “የትኛው” (which), etc. and prepositional interrogative phrases like “ለምን” [ለ-ምን] (why), “በምን” [በ-ምን] (by what), etc. Besides, a verb phrase could be used to pose questions (Getahun 2013; Baye 2009). As shown below, the AmQA dataset contains context, question, and answer triplets. The contexts are articles collected from Amharic [Wikipedia](https://am.wikipedia.org/wiki/ዋናው_ገጽ) dump file. The question-answer pairs are created by crowdsourcing and annotated using the [Haystack QA annotation tool](https://www.deepset.ai/annotation-tool-for-labeling-datasets). 2628 question and answer pairs are created from 378 documents.
The whole [AmQA dataset](AmQA_Dataset.json) can be found here. We also split the dataset into [train](train_data.json), [dev](dev_data.json), and [test](test_data.json) with a size of 1728, 600, and 300 respectively.

```json
  {
   "paragraphs": [
        {
          "qas": [
            {
              "question": "በላሊበላ ስንት ውቅር አብያተ ክርስቲያናት አሉ?",
              "id": 272819,
              "answers": [
                {
                  "answer_id": 270463,
                  "document_id": 266719,
                  "question_id": 272819,
                  "text": "11",
                  "answer_start": 290,
                  "answer_end": 292,
                  "answer_category": null
                }
              ],
              "is_impossible": false
            },
            {
              "question": "ከላሊበላ አስራ አንዱ ውቅር አብያተ ክርስቲያናት ግዙፉ የትኛው ነው?",
              "id": 272822,
              "answers": [
                {
                  "answer_id": 270466,
                  "document_id": 266719,
                  "question_id": 272822,
                  "text": "ቤተ መድሃኔ ዓለም",
                  "answer_start": 372,
                  "answer_end": 383,
                  "answer_category": null
                }
              ],
              "is_impossible": false
            },
            {
              "question": "በላሊበላ የጌታ ልደት ቀን በቤተ ማርያም የሚቀርበው ልዩ ዝማሬ ምን ይባላል?",
              "id": 272836,
              "answers": [
                {
                  "answer_id": 270480,
                  "document_id": 266719,
                  "question_id": 272836,
                  "text": "ቤዛ ኩሉ",
                  "answer_start": 465,
                  "answer_end": 470,
                  "answer_category": null
                }
              ],
              "is_impossible": false
            }
          ],
          "context": "ንጉሡ ላሊበላ የሚለውን ስም ያገኘው፣ ሲወለድ በንቦች ስለተከበበ ነው። ላል ማለት ማር ማለት ሲሆን፤ ላሊበላ ማለትም -ላል ይበላል (ማር ይበላል) ማለት አንደሆነ ይነግራል።  ውቅር ቤተክርስቲያናቱን ንጉሡ ጠርቦ የስራቸው ከመላእክት እገዛ ጋር እንደሆነ በኢትዮጵያ ኦርቶዶክስ እምነት ተከታዮች ይነግራል። በ16ኛው ከፍለ ዘመን አውሮፓዊ ተጓዥ ላሊበላን ተመልክቶ «ያየሁትን ብናግር ማንም እንደኔ ካላየ በፍጹም አያምነኝም» ሲል ተናግሮ ነበር። በላሊበላ 11 ውቅር ዐብያተ ክርስቲያናት ያሉ ሲሆን ከነዚህም ውስጥ ቤተ ጊዮርጊስ (ባለ መስቀል ቅርፁ) ሲታይ ውሃልኩን የጠበቀ ይመስላል። ቤተ መድሃኔ ዓለም የተባለው ደግሞ ከሁሉም ትልቁ ነው። ላሊበላ (ዳግማዊ ኢየሩሳሌም) የገና በዓል ታህሳስ 29 በልዩ ሁኔታ ና ድምቀት ይከበራል፣ \"ቤዛ ኩሉ\" ተብሎ የሚጠራው በነግህ የሚደረገው ዝማሬ በዚሁ በዓል የሚታይ ልዩ ና ታላቅ ትዕይንት ነው።የሚደረገውም ከቅዳሴ በኋላ በቤተ ማርያም ሲሆን ከታች ባለ ነጭ ካባ ካህናት ከላይ ደግሞ ባለጥቁር ካብ ካህናት በቅዱስ ያሬድ ዜማ ቤዛ ኩሉ እያሉ ይዘምራሉ። 11ዱ የቅዱስ ላሊበላ ፍልፍል አብያተ ክርስቲያናት ቤተ መድሃኔ ዓለም፣ ቤተ ማርያም፣ ቤተ ደናግል፣ ቤተ መስቀል፣ ቤተ ደብረሲና፣ ቤተ ጎለጎታ፣ ቤተ አማኑኤል፣ ቤተ አባ ሊባኖስ፣ ቤተ መርቆሬዎስ፣ ቤተ ገብርኤል ወሩፋኤል፣ ቤተ ጊዮርጊስ ናቸው።",
          "document_id": 266719
        }
      ]
    }
```
## Baseline Model
Since the AmQA dataset contains a set of contexts along with question-answer pairs, it can be considered as a reading comprehension (RC) task. That is, given a question Q and a context, the goal of the model is to identify a word or group of consecutive words that answer question Q. Hence, based on this assumption we have set a baseline value for the AmQA using XLM-R (Cross-Lingual Language Model-RoBERTa) based QA model. On the other hand, retriever-reader-based QA models first retrieve relevant passages, then read top-ranked passages and try to predict the start and end positions of the answer. So, we have implemented a retriever-reader (RR) QA model using the [Farm Haystack](https://haystack.deepset.ai) open-source framework. For the retriever part, we have used BM25 and [XLM-R<sub>Large</sub>](https://huggingface.co/deepset/xlm-roberta-large-squad2) is used as a reader. The experimental result is shown in the figure given below.

<img width="518" alt="Screenshot 2022-11-29 at 13 18 01" src="https://user-images.githubusercontent.com/58974800/223388047-cbece715-05bf-4de4-b545-55063a26c354.png">

### The full paper can be found [here](https://arxiv.org/abs/2303.03290).
#### The dataset is also available on Hugging Face [here](https://huggingface.co/datasets/dagim/amharic-qa).
