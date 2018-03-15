<h1>CNN to recognize Cats and Dogs</h1>


In lesson1.ipynb we learnt how to do transfer learning on a pretraned resnet model and make a model to differentiate cats and dogs,we did this on crestle but if we wanna do this for different data on our local machine then just download data and save data of separate classes in separate folder in data subdirectory in fastai library which I told u to download in previous readme and then set path to location of that subdirectory and ignore cache part of crestle,other than that code will be same.
You will get many module not found error so just download those python packages and you will be fine.

Download link of dog and cat data : <href>http://files.fast.ai/data/dogscats.zip

<br>So steps performed in project:</br>
<br>1.Copy data into path and then transform it by tfms and then set it for our model,then train last lyer of our model on this data with precompute=True means using some of previous activations.
<br>2.find good learning rate by lr_find()
<br>3.to improve model do data augmentation and perform 1 and then for learning rate use sgdr
<br>unfreeze all layers so we can retune them.
