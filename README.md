# Git Intro Project

#include "binary_trees.h"

/**
 ** binary_tree_node - Creates a binary tree node.
 ** @parent: A pointer to the parent of the node to create.
 ** @value: The value to put in the new node.
 *
 ** Return: If an error occurs - NULL.
 **         Otherwise - a pointer to the new node.
 */
binary_tree_t *binary_tree_node(binary_tree_t *parent, int value)
{
        binary_tree_t *ne;

        ne = malloc(sizeof(binary_tree_t));
        if (new == NULL)
                return (NULL);

        ne->n = value;
        ne->parent = parent;
        ne->left = NULL;
        ne->right = NULL;

        return (ne);
}


────┬──────────────────────────────────────────────────────────────────────────────────────────────
       │ File: 1-binary_tree_insert_left.c
───────┼──────────────────────────────────────────────────────────────────────────────────────────────
   1   │ #include "binary_trees.h"
   2   │
   3   │ /**
   4   │  * binary_tree_insert_left - Inserts a node as a left-child of
   5   │  *                           of another in a binary tree.
   6   │  * @parent: A pointer to the node to insert the left-child in.
   7   │  * @value: The value to store in the new node.
   8   │  *
   9   │  * Return: If parent is NULL or an error occurs - NULL.
  10   │  *         Otherwise - a pointer to the new node.
  11   │  *
  12   │  * Description: If parent already has a left-child, the new node
  13   │  *              takes its place and the old left-child is set as
  14   │  *              the left-child of the new node.
  15   │  */
  16   │ binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value)
  17   │ {
  18   │     binary_tree_t *n;
  19   │
  20   │     if (parent == NULL)
  21   │         return (NULL);
  22   │
  23   │     n = binary_tree_node(parent, value);
  24   │     if (n == NULL)
  25   │         return (NULL);
  26   │
  27   │     if (parent->left != NULL)
  28   │     {
  29   │         n->left = parent->left;
  30   │         parent->left->parent = n;
  31   │     }
  32   │     parent->left = n;
  33   │
  34   │     return (n);
  35   │ }



   │ File: 2-binary_tree_insert_right.c
───────┼──────────────────────────────────────────────────────────────────────────────────────────────
   1   │ #include "binary_trees.h"
   2   │
   3   │ /**
   4   │  * binary_tree_insert_right - Insert a node as the right-child
   5   │  *                            of another in a binary tree.
   6   │  * @parent: A pointer to the node to insert the right-child in.
   7   │  * @value: The value to store in the new node.
   8   │  *
   9   │  * Return: If parent is NULL or an error occurs - NULL.
  10   │  *         Otherwise - a pointer to the new node.
  11   │  *
  12   │  * Description: If parent already has a right-child, the new node
  13   │  *              takes its place and the old right-child is set as
  14   │  *              the right-child of the new node.
  15   │  */
  16   │ binary_tree_t *binary_tree_insert_right(binary_tree_t *parent, int value)
  17   │ {
  18   │     binary_tree_t *new;
  19   │
  20   │     if (parent == NULL)
  21   │         return (NULL);
  22   │
  23   │     new = binary_tree_node(parent, value);
  24   │     if (new == NULL)
  25   │         return (NULL);
  26   │
  27   │     if (parent->right != NULL)
  28   │     {
  29   │         new->right = parent->right;
  30   │         parent->right->parent = new;
  31   │     }
  32   │     parent->right = new;
  33   │
  34   │     return (new);
  35   │ }





   │ File: 3-binary_tree_delete.c
───────┼──────────────────────────────────────────────────────────────────────────────────────────────
   1   │ #include "binary_trees.h"
   2   │
   3   │ /**
   4   │  * binary_tree_delete - Deletes a binary tree.
   5   │  * @tree: A pointer to the root node of the tree to delete.
   6   │  */
   7   │ void binary_tree_delete(binary_tree_t *tree)
   8   │ {
   9   │     if (tree != NULL)
  10   │     {
  11   │         binary_tree_delete(tree->left);
  12   │         binary_tree_delete(tree->right);
  13   │         free(tree);
  14   │     }
  15   │ }
───────┴──────────────────────────────────────────


────┬──────────────────────────────────────────────────────────────────────────────────────────────
       │ File: 4-binary_tree_is_leaf.c
───────┼──────────────────────────────────────────────────────────────────────────────────────────────
   1   │ #include "binary_trees.h"
   2   │
   3   │ /**
   4   │  * binary_tree_is_leaf - Checks if a node is a leaf of a binary tree.
   5   │  * @node: A pointer to the node to check.
   6   │  *
   7   │  * Return: If the node is a leaf - 1.
   8   │  *         Otherwise - 0.
   9   │  */
  10   │ int binary_tree_is_leaf(const binary_tree_t *node)
  11   │ {
  12   │     if (node == NULL || node->left != NULL || node->right != NULL)
  13   │         return (0);
  14   │
  15   │     return (1);
  16   │ }



 │ File: 5-binary_tree_is_root.c
───────┼──────────────────────────────────────────────────────────────────────────────────────────────
   1   │ #include "binary_trees.h"
   2   │
   3   │ /**
   4   │  * binary_tree_is_root - Checks if a node is a root of a binary tree.
   5   │  * @node: A pointer to the node to check.
   6   │  *
   7   │  * Return: If the node is a root - 1.
   8   │  *         Otherwise - 0.
   9   │  */
  10   │ int binary_tree_is_root(const binary_tree_t *node)
  11   │ {
  12   │     if (node == NULL || node->parent != NULL)
  13   │         return (0);
  14   │
  15   │     return (1);
  16   │ }
───────┴──────────────────────────────────────────────────────
