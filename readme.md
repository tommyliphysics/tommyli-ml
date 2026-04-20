# Welcome to my Machine Learning projects

This repository is a collection of machine learning projects on a range of areas in which the rise of artificial intelligence has a high potential for social impact. I've made the training and testing datasets for each project available, as well as detailed jupyter notebooks that can be used to generate the models from scratch (make sure to run pip install requirements.txt for all dependencies). The projects are:

## AI detection

During my time as a postdoctoral researcher in theoretical condensed matter physics, I became aware of the rapidly advancing field of natural language processing (NLP), large-language models (LLMs) and transformer models such as Google's BERT. Researchers in my field had become gripped by excitement about machine learning and its applications both in and outside of the scientific context. The release of Chat-GPT at the end of 2022 brought mass attention to these developments, and today, along with AI-generated audiovisual media, generative AI appears to be in an early stage of revolutionising the role of information technology in society. For most, LLMs are set to become an essential tool, but many view their ever-broadening influence with concern.

Today, there is a huge demand for software that can identify when a text has been produced by AI. But is it possible to use a machine learning model to accurately detect whether a machine learning model has authored a specific text, considering that the model that may have generated the text has been designed specifically to imitate human writing? To explore this problem I created Athena, an open-source AI detection app, available via a web platform at: [https://birefringent-ai.com/athena](https://birefringent-ai.com/athena). The code and documentation can be found at: [https://github.com/tommyliphysics/athena-source](https://github.com/tommyliphysics/athena-source)

## Maximising engagement on YouTube videos

Since its launch in 2005, YouTube has been a hugely impactful resource for people of all ages all around the world. While social media sites such as Facebook, Instagram and TikTok have recently become solid competitors when it comes to short-form video content for entertainment, YouTube stands out by offering long-form video content such as video essays, complete news broadcasts and video tutorials that are particularly suited for informative and educational purposes. With thousands of new videos published daily, YouTube offers a rich source of data well-suited to machine learning techniques. With its popularity continuing to exhibit solid growth I expect ML solutions to become hugely beneficial to YouTube's rapidly expanding base of content creators.

To assist aspiring YouTubers, whether students detailing their educational journey, social media teams at universities, research institutes and labs, or hobbyists and professionals offering product reviews or tutorials, I created [https://birefringent-ai.com/calliope](Calliope), an ML prediction engine trained on hundreds of thousands of YouTube videos. Calliope enables a content creator to explore a range of potential video ideas before committing to creating a video, improving their ability to reach an audience and garner views and subscriptions. 
 
You can find the following files in /youtube_predictor:
* /youtube_predictor/notebooks : Creation of a baseline model using LLM embeddings + classical machine learning with LLM-generated data (yt_prediction.ipynb), evaluation of Calliope's performance on real data (calliope_eval.ipynb)
* /youtube_predictor/data : LLM-generated data used to train the baseline model

## Trends in academic publishing

For better or worse, the success of a contemporary scientist relies on their publication record and their choice of research topic. Since current "hot topics" are generally the easiest to both publish and acquire grants in, one might expect a self-reinforcing pattern where initial excitement in a topic causes a field to grow until the number of publications reaches a stage where the perceived advantages of publishing in that area attracts more research, which then leads to more publications and more grants, and so on. The benefits of such a pattern is that early-career researchers may be brought into the field to rapidly progress it, preventing stagnation after the "low-hanging fruit" problems have been resolved and it becomes progressively more difficult to produce scientific advances in the emerging field. The downside is that, with more senior researchers switching fields, progress in established areas may slow.

Identification of "hot topics" and their associated trends is an application of machine learning that would have important benefits to the scientific community. In this project I look at data from the ArXiv preprint server over a period spanning decades, identify areas of research that have experienced growth and carefully attempt to project these growth trends into the future.

You can find the following files in /arxiv_trends:

* /arxiv_trends/notebooks/ : I look at historical trends in the cond-mat category of the ArXiv.
* /arxiv_trends/data/ : monthly data for the 500 most common keywords by appearance in the publication abstracts and titles.
