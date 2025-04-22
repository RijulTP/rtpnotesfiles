# *Deep-Learning-Module-3-Important-Topics-PYQs*
> [!question] For more notes visit 
> https://rtpnotes.vercel.app

```table-of-contents
```

## *1. Assume an input volume of dimension 64 x 64 x 3. What are the dimensions of the resulting volume after convolving a 5 x 5 kernel with zero padding, stride of 1 and 2 filters?*

- You’re given an **input image** of size:
	- 📏 64 × 64 pixels, with **3 color channels** (like Red, Green, Blue)
- You are **using a filter** (like a small window) of size:
	- 🔲 5 × 5 (this filter slides over the image to detect patterns)
- You’re told:
	- **No padding** (which means we don't add any extra border around the image)
	- **Stride of 1** (the filter moves 1 step at a time)
	- **2 filters** are used (that means we get 2 different output images)
### What does convolution do?
Think of a **magnifying glass** sliding over a photo. It looks at a small 5x5 part of the image, finds some features (like edges), and writes down a number. Then it moves one step forward and repeats this.

Doing this for the whole image gives you a **new smaller image** that contains special information — like edges, colors, or shapes.

### Calculate
- Formula to get the size of result
	- ![[Pasted image 20250423022646.png]]
	- ![[Pasted image 20250423022747.png]]
- Now, because we have **2 filters**, we get **2 output images** → so the depth = 2.
- Answer
	- ![[Pasted image 20250423022809.png]]



---

## *2. Give two benefits of using convolutional layers instead of fully connected ones for visual tasks.*

### **What is a Convolutional Layer?**
Imagine you are looking at an image. An image is made up of pixels (little tiny dots of color). A **convolutional layer** is a special type of layer used in **Convolutional Neural Networks (CNNs)**, which are great for tasks like recognizing objects in images.

#### Here's how it works:
- Think of the **convolutional layer** as a **small window** (called a **filter** or **kernel**) that moves across the image.
- This window looks at small pieces of the image at a time, one section at a time (like looking at a small part of a picture to focus on details).
- The filter slides over the image and looks for patterns like **edges, textures, or shapes**. It's good at picking up simple features that can help identify what’s in the image.
For example, in a picture of a cat, a convolutional layer might first find simple features like the edges of the cat's ears, the outline of its body, etc.


### **What is a Fully Connected Layer?**
A **fully connected layer** is a simpler type of layer that connects every neuron (a small decision-making unit) to every other neuron in the next layer.
#### Here’s how it works:
- Imagine a layer with **100 neurons**. In a **fully connected layer**, each of those 100 neurons is connected to all the neurons in the next layer. It's like each neuron is talking to every other neuron, which can be helpful but also a bit too much for image tasks.
- This type of layer **looks at the whole image** and tries to make decisions based on all the pixels together.
However, for image recognition, it's not always ideal because:
- It doesn’t focus on **local features** (like edges and corners).
- It connects **everything to everything**, which leads to **a lot of unnecessary connections** and makes the network **slow to train**.


### **Why Do We Use Convolutional Layers for Visual Tasks?**
Now that we know what both layers do, here’s why **convolutional layers** are better for visual tasks:
- **Efficiency**: Convolutional layers only look at small parts of the image at a time, making them faster and more efficient than fully connected layers.
- **Focus on important details**: They are great at detecting **patterns** like edges, textures, or shapes, which are really important for recognizing objects in images.
In short:
- **Convolutional layers** are designed for tasks where we need to look at small patterns in images.
- **Fully connected layers** are good for general tasks but aren't great at focusing on small image details.

---

## *3. Define structured outputs in Convolutional Neural networks.*

In Convolutional Neural Networks (CNNs), **structured outputs** mean that instead of just predicting one label for an entire image (like "cat" or "dog"), the network can give more detailed results. For example, it might predict what each pixel in the image represents, like labeling every pixel as either "cat," "dog," or "background."

### Example: Pixel-wise labeling
In tasks like **semantic segmentation**, the goal is to label each pixel of an image. Instead of just saying what the whole image is (like "cat"), the network looks at every single pixel and says, "This pixel is a cat," "That pixel is the background," etc.

So, the network’s output could be a map where each position in the map shows the probability that a pixel belongs to a particular category. For example, for an image of a cat, the network would output something that says, "The pixel at position (2, 3) is a cat, the pixel at (10, 5) is background," and so on.

### Problem: Output Size
When you try to do tasks like this, one problem is that the output might be smaller than the original image after passing through the network. This happens because some parts of the network, like **pooling layers** , shrink the image.

To solve this, there are a few ways to handle it:
1. **Avoid pooling layers** – Don't shrink the image at all, which helps keep the size the same.
2. **Reduce the number of labels** – Instead of labeling every pixel, label fewer points, which reduces the output size.
3. **Use pooling with a stride of 1** – Pooling still happens, but it’s done gently, so the size doesn’t shrink too much.
    


---
## *4. Suggest a method to make convolution algorithm more efficient. Justify Your answer.*

### Convolution Operations 
Imagine you're trying to look at an image to figure out patterns (like detecting edges, shapes, etc.). Convolution is like sliding a small filter (called a **kernel**) over the image to look at different parts of it at once and figure out these patterns.

But, sometimes these calculations can be slow, especially when the image is large or the filter is big. So, **how can we speed this up?**

### 1. **Parallel Computation Resources (Using Multiple Cores or GPUs)**
- **What is parallel computation?**
    - Think of it like having many workers doing the same job at the same time.
    - For example, if you have to add up numbers, instead of one person adding them all up one by one, you can split the work, and different people can add parts of the numbers at the same time.
    - This is what **parallel computation** does—it splits the work so that many processors (like the cores of a CPU or a **GPU**) can work on the problem at once.
    - **Why is this helpful?**
        - **Convolution** involves a lot of repetitive tasks (especially for large images), so if we use a **GPU** (which is designed to handle many tasks at once), we can perform these tasks much faster than if we were using a single CPU core.
### 2. **Fourier Transform (FFT)**
- **What is the Fourier Transform?**
    - The Fourier transform is a **math tool** that changes the way we look at the data. Instead of looking at the image as a whole, it helps us break it down into simpler patterns (like waves). Once we have these simpler patterns, it's easier to perform some calculations (like convolution) on them.
    - **How does it help in speeding up convolution?**
        - Normally, convolution can be slow because it involves comparing each pixel in the image with every part of the filter. But using **Fourier Transform**, we can turn this process into a simpler multiplication. After that, we just convert the results back to get the final image, which is **faster**.
### 3. **Separable Kernels**
- **What is a separable kernel?**
    - Imagine a **2D filter (or kernel)** that looks at an area of the image in a grid-like way (like a small box). Normally, you have to go through every single part of the filter to perform the convolution.
    - But if the filter is **separable**, that means we can break it down into **two smaller filters** (1D filters) that are easier to work with.
- **Why is it faster?**
    - Instead of doing a big, complex operation with a 2D filter, you can break it into two smaller, easier-to-handle 1D operations. This reduces the amount of work you need to do, making it **faster** to compute.
---
## *5. Why Zero padding is used in CNN? List the different types of Zero padding techniques used.*

Imagine you’re looking at a picture (or an image) and you want to apply a filter (a small box, called a **kernel**) to detect things like edges or shapes. The filter moves over the image, looking at small sections, and produces an output based on what it sees.

![[Pasted image 20250423024932.png]]
However, when this filter moves near the edges of the image, it doesn’t have enough surrounding pixels to work with. For example, if the filter is 3x3 (a small 3x3 grid), when it reaches the edges of the image, it doesn’t have pixels outside the image to help process that section properly. This can lead to important details being lost near the edges.

**Zero padding** solves this problem by adding extra pixels with a value of 0 around the image, so the filter has enough space to process even the edges properly.

### Why Use Zero Padding in CNN?
1. **Keeps the Image Size Consistent**:  
	1. One of the main reasons for zero padding is to **keep the size of the output the same as the input size**.
	2. Without padding, applying the filter (kernel) will reduce the size of the image because the filter can only move over valid parts of the image (not the edges).
	3. Zero padding adds extra pixels so that after applying the filter, the output image has the same width and height as the input.
2. **Helps with Edge Information**:  
    Padding ensures that the edges of the image get the same attention as the middle. It’s like giving more space to the filter when it’s working on the edges, ensuring that no information is missed.
3. **Improves Performance**:  
    By using padding, the network can better understand features at the borders of the image, which can lead to better overall performance in detecting patterns and objects.

### Types of Zero Padding Techniques
There are a few different ways zero padding is used, each with specific goals:
#### 1. **Valid Padding (No Padding)**
- **What it is**: In this case, no extra pixels are added around the image. The filter only slides over the **valid** parts of the image (where it can fully fit).
- **Effect**: This reduces the size of the output image after applying the filter.
- **Example**: If you have a 5x5 image and you apply a 3x3 filter, the output will be a 3x3 image, as the filter can’t slide over the edges.
#### 2. **Same Padding**
- **What it is**: This method adds enough zeros around the image so that the output image has the **same size** as the input image. This is the most common padding technique.
- **Effect**: The image stays the same size after applying the filter.
- **Example**: If you have a 5x5 image and apply a 3x3 filter, padding will be added to keep the result a 5x5 image.
    
#### 3. **Full Padding**
- **What it is**: This is where padding is applied around the entire image to make sure that every part of the image can be processed by the filter. It results in a larger output image than the input.
- **Effect**: The image will increase in size after padding is applied and the filter is used.
- **Example**: If you have a 5x5 image and apply a 3x3 filter, the output could be a larger image, such as 7x7, because of the added padding.

---
## *6. What is the benefit of using Pooling layer in CNN?*

In Convolutional Neural Networks (CNNs), **pooling** is a technique that helps to make the model work faster and better by reducing the size of the data it has to process. Imagine you have a photo, and you want to identify important features like edges, shapes, or corners, but you don't need to remember every small detail of the image.

A **pooling layer** helps by summarizing the image data into smaller chunks, focusing on the most important parts. It's like looking at the bigger picture, not every tiny detail.

### Benefits of Using Pooling Layers:
1. **Reduces the Size of the Data**:  
    Pooling helps reduce the **dimensions** (width and height) of the image data. This means the model has less information to process, which speeds up the training and prediction process.
2. **Prevents Overfitting**:  
    By reducing the size of the data, pooling also helps **prevent overfitting**. Overfitting happens when the model learns too many details from the training data and performs poorly on new data. Pooling helps avoid this by focusing on the most important features.
3. **Keeps Important Features**:  
    Pooling helps in **selecting the important parts of the image**. It chooses the most prominent features, like edges and corners, which are important for recognizing objects.
4. **Helps with Position Changes**:  
    Pooling helps make the model **more robust to small changes in the position** of objects in the image. For example, if an object moves slightly in the image, the pooling layer helps the model recognize it even if its position changes.

---
## *7. Draw and explain the architecture of convolutional neural networks.*

Imagine you have an image, like a photo of a cat, and you want a computer to recognize it. A Convolutional Neural Network (CNN) is a special type of model that helps the computer understand images, by breaking down the image into smaller parts, looking at patterns, and then making a decision about what the image represents.


### CNN Architecture: The Layers of a CNN

![[Pasted image 20250423025756.png]]
Think of a CNN as a series of layers stacked on top of each other. Each layer helps the model understand different aspects of the image. Here are the main layers that make up the CNN:
### 1. **Input Layer**:
- **What it is**: This is the first layer where we give the image to the model.
- **What it does**: It holds the raw image data. For example, if you have an image of size 32x32 pixels with 3 color channels (Red, Green, and Blue), this layer will hold that image.
- **Example**: If your image is 32 pixels wide, 32 pixels tall, and has 3 color channels, the input layer has the shape (32x32x3).
### 2. **Convolutional Layers**:
- **What it is**: This layer applies small filters (like tiny windows) to the image to look for important features like edges, textures, or shapes.
- **What it does**: It "slides" a filter over the image and looks for specific patterns. The filter detects features like lines or corners in the image.
- **How it works**: The filter looks at small sections of the image and performs some calculations, like multiplying the values in the filter with the values in the image, to find patterns.
- **Example**: If we use 12 filters in this layer, we get a feature map (or output) showing how each of the filters responded to different parts of the image. The output size can be 32x32x12 (12 channels for 12 different filters).
    

### 3. **Activation Layer (ReLU)**:
- **What it is**: After the convolution layer, we add an activation function.
- **What it does**: It adds non-linearity to the model. In simple terms, it allows the model to learn more complex patterns. The most common activation function used is called **ReLU** (Rectified Linear Unit), which simply changes all negative values to zero.
- **Example**: If the output from the convolution layer is [-2, 3, -1, 5], ReLU will change it to [0, 3, 0, 5], making all negative values zero.
### 4. **Pooling Layer**:
- **What it is**: The pooling layer reduces the size of the image (or feature map), making the network faster and more efficient.
- **What it does**: It looks at small regions of the image and reduces them to a single value. The most common types are:
    - **Max Pooling**: Picks the largest value in the region.
    - **Average Pooling**: Takes the average of the values in the region.
- **Why it's important**: Pooling reduces the amount of data, so the network can focus on the most important features.
- **Example**: If you apply max pooling with a 2x2 filter (looking at 2x2 sections of the image) and a stride of 2 (how much you move the filter), you will end up with an image that's half the size. So, if the feature map was 32x32x12, after pooling it might become 16x16x12.
### 5. **Flattening**:
- **What it is**: After convolution and pooling, the feature map is turned into a single long vector.
- **What it does**: This step "flattens" the multi-dimensional feature map into a one-dimensional vector, so it can be fed into the fully connected layers.
- **Example**: If the pooled feature map was 16x16x12, it would be flattened into a 1D vector of size 16_16_12 = 3072.
### 6. **Fully Connected Layers**
- **What it is**: These layers are the traditional neural network layers that connect every neuron from the previous layer to every neuron in the next layer.
- **What it does**: The fully connected layers use the features from the previous layers (after flattening) to make predictions or classifications.
- **Example**: After flattening, the model uses fully connected layers to decide if the image represents a cat, dog, or some other object.
### 7. **Output Layer**:
- **What it is**: This is the final layer that gives the result of the network's classification.
- **What it does**: It provides the final output, which is the prediction. If it's a classification task (e.g., recognizing a cat), it outputs the probability of each class.
- **Example**: If you have 3 classes (cat, dog, and bird), the output layer will give a probability for each class. It might output [0.8, 0.1, 0.1], meaning the model is 80% sure it's a cat.

----
## *8. Explain how CNN produce structured output.*

CNNs produce structured output using a series of **specialized layers** that are designed to handle more detailed information from the input image. Let’s look at a couple of examples:

#### **Example 1: Semantic Segmentation (Pixel-wise Classification)**
In tasks like **semantic segmentation**, CNNs are used to label **every single pixel** in an image. The goal is to classify each pixel as belonging to a certain category. For example, in an image of a street scene, some pixels might belong to "sky", some to "buildings", some to "cars", and others to "roads". Each pixel gets a label based on its class.

- **How it works**:
    - The CNN uses convolutional layers to extract features (like edges or textures) from the image.
    - After that, the CNN applies **deconvolution** or **upsampling** to bring the feature maps back to the original image size.
    - **Softmax function** is applied on each pixel, which gives a probability of that pixel belonging to each class (like "sky", "building", "road", etc.).
    - **Output**: The result is an image with the same size as the input, but with each pixel labeled with a class (e.g., [0: background, 1: sky, 2: road]).

#### **Example 2: Object Detection (Bounding Boxes)**

In **object detection**, the CNN is tasked with identifying the locations of objects in the image and drawing bounding boxes around them. Each bounding box is associated with a label (e.g., "cat", "dog") and a probability score.

- **How it works**:
    - The CNN uses convolutional layers to find important features like edges and shapes of objects in the image.
    - After detecting objects, the CNN generates a **set of bounding boxes** (coordinates for each box) and assigns a label and probability to each box (like "cat" with 95% confidence).
    - **Output**: The result is a list of bounding boxes along with labels and confidence scores (e.g., “cat” in the box [x1, y1, x2, y2] with 95% confidence).

---

## *9. Explain in detail the variants of convolution functions.*
Convolution operations in **Convolutional Neural Networks (CNNs)** can take various forms and be adjusted to suit specific needs in tasks such as image processing and feature extraction

### 1. **Full Convolution**
- Full convolution refers to the most standard form of convolution where we apply a kernel (filter) to an input image and slide it across the entire input.
- When using **full convolution**, the output feature map’s dimensions increase compared to the input, as enough zero-padding is added around the input image to ensure the kernel can slide over every pixel, including those near the borders.
- **How it works**: We add zeros around the input so that the kernel has a chance to cover every pixel multiple times (the kernel visits every pixel exactly **k times**, where **k** is the kernel size).
- **Output Size**: The output of the convolution is larger than the input, resulting in a feature map that has dimensions of **m + k - 1** (where **m** is the size of the input and **k** is the kernel size).

**Advantages**:
- Full convolution allows the kernel to learn from every pixel, even at the borders, and helps to capture all spatial information.
**Disadvantages**:
- **Memory-intensive**: It requires significant computational resources and may lead to large output sizes.
- **Difficulty in learning**: Because the kernel is applied to every possible region, learning an optimal kernel for all positions may be more challenging.
    

### 2. **Zero Padding Variants**
- Zero padding is a technique used to add extra rows and columns of zeros around the input image to ensure that the convolution operation can be performed more effectively.
- There are different **types of zero padding** techniques that influence the dimensions of the output.
#### **Valid Padding (No Padding)**
- **Description**: No padding is applied, meaning the output size will shrink after each convolution operation. Only valid (non-zero) positions of the input are considered.
- **Effect on Output Size**: After applying the kernel, the output dimensions will reduce. For example, if the kernel is **3x3**, the width and height of the feature map will shrink by **2 pixels** (one on each side).
- **When to Use**: Valid padding is used when we don’t need to preserve the exact spatial dimensions of the input. It is more efficient when spatial size reduction is desired.

#### **Same Padding**
- **Description**: Padding is applied in such a way that the output size is the same as the input size. This is done by adding enough zeros around the input so that the kernel can apply to the entire image while keeping the spatial dimensions unchanged.
- **Effect on Output Size**: After applying the kernel, the output will have the same width and height as the input.
- **When to Use**: Same padding is often used in CNNs where we want the output to have the same size as the input, making it easier to stack layers without reducing the spatial resolution of the input.

#### **Full Padding**
- **Description**: This method involves adding zeros around the input so that the kernel can slide across the entire input and cover every pixel multiple times, even at the borders. The output size becomes larger than the original input.
- **Effect on Output Size**: The output size will be **m + k - 1**, where **m** is the size of the input and **k** is the kernel size.
- **When to Use**: Full padding is used when we want to ensure that the kernel visits each input pixel multiple times, making sure that all spatial relationships are considered.


### 3. **Unshared Convolution**

**Unshared convolution** (also called **locally connected layers**) is a variant of convolution where different regions of the input image are allowed to use different kernels. Unlike the standard convolution, where the same kernel is applied across all positions, unshared convolution allows different parts of the image to be processed using different filters.
- **How it works**: Instead of using the same set of weights (kernels) across the entire input, unshared convolution uses a set of locally connected weights that can vary by region. The weights are not shared between different regions of the input.
    
**Advantages**:
- **Reduces memory consumption**: Since the weights are not shared, the model is more flexible in learning local features.
- **Increases statistical efficiency**: It allows the network to learn specific features for different parts of the input image.
- **Reduces computation**: This leads to a decrease in computation for both the forward and backward passes during training.
    
**When to Use**: Unshared convolution is useful when we want the network to learn different features in different regions of the input. For instance, it’s helpful when you know that a feature (like a mouth or eyes) should only appear in specific parts of the image, rather than across the whole image.


### 4. **Tiled Convolution**
- **Tiled convolution** involves learning a set of kernels and rotating through them as we move across the image. Instead of using the same filter at every location, different kernels are used in neighboring locations.
- **How it works**: A set of kernels (filters) is learned. As we move across the image, we rotate through these kernels, allowing neighboring regions to use different filters for feature extraction.
- **Memory Consideration**: The memory requirement increases because more filters need to be stored.

**Advantages**:
- **Diversity in feature detection**: By rotating through different filters, the network can learn to detect a wider variety of features in nearby regions.
- **Increased robustness**: It makes the network more invariant to local transformations, such as rotations or small shifts in the features.
- **When to Use**: Tiled convolution is useful when you want to capture different features at different spatial locations, especially in cases where the same feature might be represented differently across the image.



|Convolution Type|Effect on Output Size|Advantages|Use Case|
|---|---|---|---|
|**Full Convolution**|Output is larger than input (m + k - 1)|Captures detailed information across all positions.|Tasks that require full coverage of the input image.|
|**Valid Padding**|Output is smaller than input|Reduces size, more efficient, fast computation.|When spatial size reduction is desired.|
|**Same Padding**|Output is the same size as input|Keeps the size consistent, allows stacking of layers.|When input and output size must remain the same.|
|**Full Padding**|Output is larger than input|Useful for covering all pixels.|When coverage of all pixels is needed.|
|**Unshared Convolution**|Varies by region|Reduces memory consumption and computation, local features.|When different parts of the image require distinct features.|
|**Tiled Convolution**|Varies by kernel set|Detects diverse features, enhances feature robustness.|When spatially local transformations need to be captured.|

---
## *10. What is meant by parameter sharing in CNN? How does the parameter sharing helps to improve a machine learning system?*

---

## *11. What are the motivations behind using Convolution operation in neural networks? Compare traditional convolution and Tiled convolution methods.*



