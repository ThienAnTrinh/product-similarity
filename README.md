## Project: Product Similarity Matching using Siamese Network

### Overview
Product matching is one of the vital tasks in e-commerce. Since an e-commerce platform has to host a huge amount of products from different vendors, it can face an issue of having a database containing similar products yet presented as different product titles. For example, seller A and seller B are selling the same iphone 10 pro max, but the item is named "iphone 10 pro max" by seller A and "iphone X (pro max)" by seller B. Detecting duplicated items are not only crucial for product catalog management, but can also facilitate important downstream tasks such as product recommendation and product classification. For instance, seller A is selling an item at $10, it would be great if the recommendation system can find a similar item (although with a different name) from user B with a lower price and recommend it to the buyers.

This project aims to experiment with different model architectures on detecting whether 2 product titles refer to the same or different products. This is an NLP classification task where a pair of product titles is labeled as 1 if they are matched and as 0 otherwise.

For example:
* ["iphone 10 pro max", "iphone X (pro max)"] is labeled as 1
* ["samsung galaxy s21", "iphone X pro max"] is labeled as 0

Different model architectures were be built, trained and benchmarked. Siamese networks were also employed, based on [this paper](https://iopscience.iop.org/article/10.1088/1742-6596/1684/1/012074) (Note: the project took initiative from this paper and used it as a reference, but did not use the exact architectures proposed in the paper nor any code from it). The base models of the Siamese networks were recurrent networks such as GRUs which would be trained from scratch or pre-trained BERTs that would be fine-tuned. 

### Objectives
1. Prepare and preprocess a product-matching dataset
2. Build and train/fine-tune different model architectures
3. Benchmark the models and provide insights 

### Dataset
This project uses the ["WDC Product Data Corpus and Gold Standard for Large-Scale Product Matching (LSPM)" dataset](http://webdatacommons.org/largescaleproductcorpus/v2/).
The training dataset is provided in four different sizes, namely small (16.6 MB), medium (47 MB), large (191 MB) and xlarge (405.7 MB) in json format. The small dataset will be used as it fits the available resources.