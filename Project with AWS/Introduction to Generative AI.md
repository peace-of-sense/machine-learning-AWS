# Generative AI

Generative AI is one of the biggest recent advancements in artificial intelligence because of its ability to create new things.

![An image showing discriminative versus generative algorithms](https://video.udacity-data.com/topher/2021/May/6091a6b8_screen-shot-2021-05-04-at-12.55.15-pm/screen-shot-2021-05-04-at-12.55.15-pm.png)

### Popular Generative models

* **Autoregressive models:** *Autoregressive convolutional neural networks (AR-CNNs)* are used to study systems that evolve over time and assume that the likelihood of some data depends only on what has happened in the past. It’s a useful way of looking at many systems, from weather prediction to stock prediction.
* **Generative adversarial networks (GANs):** *Generative adversarial networks (GANs)*, are a machine learning model format that involves pitting two networks against each other to generate new content. The training algorithm swaps back and forth between training a *generator network* (responsible for producing new data) and a *discriminator network* (responsible for measuring how closely the generator network’s data represents the training dataset).
* **Transformer-based models**: *Transformer-based models* are most often used to study data with some sequential structure (such as the sequence of words in a sentence). Transformer-based methods are now a common modern tool for modeling natural language.

## AWS DeepComposer

Each AWS DeepComposer Music studio experience supports three different generative AI techniques: generative adversarial networks (GANs), autoregressive convolutional neural network (AR-CNNs), and transformers.

- Use the GAN technique to create accompaniment tracks.
- Use the AR-CNN technique to modify notes in your input track.
- Use the transformers technique to extend your input track by up to 30 seconds.

## What are GANs?

A GAN is a type of generative machine learning model which pits two neural networks against each other to generate new content: a generator and a discriminator.

- A *generator* is a neural network that learns to create new data resembling the source data on which it was trained.
- A *discriminator* is another neural network trained to differentiate between real and synthetic data.

The generator and the discriminator are trained in *alternating cycles*. The generator learns to produce more and more realistic data while the discriminator iteratively gets better at learning to differentiate real data from the newly created data.

<img src="https://video.udacity-data.com/topher/2021/April/6088998a_screen-shot-2021-04-27-at-4.08.43-pm/screen-shot-2021-04-27-at-4.08.43-pm.png" alt="A schema representing a GAN model used within AWS DeepComposer" style="zoom:50%;" />

### Generator

- The generator takes in a batch of single-track piano rolls (melody) as the input and generates a batch of multi-track piano rolls as the output by adding accompaniments to each of the input music tracks.
- The discriminator then takes these generated music tracks and predicts how far they deviate from the real data present in the training dataset. This deviation is called the *generator loss*. This feedback from the discriminator is used by the generator to incrementally get better at creating realistic output.

### Discriminator

- As the generator gets better at creating music accompaniments, it begins fooling the discriminator. So, the discriminator needs to be retrained as well. The discriminator measures the *discriminator loss* to evaluate how well it is differentiating between real and fake data.

## AR-CNN

2D image can be used to represent music. AR-CNN generates output music iteratively over time.

An edit event is when a note is either added or removed from your input track during inference.