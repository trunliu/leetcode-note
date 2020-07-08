🎨剑指offer🎨
=======
* [1.数组中重复的数字](#数组中重复的数字)
* [2.二维数组中的查找](#二维数组中的查找)
* [3.替换空格](#替换空格)
* [4.从尾到头打印链表](#从尾到头打印链表)
* [5.重建二叉树](#重建二叉树)

数组中重复的数字
===========
[leetcode](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)找出数组中重复的数字。
在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。
### 解题思路1
* 建立哈希表或者数组记录数字出现次数，大于1就返回
```cpp
    int cnt[100000];
    int findRepeatNumber(vector<int>& nums) {
        for (int i = 0; i < nums.size(); ++i) {
            cnt[nums[i]]++;
            if (cnt[nums[i]] > 1) return nums[i];
        }
        return -1;
    }
```
### 解题思路2
* 先排序，遍历发现前后两个值一样，就是重复的数
```cpp
    int findRepeatNumber(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for (int i = 1; i < nums.size(); ++i) {
            if (nums[i] == nums[i -1 ]) return nums[i];
        }
        return -1;
    }
```

二维数组中的查找
====================
[leetcode](https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)在一个 n * m 的二维数组中，每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。
请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。
### 示例
```[
  [1,   4,  7, 11, 15],
  [2,   5,  8, 12, 19],
  [3,   6,  9, 16, 22],
  [10, 13, 14, 17, 24],
  [18, 21, 23, 26, 30]
]
```
### 解题思路
* 一般规律性很强的矩阵，数列，一定要找一个关键位置的数字，作为比较，用这个数字能够完成一部分筛选
* 例如本题的左下角，因为他是本行的最小值，所以如果`target`比他还要小，说明target一定不在此行。他又是本列的最大值，如果`target`比他还要大，那target一定不在这一列。通过这样可以筛选掉一行或者一列。
* 直到左下角的值等于target时结束。
```cpp
    bool findNumberIn2DArray(vector<vector<int>>& matrix, int target) {
        int row = matrix.size() - 1;
        int col = 0;
        while (row >= 0 && col < matrix[0].size()) {
            if (matrix[row][col] == target) return true;
            else if (matrix[row][col] > target) row--;
            else col++;
        }
        return false;
    }
```

替换空格
==============
[leetcode](https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/)请实现一个函数，把字符串 s 中的每个空格替换成"%20"。
### 示例 1：
```
输入：s = "We are happy."
输出："We%20are%20happy."
 ```
限制：
0 <= s 的长度 <= 10000

### 解题思路
* 方法1：遍历找到空格，删除空格，插入新字符
* 方法2：创建空字符，遇到空格就push新字符，非空格push正常字符。
```cpp
    string replaceSpace(string s) {
        for (int i = 0; s[i] != '\0'; ++i) {
            if (s[i] == ' ') {
                s.erase(i, 1);
                s.insert(i, string("%20"));
            }
        }
        return s;
    }
```
* 注意 `？a ：b`运算符中a和b必须属于同一类型，`“%20”`是const char*类型，而`ch`属于char类型，只能用以下形式来写。
```cpp
    string replaceSpace(string s) {
        string ans = "";
        for (char ch : s) 
            ans = (ch == ' ') ? ans + "%20" : ans + ch ;
        return ans;
    }
```

从尾到头打印链表
=====================
[leetcode](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/)输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。
### 解题思路
* 反转一般想到头插法或者栈实现
```cpp
   vector<int> reversePrint(ListNode* head) {
        ListNode* pre = NULL;
        ListNode* cur = head;
        while (cur != NULL) {
            ListNode * tmp = cur->next;
            cur->next = pre;
            pre = cur;
            cur = tmp;
        }
        vector<int> res;
        while (pre != NULL) {
            res.push_back(pre->val);
            pre = pre->next;
        }
        return res;
    } 
```

重建二叉树
==================
[leetcode](https://leetcode-cn.com/problems/zhong-jian-er-cha-shu-lcof/)输入某二叉树的前序遍历和中序遍历的结果，请重建该二叉树。假设输入的前序遍历和中序遍历的结果中都不含重复的数字。
```
前序遍历 preorder = [3,9,20,15,7]
中序遍历 inorder = [9,3,15,20,7]
```
返回如下的二叉树：
```
    3
   / \
  9  20
    /  \
   15   7
```
### 解题思路
* 新建/改变树结构的，在递归函数中一定要新建`root`结点并给`root->left`和`root->right`赋值。
* 用两个指针在树中遍历时：结束条件就是`left > right`,`left=right`是最后一个结点或者说叶子节点。
* 新建树一定是先序遍历，先建立根再建立左右子树，递归函数的参数表示，`pre_root`根结点再先序列中的索引，`in_left`中序列中左子树左边界 `in_right `中序列中右子树右边界。
* 根节点都是从先序中找，第一个结点一定是根，根后一个结点一定是左子树的根节点，根后+左子树大小+1就是右子树的根结点。
* 左子树的大小则通过中序遍历得到，因为在中序列中根节点左边全是左子树的结点。
* 因为涉及根据值取他得索引，所以事先要建立id映射表`idHash`。
```cpp
    unordered_map<int, int> idHash;
    vector<int> pre;
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        pre = preorder;
        for (int i = 0; i < inorder.size(); ++i) {
            idHash[inorder[i]] = i;
        }
        return buildTree(0, 0, inorder.size() - 1);
    }

    TreeNode* buildTree(int pre_root, int in_left, int in_right) {
        if (in_left > in_right) return NULL;
        TreeNode* root = new TreeNode(pre[pre_root]);
        int in_root = idHash[pre[pre_root]];
        root->left = buildTree(pre_root + 1, in_left, in_root - 1);
        root->right = buildTree(pre_root + in_root - in_left + 1, in_root + 1, in_right);
        return root;
    }
```