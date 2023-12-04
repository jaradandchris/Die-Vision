#### High-level points to cover -
1. start out by describing the problem and why you care about it (detecting numbers on rolled die, d4-d20, different from traditional die, use for D&D game)  
2. research phase - dug into research papers that solve similar problems, talked to people about CV and ML.  Pure CV-based approach would have involved using traditional CV algorithms to first detect the bounding boxes for individual die, then try parse the number inside the bounding box. this might make it hard to handle cases where multiple faces of the die are visible, since now your algorithm needs to detect which is the "top" face, and that is hard. Decided to use a neural network, since there was a research paper that showed promising results on a very similar task (i've forgotten what this was).

3. next step: finding data to train a neural network.  I've forgotten the exact journey we went through here, but it'd be good to have some detail - some manual data annotation? only d20, no d4 / d3 / other die?4. the dataset we had was a few hundred/thousand images.  
4. neural networks usually need more data to train from scratch  most image classification tasks use pre-trained networks, since they share similar characteristics, and a lot of the learning is transferable.
5. pre-trained neural network - fine tuned it on your dice dataset (basically, initialized the network from the pre-trained model, and then trained it on your dataset) might be good to do a quick trial run through the notebook so you get a feel for the steps.
6. metrics to measure performance accuracy, precision, recall and f1_score are the most common ones the ML problem we have is a multi-class classification problem (as opposed to a binary classification problem, or a regression problem) the dataset is fairly balanced (all classes - the number on the die -  have roughly equal representation in the dataset)  
7. went with accuracy since that's easy to interpret  
8. plotted confusion matrix to understand - [https://www.analyticsvidhya.com/blog/2021/06/confusion-matrix-for-multi-class-classification/](https://www.analyticsvidhya.com/blog/2021/06/confusion-matrix-for-multi-class-classification/) what kind of accuracy you got on the test data
9. cross-validation / train-test split / other experiments you tried some experiments on hyper-parameters you tried to tune using cross-validation significant lift in accuracy? not so significant?
#### Other guidelines
11. I'd read up about the terminology if there's things you're not very sure about  
12. It's totally okay to say you don't know everything - most ML practitioners don't always know nitty-gritty details, and its totally okay to say you're still learning.  
13. Doing a trial run through the notebook would be good to get a feel for the steps. (edited) 
