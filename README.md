# Boosting Adversarial Transferability via Gradient Relevance Attack 

## Requirements

+ Python = 3.6.13
+ Tensorflow = 1.13.1
+ Numpy = 1.16.0
+ opencv = 3.4.2.16
+ scipy = 1.2.0
+ pandas =  1.1.1
+ imageio = 2.8.0

## Attack

### Prepare the data and models

Thanks for the selfless contribution of previous work, we adopt the dataset and pretrained models provided in [NI-SI-FGSM](https://github.com/JHL-HUST/SI-NI-FGSM), you may put them in dev_data/ and models/ severally.

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

#### Fine tune $\eta$ in decay indicator
In our experiments, we find decreasing $\eta$ tends to lead higher success rate on the most challenging adversarially trained model IncRes-v2ens, but degrades the performance on normally trained models. Setting $\eta$ around 0.94 can maintain a good balance between adversarially trained models and normally trained models.



