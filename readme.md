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

