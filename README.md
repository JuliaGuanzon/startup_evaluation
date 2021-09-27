<h1 align="center">Startup Evaluation Report</h1>

## Overview of the Evaluation Reports

As a venture capital firm, we want to see startup businesses succeed and we want to be able to assist in that success. The challenging part about investing in startup businesses is that it can be risky. There is no guaranteed recipe for success, and often times than not, businesses fail. With the help of the Startup Evaluation Report application, we can run an algorithm that can predict whether an applicant will be successful with help and funding from our firm.

## Results

<details>
<summary>Original Model</summary>
 
 
The Original Model scored 55.49% in loss and 72.96% in accuracy. 

 
 The model used scaled data. The Neural Network structure was cookie cutter, as in we pulled the number of inputs from the length of the data, our output neurons we equal to 1, we had 2 hidden layers of which were calculated using a standard calculation. The usage of the *relu* activation function was used for both hidden layers, and sigmoid used for the output as our final data should be binary.
    
```
nn.add(Dense(input_dim=number_input_features, units=hidden_nodes_layer1 , activation="relu"))
nn.add(Dense(units=hidden_nodes_layer2, activation="relu"))
nn.add(Dense(units=number_output_neurons, activation="sigmoid"))
```


</details>


<details>
<summary>Alternative Model 1</summary>
 
 
The Alternative Model 1 scored 55.32% in loss and 73.06% in accuracy.
 
 The model used scaled data, had a number of inputs equal to the the length of the data, 1 output neuron, and 4 hidden layers using *relu* with one using *sigmoid*. The nodes of the hidden layers were staggered descreasing by twenty.
    
```
nn_A1.add(Dense(input_dim=number_input_features, units=hidden_nodes_layer1_A1 , activation="relu"))
nn_A1.add(Dense(units=hidden_nodes_layer2_A1, activation="relu"))
nn_A1.add(Dense(units=hidden_nodes_layer3_A1, activation="relu"))
nn_A1.add(Dense(units=hidden_nodes_layer4_A1, activation="sigmoid"))
nn_A1.add(Dense(units=number_output_neurons_A1, activation="sigmoid"))
```
The model was fit by using 50 epochs.
</details>

<details>
<summary>Alternative Model 2</summary>


The Alternative Model 2 scored 55.25% in loss and 73.08% in accuracy.
 
The model used scaled data, had a number of inputs equal to the the length of the data, 1 output neuron, and 3 hidden layers using *relu*. The nodes of the hidden layers were decreased in large quantities. Originally, the idea was that more hidden layers might help, but it only made the loss percentage increase. The process to get the model down to the current score was trial and error.
 
```
nn_A2.add(Dense(input_dim=number_input_features, units=hidden_nodes_layer1_A2 , activation="relu"))

nn_A2.add(Dense(units=hidden_nodes_layer2_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer3_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer4_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer5_A2, activation="relu"))
nn_A2.add(Dense(units=hidden_nodes_layer6_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer7_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer8_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer9_A2, activation="sigmoid"))
# nn_A2.add(Dense(units=hidden_nodes_layer10_A2, activation="relu"))
# nn_A2.add(Dense(units=hidden_nodes_layer11_A2, activation="sigmoid"))

nn_A2.add(Dense(units=number_output_neurons_A2, activation="sigmoid"))
```

</details>

## Summary

The data had been fit as much as it can be after testing. The best score any data can acheive is 1, but the issue with that is it would most likely be imperfect. High scores mean a model is overfitted. Therefore, a score of .73 is a moderately good score as it is less than 1, but greater than 0.60. This model is ready to be used to evaluate startups.

