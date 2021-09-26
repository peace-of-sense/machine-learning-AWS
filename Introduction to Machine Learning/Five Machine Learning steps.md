# Five Machine Learning steps

<img src="https://video.udacity-data.com/topher/2021/April/608c4397_steps/steps.png" alt="Steps of machine learning" style="zoom:67%;" />

### 1. Define the problem

Understand the problem then identify the machine learning task we might use to solve this problem. Two common type of machine learning tasks are,

- Supervised learning
- Unsupervised learning

The presence or absence of labels in your data is often used to identify what type of ml  task can be used.

![Machine learning tasks](https://video.udacity-data.com/topher/2021/April/608c44b0_snsupersuper/snsupersuper.png)

In **supervised learning**, a task is *supervised* if you are using labeled data. We use the term *labeled* to refer to data that already contains the solutions, called *labels*.

**Types of Labels**

1. Categorical labeling- A **categorical** label *has a* **discrete** *(means finite no of values)* *set of possible values.* 

   eg. is a cat, is not a cat.

2. Continuous labeling (Regression)- A **continuous** (regression) label *does not have a discrete set of possible values, which often means you are working with **numerical data**.* 

   eg. Stock exchange prediction uses real numeric values that changes over time. 

In **unsupervised learning**, due to the lack of labeled data we use **clustering**, in which we group specific data with same properties.

-----------

You can use supervised ML approaches for these specific machine learning tasks: binary classification (predicting one of two possible outcomes), multiclass classification (predicting one of more than two outcomes) and regression (predicting a numeric value).

Examples of binary classification problems:

- Will the customer buy this product or not buy this product?
- Is this email spam or not spam?
- Is this product a book or a farm animal?
- Is this review written by a customer or a robot?

Examples of multiclass classification problems:

- Is this product a book, movie, or clothing?
- Is this movie a romantic comedy, documentary, or thriller?
- Which category of products is most interesting to this customer?

Examples of regression classification problems:

- What will the temperature be in Seattle tomorrow?
- For this product, how many units will sell?
- How many days before this customer stops using the application?
- What price will this house sell for?

### 2. Build a Dataset

Working with data is the most important process in training your machine learning model. 

#### Four aspects of working with data

![Steps of working with data](https://video.udacity-data.com/topher/2021/April/608c4dfa_datasteps/datasteps.png)

1. Data Collection

   Data collection can be either simple or complicated, but make sure the data you collected will help solving your problem.

2. Data Inspection

   The quality of your data determines the performance of your model. Impute is the common term referring to different statistical tools which can be used to calculate missing values from your dataset. 

   Always check for 

   * Outliers
   * Missing or incomplete values
   * Transformed or processed data

3. Summary Statistics

   Check *scope*, *scale*, and *shape* of the dataset, whether your data is in-line with the assumptions made by your model. 

   Use statistical formulations like mean, inner quartile range, standard deviation to better understand your data.

4. Data Visualization

   Use plots to show trends and other potential outliers or clusters in the data set.

### 3. Model Training

First and important step in model training is to spilt your data into

* Training data- The data on which the model will be trained.
* Test data- The data withheld from the model during training, which is used to test how well your model will generalize to new data.

#### Model training terminology

*The model training algorithm iteratively updates a model's parameters to minimize some loss function.*

*Model parameter*:  Model parameters are settings or configurations the training algorithm can update to change how the model behaves. Weights are the values that changes as model learns.

**Loss function:** *A loss function is used to codify the model’s distance from this goal. It is a Hyperparameter.*

#### End to end training process 

- Feed the training data into the model.
- Compute the loss function on the results.
- Update the model parameters in a direction that reduces loss.

Loop through this cycle of process until you reach a predefined stop condition.

> ##### Expert says
>
> 1. Use machine learning frameworks that are already made for your model.
> 2. Use model selection, list of established model is ever growing. So, it is recommended to try different types of algorithms for your model.
> 3. Hyperparameters are used to control how quickly or how reliable the model trains. They are set manually and are not updated during model training.
> 4. Iterate!

#### General classifications

* Linear model
* Tree-based model
* Deep learning model

**Linear models**- Simply describe the relationship between set of inputs and set of outputs through a linear function. 
$$
y = mx + b
$$
*Linear Regression* is used to handle regression problems whereas *Logistic regression* is used to handle the **classification** problems.

> Classification is **the task of predicting a discrete class label**. Regression is the task of predicting a continuous quantity.

<img src="https://dataaspirant.com/wp-content/uploads/2014/09/Classification-and-Regression-dataaspirant.png" alt="difference between classification and regression in machine learning" style="zoom: 50%;" />

Linear models are fast to train and gives you a great baseline as compared to other complex models. Always start with simple model.

**Tree-Based models**- They learn to categorize or regress by building an extremely large structure of nested *if/else blocks*, splitting the world into different regions at each if/else block. 

Training determines exactly where these splits happen and what value is assigned at each leaf region. 

The tree-based model XGBoost is commonly used as an off-the-shelf implementation for this kind of model, it is an optimized distributed gradient boosting library designed to be highly efficient, flexible and portable. 

**Deep learning model**- Extremely popular and powerful, deep learning is a modern approach based around a conceptual model of how the human brain functions. 

The **model** (also called a *neural network*) is composed of collections of ***neurons*** (very simple computational units) connected together by ***weights*** (mathematical representations of how much information to allow to flow from one neuron to the next). The process of training involves finding values for each weight.

Some of the popular deep neural network structures,

- **FFNN**: The most straightforward way of structuring a neural network, the Feed Forward Neural Network (FFNN) structures neurons in a series of layers, with each neuron in a layer containing weights to all neurons in the previous layer.
- **CNN**: Convolutional Neural Networks (CNN) represent nested filters over grid-organized data. They are by far the most commonly used type of model when processing images.
- **RNN**/**LSTM**: Recurrent Neural Networks (RNN) and the related Long Short-Term Memory (LSTM) model types are structured to effectively represent *for loops* in traditional computing, collecting state while iterating over some object. They can be used for processing sequences of data.
- **Transformer**: A more modern replacement for RNN/LSTMs, the transformer architecture enables training over larger datasets involving sequences of data.

#### Important python ml libraries

For classical models(Linear, tree based), **Scikit learn**.

For deep learning, **mxnet**, **tensorflow**, **pytorch**.

--------------------------

**bias–variance problem** is the conflict in trying to simultaneously minimize these two sources of [error](https://en.wikipedia.org/wiki/Errors_and_residuals_in_statistics) that prevent [supervised learning](https://en.wikipedia.org/wiki/Supervised_learning) algorithms from generalizing beyond their [training set](https://en.wikipedia.org/wiki/Training_set):

- The [*bias*](https://en.wikipedia.org/wiki/Bias_of_an_estimator) error is an error from erroneous assumptions in the learning [algorithm](https://en.wikipedia.org/wiki/Algorithm). High bias can cause an algorithm to miss the relevant relations between features and target outputs (underfitting).
- The *[variance](https://en.wikipedia.org/wiki/Variance)* is an error from sensitivity to small fluctuations in the training set. High variance may result from an algorithm modeling the random [noise](https://en.wikipedia.org/wiki/Noise_(signal_processing)) in the training data ([overfitting](https://en.wikipedia.org/wiki/Overfitting)).

### 4. Model Evaluation 

After you train your model, it's time to check how well your model is performing. You can understand the performance of your model by looking at its,

* **Model Accuracy:** How accurate is your predicted data compared with the actual data.
* **Log Loss:** It is the indicative value of how close the prediction probability to the corresponding actual value. If the deviation between the prediction and the actual value is more, then the log loss will be more.Model evaluation tools are often tailored to a specific use case.

Model evaluation tools are often tailored to a specific use case.

**Remember: This Process is Iterative**

https://scikit-learn.org/stable/modules/model_evaluation.html

### 5. Model Inference (Use your model)

Once you have trained your model, have evaluated its effectiveness, and are satisfied with the results, you're ready to generate predictions on real-world problems using unseen data in the field. In machine learning, this process is often called **inference**.

Model inference involves, generating predictions, finding patterns, using a trained model, testing your model with unseen data.

### 6. Remember

![iteration of the process](https://video.udacity-data.com/topher/2021/April/608c4f0d_itersteps2/itersteps2.png)

Even after you deploy your model, you're always monitoring to make sure your model is producing the kinds of results that you expect. There may be times where you reinvestigate the data, modify some of the parameters in your model training algorithm, or even change the model type used for training.

