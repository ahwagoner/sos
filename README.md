# sos#include <cstddef>
#include <iostream>
template <class Object> 

class BST
{

private:
    struct Node
    {
        Object value;
        Node  *left;
        Node  *right;
    };
public:
    Node *root = NULL;
    
    bool isEmpty() const{
        return root == NULL;
    }

    void insertN(Object a) const{
        if (root == NULL)
        {
            root = new Node(a);
            return;
        }
        Node current = root;
        while (!current.isEmpty() ){

        }
    }
};

int main() {
    BST<int> t;
    t.insertN(1);
    std::cout<<t.isEmpty();
}


 void travTree( Object &a, Node &n ){
    if ( a < n.value( ) )
    { 
        if (n.left == NULL)
        { 
            n.left = Node(a);
        }
        else {
        travTree( a, n.left ); 
        
    }
    else {
        if( n.right == NULL)
        {
            n.right = Node(a);
        }
        else
        {
           travTree( a , n.left );
        }
           
    }
}


The Simple as Possible Tree (BST)

This lab will walk you through creating your own simple-as-possible binary search tree (BST). We can build on that tree iteratively to add more features. But first you have to build the first trees, test them, and then go to the next version.
The first version will just allow you to build an empty tree. You will need to put in a node structure to represent the tree contents:
struct BSTNode {
    Object value;
    BSTNode * left;
    BSTNode * right;
};
You want to put this inside a BST class:
template < class Object>
class BST {
 ...
};
Where the ... occurs is where you need to put your definition of the BSTNode, your constructor, your representation, and one publid method: empty() that will return True if the tree is empty, False otherwise.
Now compile and test this program. You will only be able to get an answer to empty which should always be True.

Add the method insert to your class. Insert will need to find the correct position of the item, and then insert it as we did in class. You can assume that there are no duplicates in this tree. If you try to insert a duplicate item it will be ignored.
Compile and test your class. You should now be able to test an empty tree and a non-empty tree and get the appropriate value.

Add the method member that takes an Object to find, and returns True or False.
Compile and test your program. Now you should be able to test to an element that is not present and one that is.

Add the method findMin and findMax.
Compile and test your program.

Add the method inOrder that will return a list representing the inorder traversal of the tree.
Compile and test your program.

Add the method delete to delete an element.
Compile and test.

Add the method height that returns the height of the tree.
Compile and test, etc.

Add a const iterator that returns the next item in the inorder traversal.
Compile and test, etc.
