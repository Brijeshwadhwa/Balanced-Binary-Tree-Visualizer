# 🌳 Balanced Binary Tree Visualizer

A **3D-like interactive visualizer** to help users understand and check if a **Binary Tree is height-balanced**. Built for educational purposes with easy-to-use UI and in-depth explanations, making it perfect for students, educators, and anyone learning data structures!

![screenshot](./preview.png) <!-- Optional: Add a screenshot of your app -->

---

## 📌 What is a Balanced Binary Tree?

A **Balanced Binary Tree** is a binary tree where the depth difference between the left and right subtree of every node is no more than 1.

This is important because:
- It ensures tree operations like insertion, deletion, and lookup are efficient (`O(log n)`).
- Balanced trees avoid becoming skewed like linked lists.

---

## ✨ Features

- 🎨 Beautiful 3D-like tree rendering using SVG.
- 🌙 Dark mode aesthetic for better readability.
- 🧠 Visual check of whether a tree is balanced or not.
- 🧾 User-friendly input format (`level-order`, e.g., `1,2,3,null,4`).
- 📘 Complete C++ code and theory section for learning.
- ✅ Highlights balanced/unbalanced trees.
- 🧰 Pure HTML, CSS, and JavaScript — no libraries needed.
- 💾 Lightweight & works offline.

---

## 🛠️ Technologies Used

- HTML5
- CSS3
- JavaScript (Vanilla)
- SVG for tree visualization
- C++ (included in theory section)

---

## 🧠 How It Works (Logic)

### ✅ Balanced Tree Check Logic

```cpp
bool isBalanced(TreeNode* root) {
    return checkHeight(root) != -1;
}

int checkHeight(TreeNode* node) {
    if (node == NULL) return 0;

    int left = checkHeight(node->left);
    if (left == -1) return -1;

    int right = checkHeight(node->right);
    if (right == -1) return -1;

    if (abs(left - right) > 1) return -1;

    return max(left, right) + 1;
}
