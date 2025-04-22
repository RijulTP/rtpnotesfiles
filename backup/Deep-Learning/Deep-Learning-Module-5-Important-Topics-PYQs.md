# Deep-Learning-Module-5-Important-Topics-PYQs

> [!question] For more notes visit 
> https://rtpnotes.vercel.app
```table-of-contents
```
## *1. How deep learning supports the field of natural language processing.*

### What is NLP?
**Natural Language Processing (NLP)** is a field that helps computers understand, interpret, and respond to human language.
#### Main uses of NLP:
- **Spell check**
- **Keyword search**
- **Text classification** (e.g., Positive/Negative reviews)
- **Machine translation** (like Google Translate)
- **Voice assistants** (like Siri, Alexa)
- **Answering complex questions**

### How Deep Learning Helps NLP

**Deep Learning** (a type of Artificial Intelligence) is used to make NLP tasks more accurate and intelligent — especially in **Machine Translation (MT)**.

### What is Machine Translation (MT)?
Machine Translation = **Automatically converting one language into another** (e.g., English to Hindi).

### Old vs. New Approach

#### Old Approach: **Statistical Machine Translation (SMT)**
- Uses fixed rules and probability.
- Translates phrase-by-phrase.
- Struggles with:
    - Long sentences
    - Grammar like gender and word order
#### New Approach: **Neural Machine Translation (NMT)**
- Uses **Deep Learning** (neural networks)
- Learns from **pairs of sentences** (source → target)
- Doesn’t need manual grammar rules
- Works end-to-end (fully automated learning)

### Why Deep Learning is Better in NMT?
- Can learn **meaning**, not just words.
- Works well even with **long sentences** (with help of LSTM, GRU).
- **Attention mechanism** helps focus on important words during translation (just like how we read!).

### Example: Sanskrit → Malayalam Translator
A deep learning-based **NMT model** can be trained to translate Sanskrit to Malayalam using parallel sentence data.

It learns patterns like grammar, meaning, and sentence structure without being explicitly programmed.

---

## *2. Describe the technique of representation learning in deep learning.*

- **Representation learning** is a technique where a model **automatically learns useful features** (or representations) from raw data, instead of manually designing them.
- The **way data is represented** affects how easy it is to solve a problem.
- Good representation = Faster, simpler, and more accurate learning.

### In Deep Learning
- A **Deep Neural Network** learns to transform raw input (like images or text) into **useful internal representations**.
- These transformations happen layer by layer.
#### Example:
If we train a neural network to detect **cats in images**:

| Layer          | What it learns       |
| -------------- | -------------------- |
| Input Layer    | Raw pixels           |
| Hidden Layer 1 | Edges or corners     |
| Hidden Layer 2 | Eyes, ears, whiskers |
| Hidden Layer 3 | Entire cat face      |
| Output Layer   | "Cat" or "Not a Cat" |
Each hidden layer transforms the image into a **better representation** for solving the problem.

### Goal of Representation Learning
- Make the next learning step **easier**.
- **Keep important information** from the input.
- Make features more **independent and meaningful**.
- Help in **generalization** — performing well even on unseen data.


### Transfer Learning
**Transfer Learning** = Using knowledge from one task to help another similar task.
#### Example:
- **Task P1**: Classify images of Cats vs. Dogs.
- **Task P2**: Classify images of Lions vs. Elephants.
- The model learns **basic features** (like edges, shapes) from Task P1.  
- These features can be reused for Task P2, even with **less training data**.

This works because:
- **Cats, dogs, lions, elephants** all share common visual features (like fur, eyes, ears).
- So, learned representations from one task can be reused in another similar task.

---

## *3. Illustrate the use of deep learning concepts in Computer Vision.*

### What is Computer Vision?

**Computer Vision (CV)** is a branch of AI where **computers are trained to "see" and understand images or videos**, just like humans do.

### Why Deep Learning for Computer Vision?
Deep learning — especially **Convolutional Neural Networks (CNNs)** — has greatly improved the **accuracy** and **performance** of tasks like:
- Image classification
- Object detection
- Face recognition
- Self-driving car vision
- Medical image diagnosis

### Core Deep Learning Concept: Convolutional Neural Networks (CNNs)
CNNs are designed to:
- Automatically **extract features** (like edges, shapes, textures) from images.
- **Reduce image data** to the most useful parts.
- Make **predictions** based on learned visual patterns.

### How CNNs Work – Step by Step:
1. **Input Image**  
    Every image is represented as a **matrix of pixel values** (for Red, Green, Blue channels).
2. **Convolution Layers**
    - Apply small filters (kernels) to detect features like **edges or corners**.
    - The result is a **feature map** (a new image showing the detected feature).
3. **Pooling Layers**
    - Reduce the size of the feature maps.
    - Keeps the most important information and removes noise.
4. **Flattening + Fully Connected Layers**
    - Final features are **flattened into a 1D vector**.
    - Passed through regular neural network layers to **predict** the output (e.g., "cat" or "dog").

---
## *4. What is an autoencoder? Give one application of an autoencoder.*

### What is an Autoencoder?
An **Autoencoder** is a type of **neural network used in unsupervised learning**.  
Its main goal is to **compress data into a smaller form** (called encoding) and then **reconstruct it** back to the original form.
### **It has 3 main parts**
![[Pasted image 20250420125240.png]]

|Part|What it does|
|---|---|
|**Encoder**|Compresses input into a smaller representation|
|**Bottleneck**|The compressed hidden layer (core representation)|
|**Decoder**|Reconstructs the input from the compressed version|

### How Autoencoders Work
1. Input data is passed into the **encoder**.
2. Encoder **compresses** it into a smaller format (encoding).
3. This encoding is then passed into the **decoder**.
4. Decoder **tries to recreate the original input**.
5. The network is trained to **minimize reconstruction error** (difference between original and output).

### Application of Autoencoders
#### **Anomaly Detection**
Autoencoders are **trained to learn normal patterns** in data.  
If you feed it new data that is very **different** from the training data, the reconstruction error becomes **high**.

So, if the reconstruction error is **large**, we can say the data is **anomalous** (abnormal).
#### Example:
- Train an autoencoder on **normal bank transactions**.
- When a **fraudulent transaction** is fed in, the autoencoder **fails to recreate it accurately**, showing high error.
- This helps in **detecting fraud** automatically.
---
## *5. What are the benefits and drawbacks of using Word embeddings?*

### **What are Word Embeddings?**
Word embeddings are a way to turn words into numbers so that computers can understand the meaning of words.  
Words with similar meanings get similar numbers. For example, "king" and "queen" will have similar values.
Think of it like giving each word a position on a map where similar words are close together.


#### **Benefits of Word Embeddings:**
- They capture word meanings and relationships.
- Faster and more efficient than older methods.
- Help models understand context in language.
- Commonly used in most NLP tasks.

#### **Drawbacks of Word Embeddings:**
- Require a lot of memory for large vocabularies.
- Depend on the training data (may carry bias).
- Cannot distinguish similar-sounding words (e.g., _cell_ vs _sell_).
- Can face errors with unknown words (Out-of-Vocabulary).

---

## *6. Describe some application areas of deep learning*

### **1. Image Processing and Computer Vision**
✔ **Facial Recognition** → Used in phones and security systems.  
✔ **Medical Imaging** → Detecting diseases from X-rays, MRIs.  
✔ **Self-driving Cars** → Identifying objects, lane detection.

### **2. Natural Language Processing (NLP)**
✔ **Machine Translation** → Google Translate.  
✔ **Chatbots and Virtual Assistants** → Alexa, Siri, ChatGPT.  
✔ **Speech Recognition** → Voice-to-text applications.

### **3. Healthcare and Drug Discovery**
✔ **Disease Prediction** → AI diagnosing cancer, diabetes.  
✔ **Protein Structure Prediction** → Used in drug discovery.

### **4. Finance and Stock Market**
✔ **Fraud Detection** → Identifying fraudulent transactions.  
✔ **Stock Price Prediction** → Using historical data for forecasting.

### **5. Gaming and Robotics**
✔ **AI in Video Games** → Realistic NPC behaviors.  
✔ **Industrial Robots** → Used in manufacturing and automation.

---

## *7. Compare Boltzmann Machine with Deep Belief Network.*
### What is a **Boltzmann Machine**?
![[Pasted image 20250420131017.png]]
A **Boltzmann Machine** is a type of neural network used to **find patterns in data**. It is **unsupervised**, which means it **learns from data without needing labeled answers**.
- It has two types of nodes:
    - **Visible nodes**: What we can see (the input).
    - **Hidden nodes**: What we cannot see (used to understand patterns).
- All nodes are connected to each other.
- It uses probability and randomness to learn.
- It tries to **reduce its energy**, like a system finding the most stable state.
	- Think of it like a group of people all talking to each other, trying to agree on something. Over time, they settle into a state where they all kind of “agree” — that’s learning.

### What is a **Deep Belief Network (DBN)**?
![[Pasted image 20250420131116.png]]

A **Deep Belief Network** is a **stack of smaller networks** called **Restricted Boltzmann Machines (RBMs)**.
- It is also used to learn patterns, but in **multiple layers**, one after another.
- Each layer learns something deeper or more meaningful.
- It is easier to train than a full Boltzmann Machine.
- It is often used to **pre-train deep learning models**.
- Imagine learning to draw. First, you learn lines, then shapes, then faces. DBNs work similarly — each layer learns something more advanced.

|Feature|Boltzmann Machine|Deep Belief Network (DBN)|
|---|---|---|
|**Learning Type**|Unsupervised|Unsupervised (layer-by-layer)|
|**Structure**|One layer of visible and hidden units, all connected|Multiple layers, made of stacked RBMs|
|**Connections**|All nodes connect with each other|Nodes in one layer connect only to the next layer|
|**Training**|Hard to train due to full connections|Easier to train (train one layer at a time)|
|**Use Case**|Find patterns, detect anomalies|Used in deep learning for feature learning and pre-training|
|**Speed**|Slow|Faster than Boltzmann Machine|
|**Type**|Stochastic (random-based)|Probabilistic (based on likelihood)|

---

## *8. Explain the merits and demerits of using Autoencoders in Computer Vision.*

**Merits of Autoencoders in Computer Vision**
- Help in **reducing dimensionality** of images, making it easier to process.
- Can **denoise** images by learning to remove noise from input images.
- **Unsupervised learning** (no labeled data needed).
- Useful for **anomaly detection** (detects unusual images).
- Learns important **features** of images for downstream tasks.


**Demerits of Autoencoders in Computer Vision**:
- Learned features can be **hard to interpret**.
- Risk of **losing important information** during compression.
- Can **overfit** if not designed properly.
- Training can be **difficult** and take time to fine-tune.
- Not ideal for **complex tasks** like object detection or segmentation.
---

## *9. Illustrate the use of deep learning concepts in Speech Recognition.*
**Speech Recognition** is the process of converting spoken language (audio) into written text. Deep learning plays a major role in improving the accuracy and performance of modern speech recognition systems.

- **Input (Audio)**
    - When someone speaks, the sound is broken into small pieces (like every 20 milliseconds).
    - These small pieces are turned into numbers (features) that the computer can understand.
- **Output (Text)**
    - The goal is to guess the correct words the person spoke.
- **Deep Learning Model**
    - A special kind of program (called a **neural network**) learns how to match sounds to words.
    - It improves over time by training on lots of speech and text examples.

### **Two Types of Deep Learning Systems:**

#### 1. **Old method (with steps):**
- Earlier, systems used separate steps:
    - First extract features from audio.
    - Then use **HMM** (Hidden Markov Model) to match sound to words.
    - Deep learning was used to help in one part only.
#### 2. **New method (end-to-end):**
- Now, deep learning does **everything in one model**.
- It listens to audio and directly gives the text, all in one go.
- This is called **end-to-end speech recognition**.
- Example: **LSTM** (Long Short-Term Memory) networks and **CTC** (Connectionist Temporal Classification) help in this.


### Applications
1. **Automatic Speech Recognition (ASR):**
	1. Transcribing spoken words into text accurately.
	2. Example: Virtual assistants like Siri and Alexa.
2. **Speech-to-Text Applications:**
	1. Facilitating real-time transcription.
	2. Example: Live captions for videos or meetings.
3. **Speaker Identification:**
	1. Recognizing the speaker's identity from their voice.
	2. Example: Security systems based on voice authentication.
4. **Language Translation:**
	1. Translating spoken words from one language to another.
	2. Example: Google Translate for real-time audio translation.
5. **Natural Language Understanding (NLU):**
	1. Interpreting and analyzing spoken commands.
	2. Example: "Play my favorite song" processed by AI-based music apps
---
## *10. Explain any two word embedding techniques in detail.*

### **What is Word Embedding?**
Word embedding means converting words into fixed-size vectors (numbers) that carry meaning. These vectors are useful in many tasks like translation, chatbots, and sentiment analysis.
### Word2Vec
**Word2Vec** is a technique used in deep learning to convert words into numbers (called **vectors**) so that a computer can understand their **meanings and relationships**.

Words that are used in similar contexts will end up having **similar vectors**. This is super helpful for tasks like language translation, autocomplete, and recommendation systems.

#### **How Word2Vec Works:**
- Every word is first assigned a **vector**. This can be:
    - A **random vector**, or
    - A **one-hot vector** (a vector of all 0s with just one 1 at the position for that word).
>  Example:  
> If we have 500 unique words in our text, a one-hot vector would be a list of 500 numbers, where only one of them is "1", and the rest are "0".

- Then we pick a **window size** (how many nearby words we care about). 
- We go through the entire text and **train a small neural network** (with just one hidden layer) to adjust these vectors so that similar words are placed **closer together in vector space**.
- There are **Two Main Models in Word2Vec:**
#### 1. **CBOW (Continuous Bag of Words)**
- CBOW stands for **Continuous Bag of Words**.  
- Its goal is simple:
- **Given the surrounding words (context), can you guess the middle word?**
- Example
	- **"The cat sat on the mat."**
	- If we pick **“sat”** as the target word and use a **window size of 2**, the context words are:
		- `Context words = ["The", "cat", "on", "the"]`
		- `Target word = "sat"`
	- CBOW will use these context words to **predict** the center word ("sat").

Now let’s visualize the CBOW model as a simple neural network. Take a look at this
![[Pasted image 20250423003256.png]]
##### **1. Input Layer (Context Words)**
- We take the **context words** (`The`, `cat`, `on`, `the`) and convert them into **vectors** using one-hot encoding or embeddings.
- Each word becomes a long list of numbers. We feed these vectors into the model.
##### **2. Projection / Hidden Layer**
- The vectors are **averaged** or **added together**.
- This gives us a single vector that represents the **combined meaning** of the context.
- This layer doesn’t apply any activation—it just combines the input.
- Think of it as a way to mix all the surrounding words into a single meaning.
##### **3. Output Layer**
- The model now tries to guess the **most likely word** that fits the center position based on that combined vector.
- It outputs a **probability distribution** over all the words in the vocabulary.
- The word with the **highest probability** is the prediction.
#### 2. **Skip-Gram**
- The **Skip-gram** model is a type of word embedding technique used in **Word2Vec**. Its goal is the opposite of **CBOW**:
	- **Given a target word, can you predict the surrounding context words?**
- Let’s use the same sentence from before:
	- **"The cat sat on the mat."**
	- If we choose **“sat”** as the target word and use a **window size of 2**, the context words will be:
		- Context words = ["The", "cat", "on", "the"]
		- Target word = "sat"
- Key Idea of Skip-gram:
	- **Target word**: "sat"
	- **Context words**: ["The", "cat", "on", "the"]
- Skip-gram uses the **target word** ("sat") to predict the **context words** (["The", "cat", "on", "the"]).
![[Pasted image 20250423003742.png]]

#### **1. Input Layer (Target Word)**
- The **input** to the model is the **target word** (`sat` in this case).
- We convert it into a vector (like CBOW, using one-hot encoding or embeddings).
#### **2. Projection / Hidden Layer**
- The vector representing the target word is passed through a **hidden layer** (projection layer).
- The idea is to create a representation of the target word in the vector space.
#### **3. Output Layer (Context Words)**
- The model **predicts** the context words based on the target word.
- It outputs a **probability distribution** over all words in the vocabulary for each context word.
- The context words are selected from this distribution, and the model adjusts the vectors based on the likelihood of these predictions.

---
### Glove
**GloVe** stands for **Global Vectors for Word Representation**. It’s a method used to **turn words into numbers** so that computers can understand them.

Imagine trying to explain words to a computer — it doesn’t understand “cat” or “coffee” like we do. But if we can represent these words as numbers (like turning “cat” into [0.2, 0.8, -0.5, …]), the computer can **learn** how similar they are.

#### The Goal of GloVe
To give each word a **unique number vector** (like coordinates) so that:
- Similar words get similar numbers.
- Word meanings and relationships are captured.
#### Let’s Use an Example
Imagine we give a computer this small set of sentences:

> “It is a nice evening.”  
> “Good evening!”  
> “Is it a nice evening?” 

The computer now watches how often words appear **together**. For example:
- “nice” appears often with “evening”
- “it” often appears with “is”
- “good” appears near “evening” once

So it creates a table (called a **co-occurrence matrix**) where it notes:
- How often every word shows up **next to** every other word.
Think of this like a **big tally sheet** of which words hang out together.

- ![[Pasted image 20250423004458.png]]
-  The words which occur next to each other get a value of 1, if they are one word apart then 1/2, if two words apart then 1/3 and so on
- Lets take a look at few values
	- **First row, first column**, It and it => Both never comes together, so assigning as zero
	- **Second row, first column**, It and is
		- These appear in 2 sentences
			- It is a nice evening.
			- Is it a nice evening?
		- In both the cases, they appear next to each other
		- So We can Assign 1 + 1
	- **Third row, first column**, It and a
		- These appear in 2 sentences
			- It is a nice evening.
			- Is it a nice evening?
		- In sentence #1, it is one word apart => 1/2
		- In sentence #2 it is close to each other =>1
		- So we assign 1/2 + 1

#### How It Learns Meaning
Now here’s the clever part:
Words that appear in similar situations probably mean similar things.
- “cat” and “dog” both appear near “pet”, “food”, “play”
- “doctor” and “nurse” both appear near “hospital”, “patient”

So GloVe uses these patterns to figure out:
- "Ah, **cat and dog** are kinda similar"
- "King and queen are connected somehow"
    
Eventually, it gives each word a **vector** (a list of numbers).  
For example:
- **“king”** = [0.8, 1.2, -0.4, ...]
- **“queen”** = [0.7, 1.1, -0.3, ...]
- **“man”** = [0.5, 1.0, -0.5, ...]
- **“woman”** = [0.6, 1.05, -0.4, ...]
    
Now we can do math with them
#### Word Math
> king - man + woman = ?  
> Answer: ≈ queen

**GloVe can figure out that “king” is to “man” as “queen” is to “woman”**


### GloVe vs Word2Vec 
- **Word2Vec** focuses on **local context** (words nearby in a sentence).
- **GloVe** looks at **all the data** (global statistics) to find deeper relationships.

---

## *11. Explain any three research areas of neural network.*
### **1. Computer Vision**
- **Goal:** Help machines “see” and understand visual information like images and videos.
- **Examples:**
    - Face recognition (like unlocking your phone with your face)
    - Object detection (like detecting people or cars in surveillance
    - Image classification (identifying if an image contains a cat or a dog)
- **Neural Network Used:** Convolutional Neural Networks (CNNs)
- **Why it's a research area:** Researchers work to improve accuracy, reduce errors, and make these models faster and more efficient.
### **2. Natural Language Processing (NLP)**
- **Goal:** Help computers understand, generate, and respond to human language.
- **Examples:**
    - Chatbots (like ChatGPT!)
    - Language translation (Google Translate)
    - Sentiment analysis (finding out if a tweet is positive or negative)
- **Neural Network Used:** Recurrent Neural Networks (RNNs), Transformers (like BERT, GPT)
- **Why it's a research area:** Human language is complex — full of sarcasm, slang, and different meanings. So, improving how machines handle language is a big challenge.

---

### **3. Healthcare and Medical Diagnosis**
- **Goal:** Assist doctors and medical staff in diagnosing diseases and recommending treatments.
- **Examples:**
    - Predicting diseases like cancer or diabetes from test results or images
    - Analyzing MRI or CT scans
    - Monitoring patient health using wearable devices
- **Neural Network Used:** Deep Neural Networks (DNNs), CNNs
- **Why it's a research area:** Healthcare needs **high accuracy and reliability**, and neural networks can save lives if used correctly.

## *12. Illustrate the use of representation learning in object classification.*

### **What is Representation Learning?**
Representation learning is like teaching a machine to "see" things the way we do. It takes raw data (like images or text) and transforms it into a form that a computer can understand more easily.

Let's use a simple example to understand how representation learning works in classifying objects like **cars**, **bicycles**, and **motorcycles** from images.
### **Step-by-Step Process:**
#### **1. Raw Input Data (Images)**
- Imagine you have a collection of photos of different objects
	- **Cars**
	- **Bicycles**
	- **Motorcycles**
- Each photo is a **high-dimensional array** of pixel values. A photo might have thousands or even millions of pixels, with each pixel having a color value (RGB – red, green, blue).
- **Problem**: The raw pixel data is too complex for a machine to directly understand, so we need a way to process it into something more useful.
#### **2. Preprocessing the Data**
- Before we can train the machine, we do some cleaning and preparation to make sure all images are in the right format.
- For example:
	- **Resizing** the images to make them all the same size (to avoid confusing the model).
	- **Normalizing** pixel values (scaling the pixel values so they are between 0 and 1 to make the learning easier).
	- **Data Augmentation** (creating variations of images to make the model more robust, like flipping images or changing their brightness).
#### **3. Representation Learning (Using a Neural Network)**
- Here’s where the magic of **representation learning** happens. We use a special type of neural network called a **Convolutional Neural Network (CNN)**.
- A CNN is like a smart "filter" that automatically learns to recognize patterns in images. It works in several layers, each focusing on different aspects of the image:
- **Convolutional Layers**: These layers help the model detect simple features like edges or corners in the image. For example, it might learn to detect that a bicycle has circular wheels.
- **Pooling Layers**: These layers simplify the image, making it smaller and easier for the network to process while keeping important features.
- **Fully Connected Layers**: These layers take the detected features and start learning more abstract concepts, like recognizing the object as a "bicycle" or "car."
#### **4. Feature Extraction**

As the CNN learns from the images, it starts to extract **features** (important details) from the image. These features could be simple patterns like colors or edges, or more complex ones like shapes or textures. These features are much easier for the model to use for classification.

For example, for a **bicycle**:
- It might learn features like the **circular shape** of the wheels or the **frame** of the bike.
- For a **car**, it might learn features like **rectangular shapes** and the presence of **windows**.

#### **5. Classification (Making the Prediction)**
Once the CNN has learned to recognize important features from the images, the next step is to **classify** the object. For this, we use a **classifier** (such as **softmax** or **support vector machine**) to label the object.
- **Softmax** helps the model choose one object class (car, bicycle, motorcycle) from the possible options.
- The model takes the learned features (from CNN), and based on the patterns it learned, it predicts whether the image is of a **car**, **bicycle**, or **motorcycle**.

#### **6. Prediction on New Images**
After training, the model is ready to classify **new, unseen images**. For example, it might be shown a new photo of a **motorcycle**. The model:
1. Takes the image and applies all the learned features (from representation learning).
2. The CNN extracts features from the image, and the classifier decides that the image is a **motorcycle**.


### **Why is Representation Learning Important in Object Classification?**
- **Automatic Feature Extraction**: Unlike earlier methods where features had to be manually defined, representation learning (using CNNs) allows the machine to automatically learn which features are important for classification.
- **Improved Accuracy**: By learning features that are specific to the objects (e.g., the wheels of a bicycle or the shape of a car), the model can classify objects much more accurately.
- **Generalization**: The learned features can generalize well to new images, even if the objects are viewed from different angles or in different lighting conditions.

## *13. What are generative models? Discuss the features of generative models.*
- Generative models are a type of machine learning model that **learns to generate new data** that looks similar to the training data.
- Think of it like an artist who studies thousands of paintings and then creates new, original artworks that look like they belong in the same style.
- In technical terms, a generative model **learns the underlying patterns or distribution of the input data**, and then uses that knowledge to generate new examples.

### **Key Features of Generative Models:**

|Feature|Description|
|---|---|
|**1. Data Generation**|Can create new data that looks realistic, like images, text, or audio.|
|**2. Learns Full Distribution**|Unlike discriminative models (which only learn to classify), generative models learn the **entire data distribution**.|
|**3. Unsupervised or Semi-supervised**|Often trained with **unlabeled data**, making them very useful when labeled data is scarce.|
|**4. Realistic Outputs**|Especially in GANs, outputs like **fake human faces or artworks** can look extremely real.|
|**5. Versatility**|Can be used in **image editing, text generation, drug discovery**, and more.|
|**6. Captures Hidden Patterns**|Learns the **hidden structure** of the data (e.g., what makes a cat a cat) without needing to label everything manually.|
|**7. Interactive Learning**|In GANs, there's a **competition between two networks** (generator and discriminator), which helps improve performance over time.|
