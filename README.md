# [Low Resource Question Answering: An Amharic Benchmarking Dataset](https://aclanthology.org/2024.rail-1.14) (Taffa et al., 2024)
Question Answering (QA) systems return concise answers or answer lists based on natural language text, which uses a given context document. Many resources go into curating QA datasets to advance the development of robust QA  models. There is a surge in QA datasets for languages such as English; this is different for low-resource languages like Amharic. Indeed, there is no published or publicly available Amharic QA dataset. Hence, to foster further research in low-resource QA, we present the first publicly available benchmarking **Amh**aric **Qu**estion **A**nswering **D**ataset (Amh-QuAD). We crowdsource 2,628 question-answer pairs from over 378 Amharic Wikipedia articles. Using the training set, we fine-tune an XLM-R-based language model and introduce a new reader model. Leveraging our newly fine-tuned reader run a baseline model to spark open-domain Amharic QA research interest. The best-performing baseline QA achieves an F-score of 80.3 and 81.34 in retriever-reader and reading comprehension settings.
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
<img width="1318" alt="amh_qa_basline" src="https://github.com/semantic-systems/amharic-qa/assets/58974800/f54a723c-cbe1-4b7d-8c7f-deffd467559c">

## Evaluation
Since the AmQA dataset contains a set of contexts and question-answer pairs, it can be considered a reading comprehension (RC) task. That is, given a question Q and a context, the goal of the model is to identify a word or group of consecutive words that answer question Q. 
On the other hand, retriever-reader-based QA models first retrieve relevant passages, then read top-ranked passages and try to predict the start and end positions of the answer. So, we have implemented a retriever-reader (RR) QA model using the [Farm Haystack](https://haystack.deepset.ai) open-source framework. For the retriever part, we have used BM25 as a retriever and finetuned [XLM-R<sub>Large</sub>](https://huggingface.co/deepset/xlm-roberta-large-squad2) for the reader. The experimental result is shown in the figure given below.

<img width="1127" alt="amh_qa_evaluation" src="https://github.com/semantic-systems/amharic-qa/assets/58974800/0f1d93e6-1f78-4928-aeb8-f12d9ace6130">

### The full paper can be found [here](https://aclanthology.org/2024.rail-1.14.pdf).
#### The dataset is also available on Hugging Face [here](https://huggingface.co/datasets/dagim/amharic-qa).
#### N.B. This work previously released in Arxiv entitled [AmQA: Amharic Question Answering Dataset](https://arxiv.org/pdf/2303.03290).
##### Cite Us
```bibtex
@inproceedings{taffa-etal-2024-low,
    title = "Low Resource Question Answering: An {A}mharic Benchmarking Dataset",
    author = "Taffa, Tilahun Abedissa  and
      Usbeck, Ricardo  and
      Assabie, Yaregal",
    booktitle = "Proceedings of the Fifth Workshop on Resources for African Indigenous Languages @ LREC-COLING 2024",
    month = may,
    year = "2024",
    address = "Torino, Italia",
    publisher = "ELRA and ICCL",
    url = "https://aclanthology.org/2024.rail-1.14",
    pages = "124--132"
}
```
