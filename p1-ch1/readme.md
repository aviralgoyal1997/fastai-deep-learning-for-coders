<h1>CNN to recognize Cats and Dogs</h1>


In lesson1.ipynb we learnt how to do transfer learning on a pretraned resnet model and make a model to differentiate cats and dogs,we did this on crestle but if we wanna do this for different data on our local machine then just download data and save data of separate classes in separate folder in data subdirectory in fastai library which I told u to download in previous readme and then set path to location of that subdirectory and ignore cache part of crestle,other than that code will be same.
You will get many module not found error so just download those python packages and you will be fine.

Download link of dog and cat data : <href>http://files.fast.ai/data/dogscats.zip

<br>So steps performed in project:</br>
<br>1.Copy data into path and then transform it by tfms and then set it for our model,then train last lyer of our model on this data with precompute=True means using some of previous activations.
<br>2.find good learning rate by lr_find()
<br>3.to improve model do data augmentation and perform 1 and then for learning rate use sgdr
<br>unfreeze all layers so we can retune them.

<h1>Using keras for same </h1>
Applications

Keras Applications are deep learning models that are made available alongside pre-trained weights. These models can be used for prediction, feature extraction, and fine-tuning.

Weights are downloaded automatically when instantiating a model. They are stored at ~/.keras/models/.
Available models
Models for image classification with weights trained on ImageNet:

    Xception
    VGG16
    VGG19
    ResNet50
    InceptionV3
    InceptionResNetV2
    MobileNet
    DenseNet
    NASNet
<h2>Example of resnet50 model on Imagenet classes</h2>
<h3><br>from keras.applications.resnet50 import ResNet50
<br>from keras.preprocessing import image
<br>from keras.applications.resnet50 import preprocess_input, decode_predictions
<br>import numpy as np
<br>model = ResNet50(weights='imagenet')
<br>img_path = 'elephant.jpg'
<br>img = image.load_img(img_path, target_size=(224, 224))
<br>x = image.img_to_array(img)
<br>x = np.expand_dims(x, axis=0)
<br>x = preprocess_input(x)
<br>preds = model.predict(x)
<br># decode the results into a list of tuples (class, description, probability)
<br># (one such list for each sample in the batch)
<br>print('Predicted:', decode_predictions(preds, top=3)[0])
<br># Predicted: [(u'n02504013', u'Indian_elephant', 0.82658225), (u'n01871265', u'tusker', 0.1122357), (u'n02504458', u'African_elephant', 0.061040461)]</h3>

for transfer learning on pretrained models and and many other things visit :
<h2><href>https://keras.io/applications/</href></h2>
<br>In model.fit_generator arguments are (train_generator, train_generator.n // batch_size, epochs=3, workers=4,
        validation_data=validation_generator, validation_steps=validation_generator.n // batch_size)</br>
For training our own model <href>https://becominghuman.ai/building-an-image-classifier-using-deep-learning-in-python-totally-from-a-beginners-perspective-be8dbaf22dd8</href>
