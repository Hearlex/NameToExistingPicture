# NameToExistingPicture
Attempt at selecting images often connected to specific names with neural networks
This was a project by Dániel Egyed and Alex Armand Hegedüs

## Detailed description
Let's say we have 'David'. David is a name that many different person can have and they all look mostly different. But what if we were searching for an avarage of those people. Could we find a picture for someone named David?

This is an attempt to create an Artificial Intelligence that can learn names and looks that might come with said name. A really great way to imagine this is to ask somebody what country could a person named Louise come from? There is a great chance they would say France. So this AI could follow the same logic, and choose a picture from somebody who was born in France.

## Neural Networks
Most of the time when we face a problem that is hardly describeable with mathematics we choose to work with Neural Networks as they can find patterns pretty easily. For this specific task we would like to try using an RNN (Recurrent Neural Network). The reason for this is that names are not bound by a 'character limit'. They can be as long or as short as they want to be. Because of this we don't know the size of the input.

RNNs have a problem though. They have a hard time with too large or too ambigous data like 250 times 250 pixels with 3 channels for each picture. A person can even have multiple pictures so how could we help the RNN learn all this? First we could lower the resolution. Then we could try to lower the size with another Neural Network:

We tried using an Autoencoder to create a key. This key is then used by the autoencoder to try to recreate the original image as much as possible, while the key remains a vector of around 256 floats in size. That is much smaller than the original picture.

## Conclusion
Although we lowered the information size, the problem wasn't solved. In the end, Recurrent Neural Networks even with the usage of multiple layers weren't complex enough to find any pattern in a task this hard.

If we are to find any success with this later on, we should try something that has a better memory like LSTM or Transformers.
