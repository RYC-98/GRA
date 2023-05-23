# GRA

## Requirements

+ Python = 3.6.13
+ Tensorflow = 1.13.1
+ Numpy = 1.16.0
+ opencv = 3.4.2.16
+ scipy = 1.2.0
+ pandas =  1.1.1
+ imageio = 2.8.0

## Qucik Start

### Prepare the data and models

You should download the [data](https://drive.google.com/drive/folders/1CfobY6i8BfqfWPHL31FKFDipNjqWwAhS) and [pretrained models](https://drive.google.com/drive/folders/10cFNVEhLpCatwECA6SPB-2g0q5zZyfaw) and place the data and pretrained models in dev_data/ and models/, respectively.

### GRA

#### Runing attack

Taking GRA attack for example, you can run this attack as following:

```
CUDA_VISIBLE_DEVICES=gpuid python GRA_v3.py 
```

All the provided codes generate adversarial examples on inception_v3 model. If you want to attack other models, replace the model in `graph` and `batch_grad` function and load such models in `main` function.

The generated adversarial examples would be stored in directory `./outputs`. Then run the file `simple_eval.py` to evaluate the success rate of each model used in the paper:

```
CUDA_VISIBLE_DEVICES=gpuid python simple_eval.py
```

### More questions about my paper or exchange ideas
Send an email to my mailbox: ryc_981015@163.com
