# Welcome to my Machine Learning projects

This repository is a collection of machine learning projects on a number of topics that I have been developing an interest in. I've made the training and testing datasets for each project available, as well as detailed jupyter notebooks that can be used to generate the models from scratch (make sure to run pip install requirements.txt for all dependencies). The projects are:

## AI detection

During my time as a postdoctoral researcher in theoretical condensed matter physics, I became aware of the rapidly advancing field of natural language processing (NLP), large-language models (LLMs) and transformers such as Google's BERT. Researchers in my field had become gripped by excitement about machine learning and its applications both in and outside of the scientific context. The release of Chat-GPT at the end of 2022 brought mass attention to these developments, and today, along with AI-generated audiovisual media, generative AI appears to be in an early stage of completely revolutionising the role of information technology in society. For most, LLMs are set to become an essential tool, but many view its increasingly pervasive influence with concern. Developing software that can identify when a text has been produced by AI is becoming a critical need. This of course raises a fascinating theoretical challenge: is it possible to use a machine learning model to accurately detect whether a machine learning model has authored a specific text, considering that the model that may have generated the text has been designed specifically to imitate human writing?

I explored this problem by training LLMs to detect AI-generated text rather than create it and the full process is documented in "/ai_detector." For training and testing, I compiled a dataset of 12090 human-generated texts obtained from Wikipedia, Reddit and IMDB, and generated 12090 samples of matching text using GPT-3.5 Turbo. I then trained two variants of BERT to recognise AI-generated text.

One of the models is deployed on a serverless container at AWS Fargate and can be used as an app via a web portal at https://tommyliphysics.github.io/ai_detector/ .

![AIDetectorDemov3-Made-with-Clipchamp_1717406081115](https://github.com/tommyliphysics/tommyli-ml/assets/166401665/234e6b85-fcd6-49cf-8fda-cef56467465b)

You can find the following files in /ai_detector:
* /ai_detector/notebooks/ : I document the preprocessing of the raw data in preparation for machine learning (data_wrangling.ipynb), exploratory data analysis using NLP methods (EDA.ipynb), the creation of two models (deberta.ipynb and distilbert.ipynb) and model testing (eval.ipynb).
* /ai_detector/data/ : the raw datasets (reddit.csv, imdb.csv, wiki.csv, gpt_reddit.csv, gpt_reviews.csv, gpt_wiki.csv), the cleaned datasets (reddit_cleaned.csv, imdb_cleaned.csv, wiki_cleaned.csv, gpt_reddit_cleaned.csv, gpt_reviews_cleaned.csv, gpt_wiki_cleaned.csv), the final form of the data used for training and testing and the split train/test sets (samples.csv, train.csv, test.csv), and the full text used to train a sentencepiece tokenizer (corpus.txt)
* /ai_detector/tokenizers/ : various tokenizers trained during EDA.

## YouTube popularity prediction

Since its launch in 2005, YouTube has been a hugely impactful resource for people of all ages all around the world. While social media sites such as Facebook, Instagram and TikTok have recently become solid competitors when it comes to short-form video content for entertainment, YouTube stands out by offering long-form video content such as video essays, complete news broadcasts and video tutorials that are particularly suited for informative and educational purposes. With thousands of new videos published daily, YouTube offers a rich source of data well-suited to machine learning techniques. With its popularity continuing to exhibit solid growth I expect ML solutions to become hugely beneficial to YouTube's rapidly expanding base of content creators.

The question I address in this project is: how well can the popularity of a YouTube video be predicted by text features such as the video title and description? Developing such a tool would enable a content creator to explore a range of potential video ideas before committing to creating a video, improving their ability to reach an audience and garner views and subscriptions. I compiled a dataset consisting of metadata for 31662 YouTube videos published in the last seven years in topics related to science and technology, and created a number of classical machine learning models.

Five of these models are deployed on a serverless container at AWS Fargate and can be used as an app via a web portal at https://tommyliphysics.github.io/youtube_predictor/ .

![ytpredictor](https://github.com/tommyliphysics/tommyli-ml/assets/166401665/28a0748f-7dc5-4690-9236-fd5420b9951d)

You can find the following files in /youtube_predictor:
* /youtube_predictor/notebooks : I document the exploratory data analysis using NLP methods (EDA.ipynb), model building via classical machine learning methods with Bayesian hyperparameter optimisation (tfidf.ipynb), and testing (eval.ipynb)
* /youtube_predictor/data : raw datasets (video_metadata_v1.csv, video_metadata_v2.csv - v2 was used for training and testing the models), the final datasets used for training and testing and the split train/test sets (YT_data_v2.csv, train.csv, test.csv), and optimised hyperparameters for various models (logreg_tune.csv, mnB_tuned.csv, perceptron_tuned.csv, SVM_tuned.csv)
* /youtube_predictor/tokenizers : byte-pair encoding tokenizers trained during EDA.

## Trends in academic publishing

For better or worse, the success of a contemporary scientist relies on their publication record, and their choice of research topic. Since "hot topics" are generally the easiest to both publish and acquire grants in, one might expect a self-reinforcing pattern where initial excitement in a topic causes a field to grow until the number of publications reaches a stage where the perceived advantages of publishing in that area attracts more research, which then leads to more publications and more grants, and so on. The benefits of such a pattern is that early-career researchers may be brought into the field to rapidly progress it, preventing stagnation after the "low-hanging fruit" problems have been resolved and it becomes progressively more difficult to produce scientific advances in the emerging field. The downside is that, with more senior researchers switching fields, progress in established areas may slow.

Identification of "hot topics" and their associated trends is an application of machine learning that would have important benefits to the scientific community. In this project I look at data from the ArXiv preprint server over a period spanning decades, identify areas of research that have experienced growth and carefully attempt to project these growth trends into the future.

You can find the following files in /arxiv_trends:

* /arxiv_trends/notebooks/ : I look at historical trends in the cond-mat category of the ArXiv.
* /arxiv_trends/data/ : monthly data for the 500 most common keywords by appearance in the publication abstracts and titles.
