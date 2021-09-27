# Computer Vision

Computer vision first started in 1960s. Since its inception, it has been an interdisciplinary field. Modern day computer vision uses neural networks, these networks can quickly be trained with millions of images and produce highly accurate predictions.

Early computer vision needed hand annotated images to successfully train a model. It was a tedious and time consuming process.

Modern day CV uses three main component of neural network,

1. **Input layer**: This layer receives data during training and when inference is performed after the model has been trained.
2. **Hidden Layer**: This layer finds important features in the input data that have predictive power based on the labels provided during training.
3. **Output Layer**: This layer generates the output or prediction of your model.

Modern day CV uses Convolution Neural Networks or CNN. These NN uses hidden layers to extract different information from about the images. This process is called **feature extraction**. These models can be trained much faster on millions of images and generate a better prediction than earlier models.

## Application

Computer vision (CV) has many real-world applications. 

* **Image classification** is the most common application of computer vision in use today. Image classification can be used to answer questions like *What's in this image?* This type of task has applications in *text detection* or *optical character recognition (OCR)* and *content moderation*.
* **Object detection** is closely related to image classification, but it allows users to gather more granular detail about an image. For example, rather than just knowing whether an object is present in an image, a user might want to know if there are *multiple instances of the same object* present in an image, or if *objects from different classes* appear in the same image.
* **Semantic segmentation** is another common application of computer vision that takes a pixel-by-pixel approach. Instead of just identifying whether an object is present or not, it tries to identify down the pixel level which part of the image is part of the object.
* **Activity recognition** is an application of computer vision that is based around videos rather than just images. Video has the added dimension of time and, therefore, models are able to detect changes that occur over time.

## AWS DeepLens

AWS DeepLens allows you to create and deploy end-to-end computer vision–based applications. The following video provides a brief introduction to how AWS DeepLens works and how it uses other AWS services.

## Summary

AWS DeepLens is a **deep learning–enabled camera** that allows you to deploy trained models directly to the device. You can either use sample templates and recipes or train your own model.

AWS DeepLens is integrated with several AWS machine learning services and can perform local inference against deployed models provisioned from the AWS Cloud. It enables you to learn and explore the latest artificial intelligence (AI) tools and techniques for developing computer vision applications based on a deep learning model.

### The AWS DeepLens device

The AWS DeepLens camera is powered by an Intel® Atom processor, which can process 100 billion floating-point operations per second (GFLOPS). This gives you all the computing power you need to perform inference on your device. The micro HDMI display port, audio out, and USB ports allow you to attach peripherals, so you can get creative with your computer vision applications.



<img src="https://video.udacity-data.com/topher/2021/April/6072536e_31cya1azvfl.-ac-/31cya1azvfl.-ac-.jpg" alt="An AWS DeepLens Device" style="zoom: 50%;" />



<img src="https://video.udacity-data.com/topher/2021/April/607a0379_screen-shot-2021-04-16-at-2.36.08-pm/screen-shot-2021-04-16-at-2.36.08-pm.png" alt="An image showing how AWS DeepLens works" style="zoom: 50%;" />

### How AWS DeepLens works

AWS DeepLens is integrated with multiple AWS services. You use these services to create, train, and launch your AWS DeepLens project. You can think of an AWS DeepLens project as being divided into two different streams as the image shown above.

- First, you use the AWS console to create your project, store your data, and train your model.
- Then, you use your trained model on the AWS DeepLens device. On the device, the video stream from the camera is processed, inference is performed, and the output from inference is passed into two output streams:
  - **Device stream** – The video stream passed through without processing.
  - **Project stream** – The results of the model's processing of the video frames.

AWS DeepLens is integrated with multiple AWS services. You use these services to create, train, and launch your AWS DeepLens project. To create any AWS DeepLens–based project you will need an AWS account.

Four key components are required for an AWS DeepLens–based project.

1. **Collect your data:** Collect data and store it in an Amazon S3 bucket.
2. **Train your model:** Use a Jupyter Notebook in Amazon SageMaker to train your model.
3. **Deploy your model:** Use AWS Lambda to deploy the trained model to your AWS DeepLens device.
4. **View model output:** Use Amazon IoT Greenrass to view your model's output after the model is deployed.

### Computer vision-based tasks

1. Object Detection: different objects are present and the number of objects present in an image. 

   Eg: To detect boy cat and dog.

2. Image Classification: Classify image based on certain parameters. 

   Eg: Dog is sleeping.

3. Semantic (Instance) Segmentation: Semantic segmentation is best used to identify the exact location (pixel) of an object in an image.

   Eg: Exact location of cat.

4. Optional Character Recognition: To identify texts in image.
5. Activity recognition is primarily used with video.

