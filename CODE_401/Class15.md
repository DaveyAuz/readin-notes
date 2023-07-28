# Reading Notes Class #15
<ol>

><li> Binary Tree in Java:

```JAVA
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;

    TreeNode(int val) {
        this.val = val;
        this.left = null;
        this.right = null;
    }
}

public class BinaryTree {
    private TreeNode root;

    public BinaryTree() {
        root = null;
    }

    // Insertion in Binary Tree
    public void insert(int val) {
        root = insertRecursive(root, val);
    }

    private TreeNode insertRecursive(TreeNode node, int val) {
        if (node == null) {
            return new TreeNode(val);
        }

        if (val < node.val) {
            node.left = insertRecursive(node.left, val);
        } else {
            node.right = insertRecursive(node.right, val);
        }

        return node;
    }

    // Pre-order traversal (root, left, right)
    public void preOrder(TreeNode node) {
        if (node != null) {
            System.out.print(node.val + " ");
            preOrder(node.left);
            preOrder(node.right);
        }
    }

    // In-order traversal (left, root, right)
    public void inOrder(TreeNode node) {
        if (node != null) {
            inOrder(node.left);
            System.out.print(node.val + " ");
            inOrder(node.right);
        }
    }

    // Post-order traversal (left, right, root)
    public void postOrder(TreeNode node) {
        if (node != null) {
            postOrder(node.left);
            postOrder(node.right);
            System.out.print(node.val + " ");
        }
    }

    public static void main(String[] args) {
        BinaryTree bt = new BinaryTree();
        bt.insert(5);
        bt.insert(3);
        bt.insert(7);
        bt.insert(2);
        bt.insert(4);
        bt.insert(6);
        bt.insert(8);

        System.out.print("Pre-order traversal: ");
        bt.preOrder(bt.root);

        System.out.print("\nIn-order traversal: ");
        bt.inOrder(bt.root);

        System.out.print("\nPost-order traversal: ");
        bt.postOrder(bt.root);
    }
}
```

</li>

><li> Binary Search Tree (BST) in Java:

```JAVA
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;

    TreeNode(int val) {
        this.val = val;
        this.left = null;
        this.right = null;
    }
}

public class BinarySearchTree {
    private TreeNode root;

    public BinarySearchTree() {
        root = null;
    }

    // Insertion in Binary Search Tree
    public void insert(int val) {
        root = insertRecursive(root, val);
    }

    private TreeNode insertRecursive(TreeNode node, int val) {
        if (node == null) {
            return new TreeNode(val);
        }

        if (val < node.val) {
            node.left = insertRecursive(node.left, val);
        } else {
            node.right = insertRecursive(node.right, val);
        }

        return node;
    }

    // In-order traversal (left, root, right)
    public void inOrder(TreeNode node) {
        if (node != null) {
            inOrder(node.left);
            System.out.print(node.val + " ");
            inOrder(node.right);
        }
    }

    // Search in Binary Search Tree
    public boolean search(int val) {
        return searchRecursive(root, val);
    }

    private boolean searchRecursive(TreeNode node, int val) {
        if (node == null) {
            return false;
        }

        if (node.val == val) {
            return true;
        } else if (val < node.val) {
            return searchRecursive(node.left, val);
        } else {
            return searchRecursive(node.right, val);
        }
    }

    public static void main(String[] args) {
        BinarySearchTree bst = new BinarySearchTree();
        bst.insert(50);
        bst.insert(30);
        bst.insert(70);
        bst.insert(20);
        bst.insert(40);
        bst.insert(60);
        bst.insert(80);

        System.out.print("In-order traversal: ");
        bst.inOrder(bst.root);

        int target = 40;
        System.out.println("\nIs " + target + " present in BST? " + bst.search(target));
    }
}
```
</li>

><li> K-ary Tree in Java:

```JAVA
class KaryTreeNode {
    int val;
    List<KaryTreeNode> children;

    KaryTreeNode(int val) {
        this.val = val;
        this.children = new ArrayList<>();
    }
}

public class KaryTree {
    private KaryTreeNode root;

    public KaryTree() {
        root = null;
    }

    // Insertion in K-ary Tree
    public void insert(int parentVal, int val) {
        if (root == null) {
            root = new KaryTreeNode(parentVal);
        }

        KaryTreeNode parentNode = findNode(root, parentVal);
        if (parentNode != null) {
            parentNode.children.add(new KaryTreeNode(val));
        }
    }

    // Breadth First Traversal
    public void breadthFirst() {
        if (root == null) {
            return;
        }

        Queue<KaryTreeNode> queue = new LinkedList<>();
        queue.add(root);

        while (!queue.isEmpty()) {
            KaryTreeNode curr = queue.poll();
            System.out.print(curr.val + " ");

            for (KaryTreeNode child : curr.children) {
                queue.add(child);
            }
        }
    }

    private KaryTreeNode findNode(KaryTreeNode node, int val) {
        if (node == null) {
            return null;
        }

        if (node.val == val) {
            return node;
        }

        for (KaryTreeNode child : node.children) {
            KaryTreeNode foundNode = findNode(child, val);
            if (foundNode != null) {
                return foundNode;
            }
        }

        return null;
    }

    public static void main(String[] args) {
        KaryTree karyTree = new KaryTree();
        karyTree.insert(1, 2);
        karyTree.insert(1, 3);
        karyTree.insert(
```

</li>

><li> vocabulary/definition list for Binary Trees, Binary Search Trees (BST), and K-ary Trees:

1) Binary Tree:

* Node: A component of the tree that may contain its own value and references to other nodes (left and right children).
* Root: The starting node of the tree from which all other nodes are descendants.
* Left: A reference to the left child node, in a binary tree.
* Right: A reference to the right child node, in a binary tree.
* Edge: The link between a parent and its child node.
* Leaf: A node that does not have any children.
* Height: The number of edges from the root to the furthest leaf, representing the depth or maximum level of the tree.

2) Binary Search Tree (BST):

* All properties of a Binary Tree apply to a BST as well.
* BST Property: In a Binary Search Tree, for every node, all values in the left subtree are less than or equal to the node's value, and all values in the right subtree are greater than or equal to the node's value.
* Searching, insertion, and deletion in a BST are performed efficiently based on the ordering property, allowing for fast retrieval and modifications.

3) K-ary Tree:

* A tree where each node can have a maximum of K children, where K is a positive integer (K-ary).
* The common terminology used in Binary Trees, like node, root, left, right, edge, leaf, and height, also applies to K-ary Trees.
* A Binary Tree is a special case of a K-ary Tree where K = 2 (each node has a maximum of two children).

4) Breadth First Traversal:

* A tree traversal method where nodes at the same level are visited before moving on to nodes at the next level.
* It involves visiting all the nodes on one level before proceeding to the next level.
* Utilizes a queue data structure to keep track of nodes to be visited.
* Useful for tasks like level-order printing and searching.

5) Depth First Traversal:

* A tree traversal method where the traversal goes as deep as possible along each branch before backtracking.
It explores as far as possible along each branch before backtracking.
* Three common depth-first traversal methods are Pre-order, In-order, and Post-order.
* Pre-order: Root -> Left Subtree -> Right Subtree
* In-order: Left Subtree -> Root -> Right Subtree
* Post-order: Left Subtree -> Right Subtree -> Root
* Typically implemented using recursion, utilizing the call stack to traverse the tree.

6) Insertion (Binary Tree and K-ary Tree):

*   The process of adding a new node to a tree.
* In Binary Trees, the new node can be added as the left or right child of an existing node based on space availability.
* In K-ary Trees, the new node is added as a child to an existing node, respecting the maximum number of children (K) allowed for each node.

7) Big O Notation:

* A notation used to describe the time and space complexity of algorithms and data structures.
* "O" represents the upper bound, or worst-case, time or space complexity.
* For Binary Trees, the worst-case time complexity for most operations is O(n), where n is the number of nodes, as traversal may involve visiting all nodes.
* For K-ary Trees, the worst-case time complexity for most operations is still O(n), as traversal may involve visiting all nodes.
* For Balanced Binary Search Trees, the height is log(n), resulting in O(log n) time complexity for search, insertion, and deletion, making these operations efficient.
* Space complexity is described in terms of the extra space used, with O(1) indicating constant space usage and O(n) indicating linear space usage.

</li>

<ol>

[HOME](../README.md)