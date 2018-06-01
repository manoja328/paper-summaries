# Do Better ImageNet Models Transfer Better?
[https://arxiv.org/pdf/1805.08974.pdf](https://arxiv.org/pdf/1805.08974.pdf)

This papers talks about transfer ability of CNN models trianed on ImageNet on different datasets. They summarize three major
findings:

1.  When models are used as only a feature extractor, the models resutls
    are not predictable enought to perform well on other tasks ( show by using r-squared value for correlation).
2.  When models are finetuned, the overall results improved and even got SOTA for some datasets.
3.  When model are trained from scratch with random initilization their performance are similar to pretrained Imagenet models 
for fine grained classification tasks.

They postulate that, although ImageNet pretrained networks produce small improvement  across many datasets but they may not be as 
general as previously suggested.
