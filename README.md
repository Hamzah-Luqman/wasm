# WASM dataset

This repository contains the code and dataset (will be released soon) for the research paper "_WASM: A Dataset for Hashtag Recommendation for Arabic Tweets_". In this paper, we introduced a benchmarked dataset for Arabic tweet hashtag recommendations. In addition, the dataset can be used for several tasks related to tweets and hashtags, such as filtering tweets of each hashtag. The proposed dataset was subject to several rounds of automatic and manual filtrations to ensure that it is suitable for tasks related to tweets and hashtags. We also presented three baseline models to approach this task from classification and generation aspects.

![Word Cloud](figures/words_cloud.png)

Dataset Statistics

| Number of Collected tweets        | 2,717,000 |
| --------------------------------- | ------- |
| Number of Tweets after filtration | 101,099  |
| Number of hashtags                | 87      |
| Number of words                   | 1,637,022 |
| Number of unique words            | 111,402  |


Top hashtags in terms of the number of tweets:

![Top Hashtags according to the number of tweets](figures/top_hashtags.png)


# Baselines

We introduced the following baseline models:

## Classification-based baselines

We proposed a hashtag recommendation system by considering this task as a classification problem. We used a BERT-based classification model trained on Arabic tweets obtained using AraBERT as an embedding layer. AraBERT is a project to create Arabic BERT-based pretrained models with various setups. We experimented with two pretrained BERT models employing two preprocessing schemes. The pretrained models explored with normal Arabic text and with Farasa-based tokenization text. The preprocessing schemes were experimented to just feed the tweet as is or challenge it more by masking its Hashtags.


## Generation-based baselines

Hashtag recommendation can also be considered as a text generation problem, where we generate a text (i.e., hashtag in our task) based on the tweet text. Several models have been proposed in the literature for text generation, such as sequence-to-sequence that can be transformer-based like T5 or just LSTM-based. However, few approaches have been proposed for hashtag generation. Inspired by a previous study [https://doi.org/10.1145/3466876], we propose the AraHASHET architecture for hashtag generation.


### NER-based generation model

During the data-collection stage, we noted that numerous tweets contain entities that are also available in the tweet text. To find the types of entities, we manually clustered hashtags based on the types of entities within the hashtag. This clustering resulted in labeling 6 hashtags as location hashtags, 44 as
organizational hashtags, and 30 as individual hashtags. These three clusters are not mutually exclusive, as a hashtag can appear in more than one cluster. Other hashtags that do not belong to these three main types are excluded.
