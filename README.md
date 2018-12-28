# BasicTree

A basic tree library used to test out different searchs (such as depth-first or breadth-first).

This library comes with a Tree and a Node class. 

## Node
### Attributes
The Node has three attributes: 
- a list of children called children
- a cost value to get to the node called cost
- a data value called data 
When created the node has no children, a random cost between 0 and 9, and a random letter as a data value.
### Functions
The Node class has one function:
- addChild(node)
  - accepts a node as an argument to add to the list of children

## Tree
### Attributes
The Tree has three attributes as well:
- a node value called root, initialized to None
- a variable containing the total number of layers called layers
- the branching factor of the tree (also accepted as an argument to the constructor), called br
### Functions
The Tree class has three functions:
- getRoot()
  - returns the root of the tree as a node
- createTree(layerNum)
  - resets the tree with random values
  - will create as many layers as passed in as an argument
- printTree()
  - attempts to print the tree in a pretty format (not the nicest but is helpful)

## Basic Usage
Create a tree:
```python
import BasicTree as bt

tree = bt.Tree()
tree.createTree(4)
tree.printTree()
```
As the tree is randomized your output may be a little different but it should have created a tree with a total of 4 layers that will print something like this:
```python
           V                
      B        Y        
   L    W    W    Z    
A  P  N  K  X  J  G  N  
```

You could then get the root and start a basic left-search like this:
```python
root = tree.getRoot()
print(root.data)
while len(root.children) > 0:
  root = root.children[0]
  print(root.data)
```
Which (if the tree were the same as above) would output:
```python
V
B
L
A
```
