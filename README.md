## Recursive Trees

For this part, we want to explore the idea of recursive function.

For these examples, we need a simple tree structure. Here we'll represent a node in a tree as a list with the first element being the node value, and the rest of the list being the children nodes.
That is to say, our tree structure is a simple nested list structure.

​	![tree1](C:\Computer\Document\HARVARD_GSD\Courses\20Spring\6009\tutorial\tut03\tut03\resources\tree1.png)


```python
'''
[val, <children>]
'''
tree1 = [13,
         [7],
         [8, 
          [99],
          [16, 
           [77]],
          [42]]]
tree1
```




    [13, [7], [8, [99], [16, [77]], [42]]]



### Question 1
```python
def tree_max(tree):
    """Walk a tree, returning the maximum value in the 
       (assumed non-empty) tree.
    >>> tree_max([13, [7], [8, [99], [16, [77]], [42]]])
    99    
    """
    pass

```


```python
# Test your code. The answer is 99
tree_max(tree1)

```

### Question 2
```python
def depth_tree(tree):
    """ Walk a tree, returning the depth of the tree
    >>> depth_tree([13, [7], [8, [99], [16, [77]], [42]]])
    4
    """
    pass
```


```python
# Test your code. The answer is 4
depth_tree(tree1)
```

### Question 3
Given two tables created and populated as follows:

```sql
CREATE TABLE dbo.envelope(id int, user_id int);
CREATE TABLE dbo.docs(idnum int, pageseq int, doctext varchar(100));

INSERT INTO dbo.envelope VALUES
  (1,1),
  (2,2),
  (3,3);

INSERT INTO dbo.docs(idnum,pageseq) VALUES
  (1,5),
  (2,6),
  (null,0);
```
What will the result be from the following query:
```sql
UPDATE docs SET doctext=pageseq FROM docs INNER JOIN envelope ON envelope.id=docs.idnum
WHERE EXISTS (
  SELECT 1 FROM dbo.docs
  WHERE id=envelope.id
);
Explain your answer.
```



































## Card Game (Python Class)

Now we have a card game, with 52 cards totally. For simplicity we only focus on the "card" class.

What classes and methods do we need? Each card has a rank and a suit,so it makes sense to make a **Card** class with these attributes. In our game, "greater" cards are those with higher rank; cards with the same rank are "equal", no matter what suit they come from.

Notes:
rank=卡牌的数字; 
suit=花色


```python
class Card():
    def __init__(self, rank, suit):
        """ rank: integer from 2 to (including) 14
            suit: 'S' for Spades（黑桃）, or 'H' for Hearts(红桃）, 
                  or 'C' for Clubs(梅花）, or 'D' for Diamonds（方块）
        """
        assert suit in {'S', 'H', 'C', 'D'}
        assert rank in range(2,15)
        self.rank = rank
        self.suit = suit
    
    def __gt__(self, other): 
        # compare the current card with the other card. Return Boolean. Higher rank means bigger; other might be None
        ### PLEASE FILL IN YOUR ANSWER
        pass
    
    def __lt__(self, other): #no card is less than None
        ### PLEASE FILL IN YOUR ANSWER
        pass
    
    def __eq__(self, other): #no card equals None
        ### PLEASE FILL IN YOUR ANSWER
        pass
```


```python
# Test your code.
c1 = Card(2,'S')
c2 = Card(6,'D')
# return false
c1 > c2
# reutnr true
c1 < c2
```
