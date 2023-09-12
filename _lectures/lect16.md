---
num: "Lecture 16"
desc: "Binary Search Trees cont."
ready: true
lecture_date: 2023-09-12 09:30:00.00-7:00
---

Recorded Lecture: [9_12_23](https://drive.google.com/file/d/1ilqSd6LbBseznI5o4pDGj40FhMokXsDp/view?usp=drive_link)

## Case 3: Delete a node with two children
* First find the successor (node with next greater value) in the right subtree
	* This can be done by traversing the left children of the node to be deleted’s right subtree
	* Also note that the successor will always only have **at most** one child
		* If the successor had a left child, then it wouldn’t be the successor!
* Temporarily store the successor and delete the successor from the tree
	* Deleting the successor will fall in either Case 1 or Case 2
* Replace the deleted node’s value with the successor’s value

![BSTDeleteCase3.png](BSTDeleteCase3.png)
