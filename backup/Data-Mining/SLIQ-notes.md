The decision tree classfier called SLIQ, uses novel techniques that improve learning time for the classifier without loss in accuracy at the same time, these techniques allows classsfication to be perfromed on large disk resident training data.

SLIQ imposes no restrictions on the amount of training data or the number of attributes in the exampes. Therefore SLIQ can potentially obtain higher accuracies by classifying larger training datasets which cannot be handled by other classifiers



### Algorithm

1. Start presorting of the samples
2. As long as the stop criterion has not been reached
	1. for every attribute
		a. place all nodes into a class histogram
		b. Start evaluation of the splits
	2. Choose a split
	3. Update the decision tree, for each new node update its class list(nodes)
	


#### Pre-sorting of the samples:-
1. For each attribute, create an attribute list with columns for the value, sample_id and class 
2. Create a class list with columsn for the sample_Id, class and leaf node.
3. Iterate over all training samples:-
	for each attribute and class(sorted by attribute value) into the attribute list
	Insert the same ID, the class and the leaf node(sorted by sample_id)
	into the class list
	
	
	

#### Evaluation of the splits
1. For each nod and for all attributes
	1. construct a histogram(for each class the histogram saves the count of samples before and after the split)
	
2. For each attribute A
	1. For each value V (traverse the attribute list for A)
	    2. Find the entry in the class list	
        3. Update the histogram for the node
        4. Assess the split(if its a maximum, record it)
        
        
        
	Attribute lists are processes one at a time, for each value v in the attribute list for the current attribute A, we find the corresponding entry in the class list, which yields the correspkonding class and the leaf node. Now update the histogram. Attached with this leaf node.

If A is a numeric attribute all the same time the splitting

if A is a categorical attribute, we wait till the attribute list has been completely scanned and then find the subset of A with the best split

If a is a numeric attribute, we compute at the same time the splitting index for the test A<=V for this leaf.

Thus in one traversal of an attribute list, the best split using this attribute is known for all the leaf nodes. Similarly with one traversal of all the attribute lists. THe best overall split for all the leaf nodes, is known. The best split test is saved with each of the nodes.

=> The L values represnt the distributions that satisfy the test.

The R values represent that do not satisfy the test..


#### Update the class list (nodes)

1. Traverse the attribute list of the used in the node
2. For each entry (value,ID)
3. FInd the matching entry (ID class node) in the class list
4. Apply the split criterion emitting a new node
5. Replace the corresponding class list entry with (ID,class,new node)



---

## 10. Explain the working of SLIQ algorithm

- **SLIQ** is a **Decision Tree algorithm** designed for **BIG datasets** — even ones that don't fit into memory (they are stored on disk).
- It **builds a decision tree** like ID3 or CART, but **faster** and **more efficiently** for large data.
- The goal is the same: **classify** things correctly (like whether someone will buy a product, or if a loan will be approved).

### Key Ideas Before Starting
- **Sample**: A single row/data point.
- **Attribute**: A feature/column (like Age, Salary, etc.).
- **Class Label**: The outcome (like "Buy" or "Don't Buy").
- **Leaf Node**: A final decision point in the tree (no further splitting).
- **Split**: Choosing an attribute and value to divide the data into groups.


### How SLIQ Works
#### 1. Pre-sorting the Samples
 - Before even building the tree, SLIQ **sorts the data** nicely:
	- For **each attribute**, it creates an **attribute list**:
	    - Columns: (Value, ID, Class Label)
	    - Sorted by **attribute value**.
	- It also makes a **class list**:
	    - Columns: (ID, Class Label, Leaf Node)
	    - Sorted by **ID** (row number).
- **Why Pre-sort?**  
	- Because it makes finding the best splits **super fast** later!

![[Pasted image 20250426143811.png]]


#### 2. Build the Tree Step-by-Step

Repeat the following steps **until the tree is complete**:
##### a. Make Histograms
- A **histogram** here is **just a count**:
    - How many samples are **before** a split and **after** a split, **for each class**.
(Think of it like:  
➡️ How many "Up" and "Down" profits **if Age <= 30**, and how many "Up" and "Down" profits **if Age > 30**.)
##### b. Evaluate Splits
- For **each attribute** and **each value**, check:
    - If we split here, **how pure** (less mixed) will the groups be?
- Pick the **split with maximum gain** (good separation between classes).
    
 **Numeric Attributes** (like Age):
- Check splits as you go (during the scan).
 **Categorical Attributes** (like Competition: Yes/No):
- Check the best split **after** scanning the whole list.

##### c. Choose Best Split
- After checking all attributes, **pick the best one** that divides the data most cleanly.
- Save that split in the decision tree.
##### d. Update the Tree
- After splitting, **update the class list**:
    - Move each sample to its new **leaf node** based on whether it satisfies the split.

##### 3. Stop When...
- Either all data in a leaf is **pure** (only one class), or
- No good split is possible anymore.
    
---

## 18. Explain the construction of decision tree using SLIQ algorithm with an example.


