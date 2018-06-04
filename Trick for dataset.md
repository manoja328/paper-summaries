Most of the content has been summarized from the link below.

[https://petewarden.com/2018/05/28/why-you-need-to-improve-your-training-data-and-how-to-do-it/](https://petewarden.com/2018/05/28/why-you-need-to-improve-your-training-data-and-how-to-do-it/)

# Unreasonable effectiveness of training data
Deep learning model enjoy so much improvement over traditional models because of the vast amount of data avaialble to these
models. While deep learning models can learn even without hand engineered features as they used to be, now the performance rest
solely on the quality of the  data and the complexity/effectiveness of the model. The author of the above blog talks about the
importance of looking into the training and testing data first before diving into optimizing any model.

Even with much better models, the final performance numbers didnot show much improvement. What could be the problem? The author 
suspected there could be something wrong with the data itself. He checked some examples where most models were failing, and with 
simple data cleaning he got decent performance even with an approach behind the SOTA.

He suggest to first visualize the data:
1. View images ( in some case the images were corrupted / wrong labels).
2. For text datasets, dump some random paragraphs and read the actual workds.

He emphasized the point of "garbase in - garbage out" meaning if we provide wrong data we can never expect our models 
to provide correct outputs. To begin often start with models that have been trained in large datasets and the finetune 
for your own dataset.

Next, he talks about sometimes while collecting data phrasing questions differently can dramatically impove resuts.
Especially useful when crowdsourcing is your major way of collecting data.

Then, he focusses on training of realistic data ( for eg. for dron image recognition training on imagenet may not be 
that fruitful since these images are too perfect and may not simulate real world variations.)

Start with printing **Confusion matrix** for your models output and analyze the output.

Most of the times cluster visualizaiton from **embedding layer** in CNNs or RNNs can provide additional information about
how model is behaving/encoding different inputs and even see the cluster distances for some incorrect classifications.

There is no downside in investing in getting more quality data. It should eventually turn out to be a fruitful investment.

Some filtering is also necessary in how you show your output if you are selling the model's output to customers. For example,
in text-generation if might be good approach to black-list some curse words. Also, models should be tested for dataset biases 
( of course this again points to getting quality and unbiased data that simulates real world).


