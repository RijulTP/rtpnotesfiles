# *Software-Testing-Module-3-Important-Topics-PYQs*

> [!question] For more notes visit 
> https://rtpnotes.vercel.app


## 1. Explain structural graph coverage for Design Elements.

## 2. Define Tour, Tour with side trips and Tour with Detours.

## 3. Explain any two methods for computing the cyclomatic complexity

## 4. Define Node coverage and prime path coverage in a control flow graph

## 5. Define Tour, Tour with side trips and Tour with Detours.

## 6. Draw control flow graph for the code fragment  given below

```c
w = x;
if(m>0){
	w++;
}
else{
        w = 2+w
}

if(y<=10){
	x=5+y
}
else{
	x = 3*x + y;
}

z = w+x;
```


### 7. Give the sets N0 N f, N and E for the below graph.

![[Pasted image 20250425011547.png]]
1. Give a path that is not a test path
2. List all test paths in the above graph
3. From the Above graph, find test case inputs such  that the corresponding test path visits edge (n1,n3)

### 8. Draw control flow graph for the following function

```
int binsearch(int X,int V[], int n){
	int low, high, mid;
	low = 0;high=n-1;
	while (low <= high){ 
	    mid = (low + high)/2;
	    if (X< V[mid])
		high = mid - 1;
	    else if (X > V[mid])
		low=mid + 1;
	    else
		return mid;
	    }
	return -1;
}
```


### 9. Draw CFG fragment for a) Simple if b)Simple while loop c)Simple for loop d) switch


## 10. Explain path selection criteria with reference to
1. All path coverage criteria
2. Statement Coverage Criteria
3. Branch Coverage Criteria
4. Predicate Coverage Criteria

## 11. Explain touring, side trips and detours with a neat examples.

## 12. Draw CFG fragment for (i) Simple if (ii) Simple while loop

## 13. Explain inheritance graph and coupling du-pairs with examples

## 14. Draw CFG to represent Exception handling.


## 15. Consider the graph given below. List test requirement for node coverage. Edge coverage, Prime path coverage

![[Pasted image 20250425012428.png]]

## 16. Explain the following concepts with examples (i) Call graph (ii) Inheritance graph (iii) Coupling du-pairs


## 17. Using the code snippet given in below. Perform data flow analysis and find all valid DU Pairs

```c
public int gcd(int x, int y){
	int tmp;
	while(y!=0){
		tmp = x%y;
		x = y;y=tmp
	}
	return x;
}
```


## 18. List and explain any three path selection coverage criteria



