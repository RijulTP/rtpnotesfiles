# *Deep-Learning-Module-2-Important-Topics-PYQs*

> [!question] For more notes visit 
> https://rtpnotes.vercel.app
```table-of-contents
```

## *1. A supervised learning problem is given to model a deep feed forward neural network. Suggest solutions for a small sized dataset for training.*

---

## *2. Explain how L2 regularization improves the performance of deep feed forward neural networks.*

---

## 3. Explain any two parameter initialization methods.

---
## 4. Compare L1 and L2 regularization.

---
## 5. What is meant by Data augmentation? List down the benefits of it.

- **Data augmentation** is a technique used in machine learning where we artificially increase the size of a dataset by making small changes to the existing data.4
- The idea is to create new data points by modifying the original data, which can help the model learn better and avoid overfitting (where the model memorizes the training data rather than generalizing to new, unseen data).

### Key Concept:
- **Augmented data**: Modified versions of the original data (e.g., flipping, rotating images).
- **Synthetic data**: New data that is generated without using the original data
- Data augmentation is not limited to images. It can also be used for **text**, **audio**, and **video** data.
### Why Use Data Augmentation?
Here are some **benefits** of using data augmentation
1. **Prevents Overfitting**: By artificially increasing the dataset size, the model sees more variations of the data, which helps it generalize better and not memorize the training data.
2. **Improves Model Accuracy**: With more diverse data, the model can learn to handle more situations and can become more accurate when making predictions.
3. **Helps with Small Datasets**: When you don't have enough data to train a good model, data augmentation helps by providing more examples.
4. **Reduces Cost of Labeling Data**: Instead of manually creating new labeled data, you can modify existing data and still use it for training.

---
## 6. Describe Early stopping in neural network training.

**Early stopping** is a technique used in training neural networks to prevent overfitting (where the model becomes too specialized in the training data and fails to generalize to new, unseen data). It helps by stopping the training process before the model starts to overfit.

### How Does Early Stopping Work?

1. **Training and Validation Split**: When training a model, we split the data into two parts:
    - **Training data**: The data used to train the model.
    - **Validation data**: The data that the model has not seen during training. We use this to check how well the model is performing on new data.
2. **Training the Model**: We begin training the neural network on the training data. During the training process, the model's performance is evaluated on both the training data and the validation data.
3. **Monitoring Performance**:
    - **Training error**: This tells us how well the model is fitting the training data.
    - **Validation error**: This tells us how well the model is performing on unseen data (the validation data).
4. **When to Stop**: Initially, as the model trains, both training and validation errors decrease, meaning the model is improving. But at some point, the model might start to "memorize" the training data, and the validation error begins to increase even though the training error keeps decreasing. This is a sign of **overfitting**.
    - **Early stopping** kicks in at the point where the validation error is the lowest. This is the **optimal point** where the model performs best on unseen data.
5. **Stopping the Training**: When the validation error starts increasing, it indicates that the model is overfitting. At this point, we stop the training, even if the training error is still decreasing.

### Visualizing Early Stopping:
![[Pasted image 20250423040527.png]]
Think of the training process as a graph with two lines:
- **Training error (blue line)**: This line keeps going down as the model improves on the training data.
- **Validation error (red line)**: This line goes down initially as the model improves on unseen data, but at some point, it starts to go up because the model starts overfitting the training data.
The **early stopping point** is the point where the validation error is at its **lowest**, just before it starts to increase again.


---
## 7. Differentiate stochastic gradient descent with and without momentum. Give equations for weight updation in SGD with and without momentum.



---
## 8. State how to apply early stopping in the context of learning using Gradient Descent. Why is it necessary to use a validation set (instead of simply using the test set) when using early stopping?
---
## 9. Describe the effect in bias and variance when a neural network is modified with more number of hidden units followed with dropout regularization.
---
## 10. Describe the advantage of using Adam optimizer instead of basic gradient descent.


---
## 11. Explain different gradient descent optimization strategies used in deep learning.


---
## 12. Explain the following. i)Early stopping ii) Drop out iii) Injecting noise at input iv)Parameter sharing and tying.
---
## 13. Discuss how the Gradient descent algorithm finds the values of the weight that minimizes the error function?
---
## 14. Which optimization technique can be used to solve the problems caused by constant learning rate in Gradient descent algorithms? Explain the method
---
## 15. Derive a mathematical expression to show L2 regularization as weight decay. Explain how L2 regularization improves the performance of deep feed forward neural networks.
---
## 16. Differentiate between gradient descent with and without momentum. Give equations for updating weights in GD with and without momentum.

