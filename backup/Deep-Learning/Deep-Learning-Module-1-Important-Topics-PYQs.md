#  Deep-Learning-Module-1-Important-Topics-PYQs

> [!question] For more notes visit 
> https://rtpnotes.vercel.app
```table-of-contents
```
## *1. Discuss methods to prevent overfitting in neural networks.*

Imagine you're preparing for an exam by **memorizing every question from last year**. You ace those questions — but when a **new question** appears on the real test, you **struggle**.

That’s exactly what overfitting is.

> In neural networks, **overfitting** happens when a model learns the training data _too well_, including its **noise**, **errors**, or **quirks** — and fails to perform well on new, unseen data.


### Ways to **Prevent Overfitting**

### **1. Regularization**
Think of this as telling the model:

> “Hey, don’t go crazy trying to fit everything perfectly. Keep it simple.”

It works by **adding a penalty** when the model becomes too complex (uses too many big numbers). So the model is **forced to keep things small and simple**.
Example: If weights in the network grow too large, regularization pushes them down.

### 2️. **Train on More Data**
The more examples you give the model, the better it can understand **what’s common** and **what’s just noise**.

> More data = better learning + less memorizing.

You’re helping the model **see a bigger picture**.

### 3. **Data Augmentation** (for image data)
If you don’t have more images, create _new ones_ by tweaking the existing ones!
How?
- Flip the image horizontally or vertically    
- Rotate it slightly
- Zoom in or crop it
- Change brightness a bit

Now your model sees **many versions** of the same object — it learns to focus on **what really matters**, not just memorized pixel positions.

### 4.**Early Stopping**
When training a model, it keeps improving on training data… but after a while, it starts to get **worse on validation data** (data it hasn’t seen before). That’s when overfitting begins.

Early stopping says:
> “Stop training right before the model starts overfitting.”

So we **monitor performance**, and **stop at the best point** — not the last point.

### 5️. **Ensemble Methods**
Imagine asking **many different models** to vote on the answer instead of relying on just one.
It’s like asking 10 students to solve a question and going with the **majority answer** — more reliable than just one person.

---

## *2. A 3-dimensional input X = (X1, X2, X3) = (1, 2, 1) is fully connected to 1 neuron which is in the hidden layer with binary sigmoid activation function. Calculate the output of the hidden layer neuron. Assume associated weights. Neglect bias term.*

- We have input
	- ![[Pasted image 20250423032711.png]]
- Activation function
	- Binary sigmoid, which will squash the output between 0 and 1
- Assume weights
	- ![[Pasted image 20250423032838.png]]
- Compute weighted sum
	- ![[Pasted image 20250423032904.png]]
- Apply sigmoid
	- ![[Pasted image 20250423032933.png]]
	- ![[Pasted image 20250423032943.png]]
- Final answer we get 0.222

---


## *3. Discuss the disadvantages of single layer perceptrons with an example.*

Imagine a **single-layer perceptron** as a basic decision-making machine — kind of like a simple yes/no filter.
- It takes **input numbers** (like features of a thing — e.g., height, weight),
- Multiplies them by **weights** (importance),
- Adds them up,
- Passes the result through a function (like a brain saying “yes” if it's big enough, or “no” if it's not),
- And gives an **output** — like a “yes” or “no”.

### What It's Good At
- If the problem is **simple**, like separating apples and oranges **based on size** and **color**, and you can draw a **straight line** to separate them on a graph, then a single-layer perceptron works great.
- This is called a **linearly separable problem**.

### Disadvantage

### Linearly seperable problem
A **single-layer perceptron** **can only solve problems where the data can be split by a straight line**. It **cannot handle** more complex patterns.

![[Pasted image 20250423033414.png]]

|Input 1 (x)|Input 2 (y)|Output|
|---|---|---|
|0|0|0 ❌|
|0|1|1 ✅|
|1|0|1 ✅|
|1|1|0 ❌|

**Plotting**
(0,1) ✅   (1,1) ❌
(0,0) ❌   (1,0) ✅

**Graph looks like**

y ↑
  |
1 |  ✅      ❌
  |
0 |  ❌   ✅
  +-------------
     0    1   → x

Can you draw **one straight line** to separate ✅ from ❌?

**Nope!** No matter how you draw it, a ✅ will always be on the wrong side. You’d need **more than one line**, or a **curve**, which a **single-layer perceptron cannot do**.



### **No Hidden Layers = No Deep Understanding**
There’s no in-between thinking. It just jumps from input to output — no extra processing or reasoning is possible.


---


## *4. List any three applications of neural network.*

### **1. Computer Vision (Seeing like humans)**
Neural networks can look at images and **understand** what’s inside — just like we do with our eyes.
- **Image Classification**: Like telling if a picture is of a cat or a dog.
- **Object Detection**: Not just seeing a dog, but pointing exactly _where_ in the picture the dog is.
- **Facial Recognition**: Unlocking your phone using your face.
- **Medical Imaging**: Doctors use it to find issues in X-rays or MRIs (like tumors).
- **Image Segmentation**: Splitting an image into different parts, like separating the background from a person.
    
### **2. Natural Language Processing (Understanding language)**
This is how machines read, write, and talk — understanding human language.
- **Language Translation**: Turning English into Spanish, or vice versa — like Google Translate.
- **Text Summarization**: Shortening a long article into a few lines.
- **Speech Recognition**: Turning spoken words into text — think Alexa or Siri.
- **Chatbots**: Talking to you like a human — customer support, virtual assistants, etc.

### **3. Healthcare (Helping doctors and patients)**
Neural networks help save lives by spotting patterns in medical data
- **Disease Prediction**: Finding early signs of illnesses like cancer or diabetes.
- **Drug Discovery**: Helping scientists find new medicines faster.
- **Patient Monitoring**: Wearables like smartwatches track your heart rate, and AIs analyze that data.
- **Personalized Medicine**: Recommending treatments based on your unique health history.
### **4. Robotics (Making smarter robots)**
Robots powered by neural networks can _see_, _think_, and _move_ better.
- **Computer Vision in Robots**: A robot recognizing and picking up a banana.
- **Path Planning**: Drones or delivery robots finding the best route to a destination.
- **Human-Robot Interaction**: Robots understanding your gestures or voice commands
### **5. Social Media (Making platforms smarter)**

Behind the scenes, neural networks help improve our social media experience.
- **Content Moderation**: Removing harmful content (like hate speech or fake news).
- **Sentiment Analysis**: Figuring out if people are happy or angry from their posts.
- **User Engagement Optimization**: Suggesting posts or ads you might like (like Instagram or TikTok algorithms).
    
---
## *5. Describe the role of hidden layers in neural networks.*


In a neural network, the **hidden layers** play a critical role in transforming the input data into useful information that can lead to a correct output.
### **What are Hidden Layers?**
- Hidden layers are the layers in a neural network **between** the input layer and the output layer.
- They are called "hidden" because they are not directly exposed to the input data or the final output; instead, they work behind the scenes to process the information.

### **How Do Hidden Layers Work?**
1. **Input Layer**: The data is fed into the network through the input layer (e.g., an image, a text, etc.).
2. **Hidden Layers**: These layers take the input and process it:
    - The data is transformed by **weights** (which are adjustable parameters) and **activation functions** (which determine if the neuron should be activated).    
    - Each hidden layer applies a mathematical operation on the input data, extracting important patterns and features.    
3. **Output Layer**: After passing through the hidden layers, the data reaches the output layer, where the final prediction or classification is made.

### **Role of Hidden Layers:**
1. **Feature Extraction**:
    - The hidden layers learn **features** (patterns) from the data. For example, in image recognition, the first hidden layer might learn to detect simple edges, while deeper layers learn complex shapes and objects.  
2. **Non-linear Transformation**:
    - The activation functions in the hidden layers (like **ReLU**, **sigmoid**, etc.) add **non-linearity** to the model, allowing it to learn complex, non-linear relationships in the data. Without this, the model would only learn linear relationships, which is limited.
3. **Pattern Representation**:
    - Each hidden layer represents a more **abstract** view of the input data. The first layer might focus on basic patterns (like edges), while deeper layers might represent more abstract concepts (like faces, animals, or even specific actions).    
4. **Improved Generalization**:
    - Hidden layers allow the model to generalize better on unseen data. They help the model understand the underlying structure of the data, rather than just memorizing specific examples (this is called **overfitting** prevention).

---

## *6. Calculate the output Y of a three input neuron with bias.The input feature vector is (x1,x2,x3) = (0.8,0.6,0.2) and weight values are [w1,w2,w3] = [0.2,0.1,-0.3] and Bias is 0.25.Use Binary Sigmoid as the activation function.*

---

## *7. Draw the architecture of a multi-layer perceptron. Derive update rules for parameters in the multi-layer neural network through the gradient descent.*


---

## *8. Describe various activation functions used in neural networks.*

### **What Are Activation Functions?**
Imagine a light switch. When you flip it, the light turns on or off. An **activation function** in a neural network works kind of like that switch—it decides if a neuron should "fire" (activate) or not based on the input it gets.

But it’s not just an on/off switch. Sometimes, it lets signals through in varying strengths, like dimming a light instead of just turning it on or off.

### **Why Do We Use Activation Functions?**
Without activation functions, a neural network would just be doing simple math, like adding and multiplying. This would make it **impossible to learn complex patterns** like recognizing faces, understanding speech, or predicting trends. Activation functions introduce **non-linearity**, allowing networks to solve more complex problems.

### **Types of Activation Functions**

#### 1. **Linear Activation Function (Identity Function)**
- **What it does:** It doesn’t really change the input. Whatever goes in, comes out the same.
- ![[Pasted image 20250210212738.png]]
- **Why it’s not great:** It can't handle complex data because it doesn't add any "twist" to the input. It treats everything in a straight line, making it **useless for learning complex patterns**.
#### 2. **Non-Linear Activation Functions**

These are the real stars because they help neural networks learn and handle complex data.

##### **a) Sigmoid (Logistic) Function**

- **Shape:** Looks like an **S**.
    ![[Pasted image 20250210212834.png]]
- **Why it’s useful:**  
    Perfect for **probability predictions**. If you want to predict whether something is **yes or no**, this is a good choice because outputs stay between 0 and 1 (like probability).
- **Problems:**  
    When the values are too high or too low, the function becomes really flat, and the network **stops learning**—this is called the **vanishing gradient problem**.

##### **b) Tanh (Hyperbolic Tangent) Function**
- **Shape:** Also **S-shaped**, but steeper.
- ![[Pasted image 20250210213037.png]]
- Range: -1 to 1
- **Why it’s better than Sigmoid:**  
    It centers the data around **zero**, which helps the model learn faster. Negative inputs become negative outputs, and positive inputs become positive outputs.
- **Problems:**  
    Still suffers from the **vanishing gradient problem**, though less than Sigmoid.
##### **c) ReLU (Rectified Linear Unit)**
- **Shape:** Looks like a **hockey stick**.
- ![[Pasted image 20250210213156.png]]
- Range: 0 to infinity
- **Why it’s super popular:**  
    It’s simple and works really well for deep learning models. **If the input is positive, it stays the same; if it’s negative, it turns into zero.** This makes computations fast and helps networks learn quickly.
- **Problems:**  
    Sometimes, if too many neurons output **zero** (because of negative inputs), the network might stop learning in those parts. This is known as the **dying ReLU problem**.

| **Activation Function** | **Range**              | **Good For**                                | **Problems**                         |
| ----------------------- | ---------------------- | ------------------------------------------- | ------------------------------------ |
| **Linear**              | −∞-\infty to +∞+\infty | Simple tasks (but rarely used)              | Can’t handle complex patterns        |
| **Sigmoid**             | 0 to 1                 | Binary classification, probabilities        | Vanishing gradient, slow learning    |
| **Tanh**                | -1 to 1                | Binary classification (better than Sigmoid) | Vanishing gradient (but less severe) |
| **ReLU**                | 0 to +∞+\infty         | Deep learning, CNNs                         | Dying ReLU (neurons stop learning)   |

Activation functions help neural networks learn and make decisions. **ReLU** is widely used today because of its simplicity and performance, while **Sigmoid** and **Tanh** are more suited for specific tasks like classification.


---

## *9. Calculate the output of the following neuron Y if the activation function is a bipolar sigmoid.*
![[Pasted image 20250416125109.png]]

---
## *10. Explain the importance of choosing the right step size in neural networks.*

Choosing the **right step size**, often called the **learning rate**, is crucial when training neural networks.

### What is the Step Size (Learning Rate)?
- The **step size** or **learning rate** controls how much the weights of the neural network are adjusted during each step of training.
- After computing the error (how far off the network's predictions are from the true values), the model adjusts its weights in the direction that reduces the error.
- The learning rate determines how big each weight update will be. If the step size is too large, the model might "jump" over the optimal solution. If it’s too small, the model might take too long to converge (find the solution).

### Why is Choosing the Right Learning Rate Important?
1. **Speed of Convergence**:
    - If the learning rate is too **large**, the network may **overshoot** the optimal solution during training. This means the weight updates might be so big that the network ends up bouncing around without finding the best solution.
        - Example: Imagine trying to reach a target by taking large steps. You might overshoot the target and never actually land on it.
    - If the learning rate is too **small**, the network may take **tiny steps**, which means it will take a very long time to converge to the optimal solution, or it might get stuck in a bad local minimum without ever reaching the best answer.
        - Example: If you take very tiny steps towards a goal, it will take a long time to reach it, and you might lose patience before you get there!
2. **Optimization Efficiency**:
    - A good learning rate helps the network learn efficiently by balancing between **too fast** (causing instability) and **too slow** (taking forever to learn).
    - Ideally, you want the model to converge **quickly** without bouncing all over the place. This ensures that the model learns the patterns in the data effectively without wasting computational resources.
3. **Stability of the Training Process**:
    - If the learning rate is too high, the training process can become unstable. The model might diverge, meaning the loss (the error in the predictions) keeps increasing instead of decreasing. This can happen if the updates to the weights are so large that the model cannot adjust properly.
    - If the learning rate is too low, the model might not make any significant progress, as each update is too small to make a difference.

---

## *12. Implement the back propagation algorithm to train Multi Layer Perceptron using tanh activation function.*

---
## *13. Compare the structure and features of Perceptron and Multilayer Perceptron with necessary diagrams. What are the draw backs of Perceptron?*


---


## *14. Discuss the advantages and disadvantages of using ReLU as an activation function in neural networks.*

### Advantages of ReLU:
1. **Simplicity**:
    - ReLU is very simple to compute, making it computationally efficient. It’s faster compared to other activation functions like sigmoid or tanh.    
2. **Avoids Vanishing Gradient Problem**:
    - The vanishing gradient problem happens when gradients (the values that help train the model) get too small, making it hard for the model to learn. ReLU helps avoid this problem because for positive inputs, the gradient is always **1** (which is useful for faster learning). 
3. **Sparsity**:
    - Since ReLU sets all negative values to zero, it naturally introduces sparsity. This means many neurons in the network will not fire (they produce zero output), which can lead to more efficient learning and a simpler model.    
4. **Faster Convergence**:
    - Due to its simplicity and directness, networks using ReLU tend to converge faster (reach an optimal solution) during training.    
5. **Easy to Implement**:
    - ReLU is easy to implement and doesn’t require much computational power, which makes it highly efficient for large models and datasets.

### Disadvantages of ReLU:
1. **Dead Neurons**:
    - One major problem with ReLU is that if the input is negative, the output is zero.
    - If a neuron receives only negative values in its inputs during training, it will always output zero, making it inactive (this is called a "dead neuron"). Once a neuron becomes inactive, it cannot learn, and this can hurt the network’s performance.
    - **Example**: If during training, a particular neuron gets negative values in all inputs, it will stop updating and become "dead." This means it won’t contribute to learning anymore.  
2. **Unbounded Output**:
    - ReLU has an output range from **0 to infinity**, meaning there is no upper limit on how large the output can be. This can cause the values to grow very large, leading to instability in training, especially if the learning rate is too high.
3. **Not Zero-Centered**:
    - The output of ReLU is always positive or zero. This can cause issues in certain cases because the activations are not zero-centered, which could slow down convergence in some scenarios. For example, when the inputs are positive and negative, the gradient descent updates can become uneven, leading to slower training.
4. **Exploding Gradients**:
    - While ReLU helps with vanishing gradients, it can sometimes lead to **exploding gradients**. This happens when large gradients accumulate, making the training process unstable.





