# RNN
Before jumping into what a RNN is we  should undersand what temporal dependency is

## Temporal Dependency
Basically temporal dependency are functions that depend on time.

Say that you are looking at the picture of a dog, the dog might be running standing etc.... the state of the dog depends on time and hence it can be termed as a temporal dependency.

RNNs are neural networks which have temporal depedencies it has knowledge not only about the new dataset it sees by also about previous dataset that it has already seen.
RNNs have memory associated with it which would give it knowledge about the previous information it has learned when it is provided a dataset.

RNNs were inspired modeled loosly on how the human brain works.

Practically RNNs show good performance in time-series datas.

## _Reflection_

Let us look back into some of the things that we already know before we dive into RNNs

### Neural Networks 

Neural Networks are basically non-linear function aproximators.

In building a supervised neural network we basically have two steps.
* Training 
* Evalutaion

In training phase we are given the training set of data and our algoritiam basically itertates to find the best set of weights which would give our desired output. Which meas if we have the same input and same weights traditionally we should get the same output becuase the output function here only depends on input and weights. 

In the Evaluation phase we would have a test dataset and these datasets are given as input to the neural network and we expect to get the output for the same. 

During the training of a network we primarly focus on feedfoward and backpropogation.

#### feedfoward

This is basically inputing the data to the network so that it can make a prediction

once the network has made a prediction we can figure out the error by taking the predicted output and since we are doing supervised learning take the actual output and predcit what amount of error is involved and then we need to do backpropogation.

#### backpropogation

In this step we will go back a step from feedfoward and use the calculated output to adjust the weights so that in the next iteration we get a prediciton what we require.

## RNNs

The principle behnind RNNs are very similar to those of FeedFowardNetwork but there are two main key differences

For an RNN in the training phase it uses

* Sequences as training inputs
* Memory elements are involved



![The-standard-RNN-and-unfolded-RNN](https://user-images.githubusercontent.com/43090559/82646483-4baabd00-9c32-11ea-86d3-167e0951044b.png)

#### _RNN_ diagram
![mlp-diagram](https://user-images.githubusercontent.com/43090559/82646531-5ebd8d00-9c32-11ea-98ed-d45b67c29c48.jpg)

#### _feed foward network_ diagram
#### Memory
Memory is the output of the hidden node which would act as additional inputs to the network during the next training phase.

In a feedfoward network the output y depends only on the input and weights but this is not the case when it comes to RNNs here the output not only depends on the weights and input but also on the previous _State_ and _State_ Weights.

##### State

This is a term used when there is memory involved in a neural network.

If you look at the diagram above an RNN can be represented as Folded and Unfolded network

In the folded part there is an input X from which a function U is mapped to hidden layer h from which the state. Basicaly this gives us an outline of the network but as we know for RNNs have temporal dependencies so we need to take into account factor for time so in order to visualise this we have the unfolded network which is seen on the right of the network. here we can understand that the at h(t) the the we can see that it depends on the output of h(t-1) as well as its weights.

Similar to Neural Networks RNNs can also be stacked up one by one on top of each other to make a more deeper network.

### Genereal Explanation

Lets us see how we can use a rnn in real world, as I have said earlier RNNs are very good at predicting pattens so we mostly train rnns to do the same. Let us say we need to train a rnn to dectect the word bravo. (This is just an example)

First we need to do one-hot encoding for this which basically means-

b 00001

r 00010

a 00100

v 01000

o 10000

And we would create a neural netowrk which would be feed random words over time and whenever this seriese is encountered it would output a value close to 1.

But now the question arises on how do we actually train this network for that we need to follow backpopogation.

## Backpropogation through time

Basically, inorder to do backpropogation throught time we need to take into account all previous timesteps.

Let us look at the folded model above in this step we need to consider three weights that has to be updated

1. The input weights
1. The weights of the state.
1. The weights connecting one state to the other.


[Take a look here to understand the math behind backpropogation throught time.](https://d2l.ai/chapter_recurrent-neural-networks/bptt.html)

Now that we know about backpropogation we might be thinking can we use this in case we have a very large rnn No we can't similar to normal MLP's here also we will have vanishing gradient problem so what do we do we cannot use the solutions of MLP here, For this we use LSTM cells.
Long Short Term Memory cells.

Unlike Normal RNNs LSTMs are fully differentiable and hence we easily backpropogate throught it, it also latches on some information and have filters of what information to hold hence avoiding vanishing gradient.

