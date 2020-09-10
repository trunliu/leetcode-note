🎨剑指offer🎨
==============
* [1.数组中重复的数字](#数组中重复的数字)
* [2.二维数组中的查找](#二维数组中的查找)
* [3.替换空格](#替换空格)
* [4.从尾到头打印链表](#从尾到头打印链表)
* [5.重建二叉树](#重建二叉树)
* [6.用两个栈实现队列](#用两个栈实现队列)
* [7.斐波那契数列](#斐波那契数列)
* [8.青蛙跳台阶问题](#青蛙跳台阶问题)
* [9.旋转数组的最小数字](#旋转数组的最小数字)
* [10.矩阵中的路径](#矩阵中的路径)
* [11.机器人的运动范围](#机器人的运动范围)
* [12.剪绳子](#剪绳子)
* [13.剪绳子II](#剪绳子II)
* [14.二进制中1的个数](#二进制中1的个数)
* [15.数值的整数次方](#数值的整数次方)
* [16.打印从1到最大的n位数](#打印从1到最大的n位数)
* [17.删除链表的节点](#删除链表的节点)
* [18.调整数组顺序使奇数位于偶数前面](#调整数组顺序使奇数位于偶数前面)
* [19.链表中倒数第k个节点](#链表中倒数第k个节点)
* [20.反转链表](#反转链表)
* [21.合并两个排序的链表](#合并两个排序的链表)
* [22.树的子结构](#树的子结构)
* [23.二叉树的镜像](#二叉树的镜像)
* [24.对称的二叉树](#对称的二叉树)
* [25.顺时针打印矩阵](#顺时针打印矩阵)
* [26.包含min函数的栈](#包含min函数的栈)
* [27.栈的压入、弹出序列](#栈的压入、弹出序列)
* [28.从上到下打印二叉树](#从上到下打印二叉树)
* [29.从上到下打印二叉树II](#从上到下打印二叉树II)
* [30.从上到下打印二叉树III](#从上到下打印二叉树III)
* [31.二叉搜索树的后序遍历序列](#二叉搜索树的后序遍历序列)
* [32.二叉树中和为某一值的路径](#二叉树中和为某一值的路径)
* [33.复杂链表的复制](#复杂链表的复制)
* [34.二叉搜索树与双向链表](#二叉搜索树与双向链表)
* [35.序列化二叉树](#序列化二叉树)
* [36.字符串的排列](#字符串的排列)
* [37.数组中出现次数超过一半的数字](#数组中出现次数超过一半的数字)
* [38.最小的k个数](#最小的k个数)
* [39.连续子数组的最大和](#连续子数组的最大和)
* [40.连续子数组的最大和]()
* [41.1～n整数中1出现的次数](#1～n整数中1出现的次数)
* [42.把数组排成最小的数](#把数组排成最小的数)
* [43.把数字翻译成字符串](#把数字翻译成字符串)
* [44.礼物的最大价值](#礼物的最大价值)
* [45.最长不含重复字符的子字符串](#最长不含重复字符的子字符串)
* [46.丑数](#丑数)
* [47.第一个只出现一次的字符](#第一个只出现一次的字符)
* [48.两个链表的第一个公共节点](#两个链表的第一个公共节点)
* [49.在排序数组中查找数字I](#在排序数组中查找数字I)
* [50.二叉搜索树的第k大节点](#二叉搜索树的第k大节点)
* [51.0～n-1中缺失的数字](#0～n-1中缺失的数字)
* [52.二叉树的深度](#二叉树的深度)
* [53.平衡二叉树](#平衡二叉树)
* [54.数组中数字出现的次数](#数组中数字出现的次数)
* [55.数组中数字出现的次数II](#数组中数字出现的次数II)
* [56.和为s的两个数字](#和为s的两个数字)
* [57.和为s的连续正数序列](#和为s的连续正数序列)
* [58.翻转单词顺序](#翻转单词顺序)
* [59.左旋转字符串](#左旋转字符串)
* [60.滑动窗口的最大值](#滑动窗口的最大值)
* [61.队列的最大值](#队列的最大值)
* [62.n个骰子的点数](#n个骰子的点数)
* [63.扑克牌中的顺子](#扑克牌中的顺子)
* [64.圆圈中最后剩下的数字](#圆圈中最后剩下的数字)
* [65.股票的最大利润](#股票的最大利润)
* [66.求1+2+…+n](#求1+2+…+n)
* [67.不用加减乘除做加法](#不用加减乘除做加法)
* [68.构建乘积数组](#构建乘积数组)
* [69.把字符串转换成整数](#把字符串转换成整数)
* [70.二叉搜索树的最近公共祖先](#二叉搜索树的最近公共祖先)
* [71.二叉树的最近公共祖先](#二叉树的最近公共祖先)
* [72.数字序列中某一位的数字](#数字序列中某一位的数字)


数组中重复的数字
================
[leetcode](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/) 找出数组中重复的数字。
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
```
[
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
* 方法二：因为是有序数组，就想到二分查找，每一行都使用二分法找target,但是此方法没有利用列得有序性  
```cpp
    bool findNumberIn2DArray(vector<vector<int>>& matrix, int target) {
        if (matrix.empty()) return false;
        int row = matrix.size();
        for (int i = 0; i < row; ++i) {
            if (find(matrix, i, target)) return true;
        }
        return false;
    }

    bool find(vector<vector<int>>& matrix, int row, int target) {
        if (matrix[row].empty()) return false;
        int left = 0, right = matrix[0].size() - 1;
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (matrix[row][mid] < target) left = mid + 1; 
            else if (matrix[row][mid] > target) right = mid;
            else if (matrix[row][mid] == target) return true;  
        }
        return matrix[row][left] == target;
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
* 方法2：使用额外空间，创建空字符，遇到空格就push新字符，非空格push正常字符。
* 注意 `？a ：b`运算符中a和b必须属于同一类型，`“%20”`是const char*类型，而`ch`属于char类型，只能用以下形式来写。
```cpp
    string replaceSpace(string s) {
        string ans = "";
        for (char ch : s) 
            ans = (ch == ' ') ? ans + "%20" : ans + ch ;
        return ans;
    }
```

```cpp
    string replaceSpace(string s) {
        int len = s.size();
        string res;
        for (int i = 0; i < len; ++i) {
            if (s[i] == ' ') {
                res += "%20";
            } else {
                res += s[i];
            }
        }
        return res;
    }
```
* 如果面试官要求不能使用额外得空间，实现原地修改，可以先统计空格数量，再原字符串后添加足够长得空间
```cpp
    string replaceSpace(string s) {
        int len = s.size();
        int cnt = 0;
        for (int i = 0; i < len; ++i) {
            if (s[i] == ' ') cnt++;
        }
        s += string(cnt * 2, ' ');
        int p1 = s.size() - 1;
        int p2 = len - 1;
        while (p2 >= 0) {
            if (s[p2] == ' ') {
                s[p1--] = '0';
                s[p1--] = '2';
                s[p1--] = '%';
            } else {
                s[p1--] = s[p2];
            }
            p2--;
        }
        return s;
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
* 用栈反转
```cpp
    vector<int> reversePrint(ListNode* head) {
        stack<int> sck;
        while (head) {
            sck.push(head->val);
            head = head->next;
        }
        vector<int> res;
        while (!sck.empty()) {
            res.push_back(sck.top());
            sck.pop(); 
        }
        return res;
    }
```
* 最low 的方法是用遍历链表，输出每个结点的值到数组中，然后用reverse()进行反转。  



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
		// 左节点个数是：in_root - in_left + 1 经常容易写错
        root->right = buildTree(pre_root + in_root - in_left + 1, in_root + 1, in_right);
        return root;
    }
```

用两个栈实现队列
====================
[leetcode](https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/)
用两个栈实现一个队列。队列的声明如下，请实现它的两个函数 appendTail 和 deleteHead ，分别完成在队列尾部插入整数和在队列头部删除整数的功能。(若队列中没有元素，deleteHead 操作返回 -1 )
### 解题思路
* 插入时，按正常入栈，但弹出时需要从最先入栈的即栈底开始，所以要用到辅助栈，将栈底元素倒出来到辅助栈的栈顶
* 只有当辅助栈的元素全部弹空后，再开始新一轮从数据栈往辅助栈倒
* 两个栈都为空时，才是真的空了。
```cpp
    stack<int> sck1;
    stack<int> sck2;
    CQueue() { }
    
     void appendTail(int value) {
        sck1.push(value);
    }
    
    int deleteHead() {
        if (sck2.empty() && sck1.empty()) return -1;
        if (sck2.empty()) {
            while (!sck1.empty()) {
                sck2.push(sck1.top());
                sck1.pop();
            }
        }
        int front = sck2.top();
        sck2.pop();
        return front;
    }
```

斐波那契数列
===================
[leetcode](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/)
写一个函数，输入 n ，求斐波那契（Fibonacci）数列的第 n 项。斐波那契数列的定义如下,斐波那契数列由 0 和 1 开始，之后的斐波那契数就是由之前的两数相加而得出。
答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。
### 解题思路
* 经典的动规问题，出了前两个元素，其他任意一个元素值都与他的前两个元素相关，所以状态方程为：`dp[i] = dp[i -1] + dp[i -2]`
* 注意答案要取模
```cpp
    int fib(int n) {
        int dp[n + 1];
        for (int i = 0; i <= n; ++i) {
            if (i == 0) dp[0] = 0;
            else if (i == 1) dp[1] = 1;
            else dp[i] = (dp[i - 1]  + dp[i - 2]) % 1000000007;
        }
        return dp[n];
    }
```
* 如果面试管要求较少的空间，可以只需要三个变量，实时记录当前值，他的前一个值和前二个值，每次遍历都进行一个更新。
```cpp
    int fib(int n) {
        int first = 0, second = 1;
        int ans = n == 0 ? 0 : 1;
        for (int i = 2; i <= n; ++i) {
            ans = (first + second) % 1000000007;
            first = second;
            second = ans;
        }
        return ans;
    }
```

青蛙跳台阶问题
============
[leetcode](https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/)
一只青蛙一次可以跳上1级台阶，也可以跳上2级台阶。求该青蛙跳上一个 n 级的台阶总共有多少种跳法。
答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。
### 解题思路
* PS:为什么要模1000000007（跟我念，一，八个零，七）,int64位的最大值为2^63-1，用最大值模1000000007的结果求平方，不会在int64中溢出。
所以在大数相乘问题中,相乘时两边都对1000000007取模，保存在int64里面不会溢出.
* 建立dp数组建立跳到当前台阶的方法数，那么对于任意台阶，可以从他前一个台阶或者前两个台阶跳到，状态方程为：'dp[i] = dp[i - 1] + dp[i - 2]'  
```cpp
    int numWays(int n) {
        int dp[n + 1];
        for (int i = 0; i <= n; ++i) {
            if (i == 0) dp[0] = 1;
            else if (i == 1) dp[1] = 1;
            else if (i == 2) dp[2] = 2;
            else dp[i] = (dp[i - 1] + dp[i - 2]) % 1000000007;
        }
        return dp[n];
    }
```
* 节省空间的做法：
```cpp
    int numWays(int n) {
        if (n == 0 || n == 1) return 1;
        if (n == 2) return 2;
        int first = 1;
        int second = 2;
        int res = 0;
        for (int i = 2; i < n; ++i) {
            res = (first + second) % 1000000007;
            first = second;
            second = res;
        }
        return res;
    }
```

旋转数组的最小数字
==========
[leetcode](https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/)
把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。输入一个递增排序的数组的一个旋转，输出旋转数组的最小元素。例如，数组 [3,4,5,1,2] 为 [1,2,3,4,5] 的一个旋转，该数组的最小值为1。  
### 解题思路
* 典型的二分查找，要查找的数左右两边的特点，他的左边都是大于数组的最后一个数，他的右边都是小于数组最后一个数。
* 本题的不同之处在于存在重复数字，所以会出现mid所指与right所指之数相等，导致无法判断最小值出现在mid左边还是右边，因此需要删除一个重复值，暴力的缩小范围。`right--`
```cpp
    int minArray(vector<int>& nums) {
        int left = 0;
        int right = nums.size() - 1;
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] > nums[right]) left = mid + 1;
            else if (nums[mid] < nums[right]) right = mid; 
            else if (nums[mid] == nums[right]) right--;                           
        }
        return nums[left];
    }  
```
* 暴力法：遍历整个数组，如果发现后面一个数小于前面一个数，说明找到了分界点。
* 如果没有找到分界点，说明整个数组都是一个数重复，就返回第一个数即可。
```cpp
    int minArray(vector<int>& numbers) {
        for (int i = 0; i + 1 < numbers.size(); ++i) {
            if (numbers[i] > numbers[i + 1]) 
                return numbers[i + 1];
        }
        return numbers[0];
    }
```

矩阵中的路径
=================
[leetcode](https://leetcode-cn.com/problems/ju-zhen-zhong-de-lu-jing-lcof/)
请设计一个函数，用来判断在一个矩阵中是否存在一条包含某字符串所有字符的路径。路径可以从矩阵中的任意一格开始，每一步可以在矩阵中向左、右、上、下移动一格。如果一条路径经过了矩阵的某一格，那么该路径不能再次进入该格子。例如，在下面的3×4的矩阵中包含一条字符串“bfce”的路径（路径中的字母用加粗标出）。
[["a","b","c","e"],
["s","f","c","s"],
["a","d","e","e"]]
但矩阵中不包含字符串“abfb”的路径，因为字符串的第一个字符b占据了矩阵中的第一行第二个格子之后，路径不能再次进入这个格子。
### 解题思路
* 本题第一想到DFS或BFS
* 使用DFS时应该注意递归结束条件有哪些：坐标越界、已经访问过、递归的深度超过word长度、字符不等于word对应位置的字符。
* 这里介绍另一种标记已访问过的方法：就是访问时将数组中的数字提取出来，原位置用其他不常用字符代替，因为递归时只访问word中字符，所以访问过的一定不会再访问，递归结束后记得回复原样（不恢复也行）
```cpp
public:
    bool exist(vector<vector<char>>& board, string word) {
        for (int i = 0; i < board.size(); i++) {
            for (int j = 0; j < board[0].size(); j++) {
                if (dfs(board, word, i, j, 0))
                    return true;
            }
        }
        return false;
    }
private:
    bool dfs(vector<vector<char>>& b, string& w, int i, int j, int k) {
        if (i >= b.size() || i < 0 || j >= b[0].size() || j < 0 || b[i][j] != w[k])
            return false;
        if (k == w.length() - 1)
            return true;
        char temp = b[i][j];
        b[i][j] = '/';
        int dx[4] = {-1, 0, 1, 0}, dy[4] = {0, 1, 0, -1};
        for (int q = 0; q < 4; q ++ ) {
            int m = i + dx[q], n = j + dy[q];
            if (dfs(b, w, m, n, k + 1)) return true;
        }
        b[i][j] = temp;
        return false;
    }
```
* 第二版解题思路，类似此类问题：通过dfs在多条路径中寻找其中一条满足条件的路径。
* 注意：第一次通过遍历先发现头节点，再根据次节点展开深度递归，记录路径长度或者储存路径信息的变量都要再每次dfs前重新定义。
* 注意：每次递归完要恢复isVis标志位。只有一种情况不需要恢复就是，只从一个节点开始dfs，只需要找到一条满足的路径即可，不需要回溯。
* dfs模板：先判断是否已经访问，再写递归结束的条件，最后只有满足一定条件的子节点才进行dfs。
```cpp
    int off[4][2] = {{1,0}, {-1,0}, {0, 1}, {0, -1}};
    vector<vector<bool>> isVis;
    string word;
    vector<vector<char>> board;
    int row;
    int col;
    bool exist(vector<vector<char>>& board, string word) {
        row = board.size();
        col = board[0].size();
        this->isVis.resize(row, vector<bool>(col, false));
        this->board = board;
        this->word = word;
        
        for (int i = 0; i < row; ++i) {
            for (int j = 0; j < col; ++j) {
                if (board[i][j] == word[0]) {
                    int depth = 0;
                    if(dfs(i, j, depth)) return true;
                }  
            }
        }
        return false;
    }

    bool dfs(int x, int y, int depth) {
        if (isVis[x][y]) return false;
        isVis[x][y] = true;
        cout << board[x][y];
        if (depth == word.size() - 1) return true;
        for (int i = 0; i < 4; ++i) {
            int m = x + off[i][0];
            int n = y + off[i][1];
            if (m < row && m >= 0 && n < col && n >= 0 && board[m][n] == word[depth + 1])
                if (dfs(m, n, depth + 1)) return true;
        }
        isVis[x][y] = false;
        return false;
    }
```


机器人的运动范围
======================
[leetcode](https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/)
地上有一个m行n列的方格，从坐标 [0,0] 到坐标 [m-1,n-1] 。一个机器人从坐标 [0, 0] 的格子开始移动，它每次可以向左、右、上、下移动一格（不能移动到方格外），也不能进入行坐标和列坐标的数位之和大于k的格子。例如，当k为18时，机器人能够进入方格 [35, 37] ，因为3+5+3+7=18。但它不能进入方格 [35, 38]，因为3+5+3+8=19。请问该机器人能够到达多少个格子？
### 解题思路
* 此题的难度在于理解上面，并不是暴力的遍历全部结点，判断哪个符合条件，因为题目时运动范围即，所以符合要求的结点都时连接在一起的。
* 因为数组中的值仅仅为两位数，因此' x / 10 + x %10'就是个位与十位的数位和
* 这里用了一个二维数组记录访问过的结点，一定要初始化二维数组。
* 因为本题求得是机器人得运动范围，不是求某一最长得路径，因此再dfs结束后不需要回复isVis数组。
```cpp
    int cnt = 0;
    int m, n, k;
    int off[4][2] = {{0, 1}, {0, -1}, {1, 0}, {-1, 0}};
    bool** isVis;
    
    int movingCount(int m, int n, int k) {
        this->m = m;
        this->n = n;
        this->k = k;

        isVis = new bool*[m];
        for (int i = 0; i < m; ++i) {
            isVis[i] = new bool[n];
            memset(isVis[i], 0, n * sizeof(bool));
        }

        dfs(0, 0, isVis);
        return cnt;
    }
    void dfs(int i, int j, bool** isVis) {
        if (isVis[i][j]) return;
        isVis[i][j] = true;
        cnt++;
        for (int z = 0; z < 4; ++z) {
            int x = i + off[z][0];
            int y = j + off[z][1];
            if (x >= 0 && y >= 0 && x < m && y < n &&
               (x / 10 + x % 10 + y / 10 + y % 10 <= k)) 
                    dfs(x, y, isVis);      
        }
        return;
    }
```

剪绳子
================
[leetcode](https://leetcode-cn.com/problems/jian-sheng-zi-lcof/)
给你一根长度为 n 的绳子，请把绳子剪成整数长度的 m 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 k[0],k[1]...k[m-1] 。请问 k[0]*k[1]*...*k[m-1] 可能的最大乘积是多少？例如，当绳子的长度是8时，我们把它剪成长度分别为2、3、3的三段，此时得到的最大乘积是18。
###  示例
```
输入: 2
输出: 1
解释: 2 = 1 + 1, 1 × 1 = 1

输入: 10
输出: 36
解释: 10 = 3 + 3 + 4, 3 × 3 × 4 = 36
```
### 解题思路
* 贪心+暴力解决  
* 要想积最大，每段长度都尽量相等或接近就行，首先想到用平均值avg，如果平均下来有剩余值，就降剩余值再平均前面每个值上，就变avg + 1，所以最终分段完每段的长度不是avg就是avg + 1
* 设分了m段,那么余数有多少，就有多少个avg + 1,剩下的就是avg
* pow(int num, int exp);求乘方函数。
```cpp
    int cuttingRope(int n) {
        int res = 0;
        for (int m = 2; m <=n; ++m) {
            int avg = n / m; 
            int sum = n % m ? pow(avg, m - n % m) * pow(avg + 1, n % m) : pow(avg, m);
            res = max(res, sum);
        }
        return res;
    }
```

剪绳子II
==================
[leetcode](https://leetcode-cn.com/problems/jian-sheng-zi-ii-lcof/)
给你一根长度为 n 的绳子，请把绳子剪成整数长度的 m 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 k[0],k[1]...k[m - 1] 。请问 k[0]*k[1]*...*k[m - 1] 可能的最大乘积是多少？例如，当绳子的长度是8时，我们把它剪成长度分别为2、3、3的三段，此时得到的最大乘积是18。
答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。
### 解题思路
* 本题与上一题得区别在于存在大数操作，`2 <= n <= 1000`
* 对于本题需要了解数学知识，要想使成绩最大化，就需要将绳子尽可能的多分段，因此每段长度有，1，2，3中长度考虑，1显然不行，2或3中，3更合适，因此此题就变为求3的幂操作。
* 幂操作因为指数级别的增加，很容易溢出int32甚至int64，所以为了不让溢出，就需要对幂结果求余，采用分割后分别求余。
* 循环求幂：大数取余满足分配律，`(xy)⊙p=[(x⊙p)(y⊙p)]⊙p`
```cpp
    int cuttingRope(int n) {
        if (n == 2 || n == 3) return n -1;
        long res = 1;
        while (n > 4) {
            res = res * 3 % 1000000007;
            n -= 3;
        }
        return res * n % 1000000007;
    }
```
* 方法二，用贪心+快速幂指法
```cpp
    int cuttingRope(int n) {
        if (n == 2 || n == 3) return n - 1;
        int a = n / 3;
        int b = n % 3;
        if (b == 2) return quickPow(3, a) * 2 % 1000000007;
        else return quickPow(3, a - 1) * (b + 3) % 1000000007; 
    }

    long quickPow(int x, int n) {
        long res = 1;
        long t = x;
        while (n) {
            if (n & 1) 
                res = res * t % 1000000007;
            t = t * t % 1000000007;
            n /= 2;
        }
        return res;
    }
```

二进制中1的个数
====================
请实现一个函数，输入一个整数，输出该数二进制表示中 1 的个数。例如，把 9 表示成二进制是 1001，有 2 位是 1。因此，如果输入 9，则该函数输出 2。
### 解题思路
* 三种方法：1、掩码为1，让数子`(num & 1)` 判断num二进制形式的最后一位是否是1，`num >>= 1`让num二进制数右移一位，就可以实现逐位判断。
* 2、方法一通过不断右移num，还可以不断左移掩码1来判断
* 3、 反转num的最后一位，记录反转次数 反转'n &= n -1'
```cpp
    int hammingWeight(uint32_t n) {
        int cnt = 0;
        while (n) {
            if (n & 1) cnt++;
            n >>= 1;
        }
        return cnt;
    }
```

```cpp
    int hammingWeight(uint32_t n) {
        uint32_t mask = 1;
        int i = 32;
        int cnt = 0;
        while (i--) {
            if (n & mask) cnt++;
            mask <<= 1;
        }
        return cnt;
    }
```

```cpp
    int hammingWeight(uint32_t n) {
        int cnt = 0;
        while (n) {
            n &= n - 1;
            cnt++;
        }
        return cnt;
    }
```

数值的整数次方
==================
[leetcode](https://leetcode-cn.com/problems/shu-zhi-de-zheng-shu-ci-fang-lcof/)
实现函数double Power(double base, int exponent)，求base的exponent次方。不得使用库函数，同时不需要考虑大数问题。
### 解题思路 
* 如果采用whie(exp--)根据指数个数不断求积的方式计算，对于指数很大的数可能会超时，因此使用快速求幂算法
* 核心就是通过指数的二进制形式，将指数进行的分解，例如（`x^9` 指数为`9`，二进制是:1001, 那么`9 = 2^3 + 2^0`, 所以`x^9 = x^8 * x^1` )
```cpp
    double myPow(double x, int n) {
        if (n == 0) return 1;
        bool isPositive = true;
        long t = n;
        if (t < 0) t = -t, isPositive = false;
        double res = 1;
        while (t) {
            if (t & 1) res *= x; 
            x *= x;
            t >>= 1; 
        }
        return isPositive ? res : (1 / res);
    }

```

* 其中用到了用移位`t >>= 1`,
* 注意能够使用的前提是`t`不能是负数（因为负数用的是补码），因此之前现做绝对化处理,但是力扣的用例中使用了`n = -2147483648`这个数，int的取值范围是-2147483648到2147483647，但-2147483648取绝对值2147483648超出int范围，所以需要long去接他。
* 可以用除法 n /= 2来代替，就不会有如上问题,也不同考虑符数问题
```cpp
    double myPow(double x, int n) {
        double res = 1;
        int t = n;
        while (n) {
            if (n & 1) res *= x;
            x *= x;
            n /= 2;
        }
        return t > 0 ? res : 1 / res;
    }
```

* 使用递归思想，易理解,因为只有`n`在递归中发送变化，因此结束条件只考虑n的情况。
```cpp
    double myPow(double x, int n) {
        if (n == 0) return 1;
        if (n == 1) return x;
        if (n == -1) return 1 / x;
        double half = myPow(x, n / 2);
        double mod = myPow(x, n % 2);
        return half * half * mod;
    }
```


打印从1到最大的n位数
========================
[leetcode](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)
输入数字 n，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。
### 示例
```
输入: n = 1
输出: [1,2,3,4,5,6,7,8,9]
```
### 解题思路
* 此题相对书上的做了简化，因为已经给出返回值是int型，所以用例中不会有大数，就简单很多
* 关键在于找到最大值，然后遍历打印即可
* 可以用pow(10, n)来确定最大边界。
* 我这里提供另一种算法：例如3位数，那么最大值就是999，4位数最大9999。
```cpp
    vector<int> printNumbers(int n) {
        int cnt = 0;
        vector<int> res;
        while (n--) {   
            cnt = cnt * 10 + 9;
        }
        for (int i = 1; i <= cnt; ++i) {
            res.push_back(i);
        }
        return res;
    }
```

删除链表的节点
====================
[leetcode](https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/)给定单向链表的头指针和一个要删除的节点的值，定义一个函数删除该节点。
返回删除后的链表的头节点。
* 删除某个结点的前提一定是找到他的前驱和要删除的结点，因此需要两个指针。
* 改变链表的操作，有可能会删除第一个结点，因此需要一个头节点作为第一个结点的前驱，来统一化操作。
```cpp
    ListNode* deleteNode(ListNode* head, int val) {
        ListNode* dummy = new ListNode(-1);
        dummy->next = head;
        ListNode* cur = head;
        ListNode* pre = dummy;
        while (cur->val != val) {
            cur = cur->next;
            pre = pre->next;
        }
        pre->next = cur->next;
        return dummy->next;
    }

```

调整数组顺序使奇数位于偶数前面
===============================
[leetcode](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)
输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有奇数位于数组的前半部分，所有偶数位于数组的后半部分。
### 解题思路
* 思路来自于快排的挖坑法，定义两个头尾指针，把最后一个数挖走，然后left指针遍历直到发现一个偶数，就把这个偶数挖走放到最后的坑里，再用right往前遍历，直到发现一个奇数，挖走放到前面那个坑里，直到俩个指针相遇，把坑不上即可。
* 注意：如果将第一个数挖走，一开始就要从末尾开始遍历，如果挖走最后一个数，就要从左先开始遍历。
```cpp
    vector<int> exchange(vector<int>& nums) {
        if (nums.size() == 0) return {};
        int left = 0;
        int right = nums.size() - 1;
        int temp = nums[right];
        while (left < right) {
            while ((nums[left] & 1) == 1 && left < right) left++;
            nums[right] = nums[left];
            while ((nums[right] & 1) == 0 && left < right) right--;
            nums[left] = nums[right];
        }
        nums[left] = temp;
        return nums;
    }
```

* 改进版,不需要挖坑了，而且只交换一次。
```cpp
    vector<int> exchange(vector<int>& nums) {
        if (nums.empty()) return {};
        int left = 0 ,right = nums.size() - 1;
        while (left < right) {
            while (left < right && (nums[right] & 1) == 0) right--;
            while (left < right && (nums[left] & 1) == 1) left++;
            swap(nums[left++], nums[right--]); 
        }
        return nums;
    }
```

链表中倒数第k个节点
======================
[leetcode](https://leetcode-cn.com/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/)输入一个链表，输出该链表中倒数第k个节点。为了符合大多数人的习惯，本题从1开始计数，即链表的尾节点是倒数第1个节点。例如，一个链表有6个节点，从头节点开始，它们的值依次是1、2、3、4、5、6。这个链表的倒数第3个节点是值为4的节点。
### 解题思路
* 快慢指针法，让快指针遍历到结尾`null`时，慢指针正好指向倒数第k个结点。
* 因为要删出结点必须要前驱，所以添加一个头结点`dummy`，方便删第一个结点。
* 注意此题返回的是删除后剩余的链，
```cpp
    ListNode* getKthFromEnd(ListNode* head, int k) {
        ListNode* dummy = new ListNode(-1);
        dummy->next = head;
        ListNode* fast = dummy;
        ListNode* slow = dummy;
        while (k--) {
            fast = fast->next;
        }
        while (fast) {
            fast = fast->next;
            slow = slow->next;
        }
        return slow;
    }
```

反转链表
===============
[leetcode](https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/)定义一个函数，输入一个链表的头节点，反转该链表并输出反转后链表的头节点。
### 解题思路
* 方法1：头插法反转
```cpp
    ListNode* reverseList(ListNode* head) {
        ListNode* pre = NULL;
        ListNode* cur = head;
        while (cur) {
            ListNode* tmp = cur->next;
            cur->next = pre;
            pre = cur;
            cur = tmp;
        }
        return pre;
    }
```
*  方法2：用栈反转:首先遍历链表，1、把每个结点入栈，2、然后再循环出栈链接到上一个结点，3、更新当前指针。
```cpp
    ListNode* reverseList(ListNode* head) {
        if (!head) return NULL;
        stack<ListNode*> sck;
        ListNode* cur = head;
        while (cur) {
            sck.push(cur);
            cur = cur->next;
        }

        ListNode* pre = sck.top();
        ListNode* curr = sck.top();
        sck.pop();
        while (!sck.empty()) {
            curr->next = sck.top();
            sck.pop();
            curr = curr->next;
        }
        curr->next = NULL;
        return pre;
    }
```

合并两个排序的链表
====================
[leetcode](https://leetcode-cn.com/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/)
输入两个递增排序的链表，合并这两个链表并使新链表中的节点仍然是递增排序的。
### 示例 
```
输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4
```
### 解题思路
* 合并需要三个指针，一个指向l1的`p1`,指向l2的`p2`，遍历合并后链表的`cur`指针,新链表的头指针`pre`。
* 同时遍历两个链表，当有一个链表遍历结束时退出循环，将另一个链表剩下的直接接上新链表。
```cpp
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        ListNode* p1 = l1;
        ListNode* p2 = l2;
        ListNode* pre = new ListNode(-1);
        ListNode* cur = pre;
        while (p1 != NULL && p2 != NULL) {
            if (p1->val <= p2->val){
                cur->next = p1;
                p1 = p1->next;
            } else {
                cur->next = p2;
                p2 = p2->next;
            }
            cur = cur->next;
        }
        cur->next = p1 == NULL ? p2 : p1;
        return pre->next;
    }
```

* 一样的思路另一种写法，区别在于while循环大判断是`||`或.
```cpp
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        ListNode* p1 = l1, p2 = l2;
        ListNode* dummy = new ListNode(-1);
        ListNode* cur = dummy;
        while (p1 || p2) {
            if (p1 == NULL) { 
                cur->next = p2;
                break;
            }
            if (p2 == NULL) {
                cur->next = p1;
                break;
            }   
            if (p1->val <= p2->val) {
                cur->next = p1;
                p1 = p1->next;
            } else {
                cur->next = p2;
                p2 = p2->next;
            }
            cur = cur->next;
        }
        return dummy->next;
    }
```

* 递归思想:先了解函数的意义是合并两个链表并返回合并后的头部节点，其次返回条件，函数的两个参数都会在
递归过程中发生变化，因此结束条件有两个，其中一个为`null`表示其中一条遍历结束，直接返回另一条链表。
```cpp
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if (l1 == NULL) return l2;
        if (l2 == NULL) return l1;

        if (l1->val <= l2->val) {
            l1->next = mergeTwoLists(l1->next, l2);
            return l1;
        } else {
            l2->next = mergeTwoLists(l1, l2->next);
            return l2;
        }
    }
```

树的子结构
================
[leetcode](https://leetcode-cn.com/problems/shu-de-zi-jie-gou-lcof/)输入两棵二叉树A和B，判断B是不是A的子结构。(约定空树不是任意一个树的子结构)
B是A的子结构， 即 A中有出现和B相同的结构和节点值。
### 示例
```
例如:
给定的树 A:

     3
    / \
   4   5
  / \
 1   2
给定的树 B：

   4 
  /
 1
返回 true，因为 B 与 A 的一个子树拥有相同的结构和节点值。

```
### 解题思路
* 首先需要遍历整个A树每个结点，来跟跟B进行对比，所以需要两个递归，第一个递归用于遍历整个A树，第二个递归用于对比两个树。
* 第一个递归结束条件，如果A树的结点遍历到结尾`null`说明还没发现子树，因此返回false，再根据题意空树`B == null`不属于任何子树
* 第二个递归判断两个树是否相等或者B是否属于A，当同时遍历两个树的结点，如果有不相等的结点一定不是，结束条件：当`(A == NULL && B == NULL)`即两个树同时遍历结束 ，说明A和B完全相等，
如果A先结束，说明A属于B，返回`false`，B先结束说吧B属于A，B是A的子树，返回`true`
```cpp
    bool isSubStructure(TreeNode* A, TreeNode* B) {
        if (A == NULL || B == NULL) return false;   // 空树不算任何子树
        if (isEqual(A, B)) return true;
        return  isSubStructure(A->left, B) || isSubStructure(A->right, B);
    }

    bool isEqual(TreeNode* A, TreeNode* B) {
        if (A == NULL && B == NULL) return true;    // 都刚好遍历完
        if (B == NULL) return true;     // B遍历到尾部，A下面还有
        if (A == NULL) return false;    // B还没有遍历完， A下面就没了
        if (A->val != B->val) return false;     
        return isEqual(A->left, B->left) && isEqual(A->right, B->right); 
    }
```

二叉树的镜像
===================
[leetcode](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)
请完成一个函数，输入一个二叉树，该函数输出它的镜像。
### 解题思路
* 对于改变树结构的递归，其中一定有`root->left =` 和`root->right = `左右子树重新赋值的操作。
* 函数意义是返回反转后的根结点。
```cpp
    TreeNode* mirrorTree(TreeNode* root) {
        if (root == NULL) return NULL;
        TreeNode* tmp = mirrorTree(root->left);
        root->left = mirrorTree(root->right);
        root->right = tmp;
        return root;
    }
```

* 能用递归就能用迭代法，对于深度递归一般使用栈，又由于翻转操作，我们需要先得到根节点，才能反转他的左右子树，
因此采用栈数据结构的前序遍历的迭代法，先右节点入栈。交换操作也可以使用`swap()`代替。
```cpp
    TreeNode* mirrorTree(TreeNode* root) {
        if (!root) return NULL;
        stack<TreeNode*> sck;
        sck.push(root);
        TreeNode* cur = NULL;
        while (!sck.empty()) {
            cur = sck.top();
            sck.pop();       
            // swap(cur->left, cur->right)
            TreeNode* tmp = cur->left;
            cur->left = cur->right;
            cur->right = tmp;
            if (cur->right) sck.push(cur->right);
            if (cur->left) sck.push(cur->left); 
        }
        return root;
    }
```

对称的二叉树
=================
[leetcode](https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/)
请实现一个函数，用来判断一棵二叉树是不是对称的。如果一棵二叉树和它的镜像一样，那么它是对称的。
例如，二叉树 [1,2,2,3,4,4,3] 是对称的。
```
    1
   / \
  2   2
 / \ / \
3  4 4  3
```
### 解题思路
* 一定需要两个指针，一个递归遍历左子树，一个遍历右子树，再进行左右子树交叉结点值的对比，当发现结点不相等时返回false
* 注意遍历到结尾`null`时的处理，都是null也属于对称。
```cpp
    bool isSymmetric(TreeNode* root) {
        if(!root) return true;
        return isSymmetric(root->left, root->right);
    }

    bool isSymmetric(TreeNode* left, TreeNode* right) {
        if (left == NULL && right == NULL) return true;
        if (left == NULL || right == NULL || left->val != right->val) return false;
        return isSymmetric(left->left, right->right) && isSymmetric(left->right, right->left) ;
    }
```

顺时针打印矩阵
====================
[leetcode](https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)
输入一个矩阵，按照从外向里以顺时针的顺序依次打印出每一个数字。
### 解题思路
* 定义四个边界，上下左右，每打印一圈四个边界就向里面缩小一个单位，同时为了保证每次打印都是从0下标开始的，所以一行n个元素只打印前n个，一列n个元素也只打印前n个。
* 循环的结束条件：当上下边界重合，或者左右边界重合时，说明就剩中间一行或者一列或者一个元素三种情况未遍历打印，需要单独考虑。
* 上下左右边界都重合说明就剩一个元素。
```cpp
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        if (matrix.empty()) return {};
        vector<int> res;
        int top = 0, bottom = matrix.size() - 1;
        int left = 0, right = matrix[0].size() - 1;
        while (left < right && top < bottom) {
            for (int i = left; i < right; ++i) res.push_back(matrix[top][i]);
            for (int i = top; i < bottom; ++i) res.push_back(matrix[i][right]);
            for (int i = right; i > left; --i) res.push_back(matrix[bottom][i]);
            for (int i = bottom; i > top; --i) res.push_back(matrix[i][left]);
            left++, right--;
            top++, bottom--;
        }
        if (left == right){ // 还剩一列 或者一个
            for (int i = top; i <= bottom; ++i) res.push_back(matrix[i][left]);
        } else if (top == bottom) { // 还剩一行
            for (int i = left; i <= right; ++i) res.push_back(matrix[top][i]);
        }
        return res;
    }
```

包含min函数的栈
====================
[leetcode](https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/)
定义栈的数据结构，请在该类型中实现一个能够得到栈的最小元素的 min 函数在该栈中，调用 min、push 及 pop 的时间复杂度都是 O(1)。
### 解题思路
* 入栈时比较当前元素与最小栈栈顶元素，更小则加入最小栈中。
* 出栈时需要考虑当前栈顶的元素是不是最小值，如果是，则最小栈也需要弹出，不是则只弹出数据栈栈顶的元素。
```cpp
    stack<int> dataSck;
    stack<int> minSck;
    MinStack() {}
    
    void push(int x) {
        dataSck.push(x);
        if (minSck.empty()) {
            minSck.push(x);
        } else {
            if (x <= minSck.top())
                minSck.push(x);
        }
    }
    
    void pop() {
        if (dataSck.empty()) return;
        if (dataSck.top() == minSck.top()) {
            dataSck.pop();
            minSck.pop();
        } else {
            dataSck.pop();
        }
    }
    
    int top() {
        return dataSck.top();
    }
    
    int min() {
        return minSck.top();
    }
```

栈的压入、弹出序列
=======================
[leetcode](https://leetcode-cn.com/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/)
输入两个整数序列，第一个序列表示栈的压入顺序，请判断第二个序列是否为该栈的弹出顺序。假设压入栈的所有数字均不相等。例如，序列 {1,2,3,4,5} 是某栈的压栈序列，序列 {4,5,3,2,1} 是该压栈序列对应的一个弹出序列，但 {4,3,5,1,2} 就不可能是该压栈序列的弹出序列。
### 解题思路
* 根据弹出数组来模拟整个入栈和出栈的操作。
* 因为入栈的顺序是固定的，因此根据push数组来遍历入栈，但是出栈可能发生再任意一个结点当中，但是一定按照pop数组进行的。
* 因此只要当入栈的元素即栈顶与pop数组第一个元素相等时，代表这个刚入栈的元素要出栈了，出栈后pop数组也要往后遍历一位。
* 用while循环是因为模拟连续出栈的操作，因为有可能一次入栈后，出现连续多次出栈操作。
* 后面只要入栈的元素即栈顶元素与pop数组相等时，就代表该出栈了。
* 最后如果栈空代表pop数组满足栈的操作。
```cpp
    bool validateStackSequences(vector<int>& pushed, vector<int>& popped) {
        stack<int> sck;
        int j = 0;
        for (auto num : pushed) {
            sck.push(num);
            while (!sck.empty() && sck.top() == popped[j]) {
                sck.pop();
                j++;
            }
        }
        return sck.empty();
    }
```

从上到下打印二叉树
=======================
[leetcode](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/)从上到下打印出二叉树的每个节点，同一层的节点按照从左到右的顺序打印。
### 解题思路
* 典型的层序遍历，使用到了队列,遍历一个结点就把他的子结点加入队列即可。
```cpp
    vector<int> levelOrder(TreeNode* root) {
        if (root == NULL) return {};
        queue<TreeNode*> que;
        que.push(root);
        TreeNode* cur = NULL;
        vector<int> res;
        while (!que.empty()) {
            cur = que.front();
            que.pop();
            res.push_back(cur->val);
            if (cur->left) que.push(cur->left);
            if (cur->right) que.push(cur->right);
        }
        return res;
    }
```
* 队列可以实现先进先出，同样用链表也可以代替队列
```cpp
    vector<int> levelOrder(TreeNode* root) {
        if (root == NULL) return {};
        vector<int> res;
        list<TreeNode*> List;
        List.push_back(root);
        TreeNode* cur = NULL;
        while (!List.empty()) {
            cur = List.front();
            List.pop_front();
            res.push_back(cur->val);
            if (cur->left) List.push_back(cur->left);
            if (cur->right) List.push_back(cur->right);
        }
        return res;
    }
```


从上到下打印二叉树II
=======================
[leetcode](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-ii-lcof/)
从上到下按层打印二叉树，同一层的节点按从左到右的顺序打印，每一层打印到一行。
```
    3
   / \
  9  20
    /  \
   15   7
输出：
[
  [3],
  [9,20],
  [15,7]
]
```
### 解题思路
* 再上题层序遍历的基础上，多了个按层打印的效果，因此每层都需要一个数组level来记录当前层的所以结点。
* 只需要知道，每次加入队列的所有结点，即为一层的所有结点。队列的长度就是一层的个数。根据这个个数来遍历一层结点。
```cpp
    vector<vector<int>> levelOrder(TreeNode* root) {
        if (root == NULL) return {};
        vector<vector<int>> res;
        queue<TreeNode*> que;
        que.push(root);
        TreeNode* cur = NULL;
        while (!que.empty()) {
            vector<int> level;
            int len = que.size();
            while (len--) {
                cur = que.front();
                que.pop();
                level.push_back(cur->val);
                if (cur->left) que.push(cur->left);
                if (cur->right) que.push(cur->right);
            }
            res.push_back(level);
        }
        return res;
    }
```

* DFS递归法.前序遍历总体来看是从左到右的遍历，因此遍历到某个节点时将其插入到对应高度的结果数组中。
* 因为无法提前知道层高，就需要再遍历的过程中，先判断当前层数在结果数组中是否已经开辟了空间。如果没有就再新建一行数组空间。
```cpp
    vector<vector<int>> res;
    vector<vector<int>> levelOrder(TreeNode* root) {
        dfs(root, 0);
        return res;
    }

    void dfs(TreeNode* root, int depth) {
        if (!root) return;
        if(depth == res.size()) res.emplace_back(vector<int>());   // 新建一行
        res[depth].emplace_back(root->val);
        dfs(root->left, depth + 1);
        dfs(root->right, depth + 1);
    }
```

从上到下打印二叉树III
===========================
[leetcode](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-iii-lcof/)
请实现一个函数按照之字形顺序打印二叉树，即第一行按照从左到右的顺序打印，第二层按照从右到左的顺序打印，第三行再按照从左到右的顺序打印，其他行以此类推。
```
    3
   / \
  9  20
    /  \
   15   7
输出：
[
  [3],
  [20,9],
  [15,7]
]
```
### 解题思路
* 再上体的基础上又多了一个条件，就是对于奇数层和偶数层，他的结点输出循环不同
* 因此还需要一个变量cnt来记录当前层数，当前为偶数层时，level数组进行反转操作。
```cpp
    vector<vector<int>> levelOrder(TreeNode* root) {
        if (root == NULL) return {};
        vector<vector<int>> res;
        queue<TreeNode*> que;
        que.push(root);
        TreeNode* cur = NULL;
        int layer = 0;
        while (!que.empty()) {
            vector<int> level;
            int len = que.size();
            while (len--) {
                cur = que.front();
                que.pop();
                level.push_back(cur->val);
                if (cur->left) que.push(cur->left);
                if (cur->right) que.push(cur->right);
            }
            if (layer % 2 != 0)
                reverse(level.begin(), level.end());
            res.push_back(level);
            layer++;
        }
        return res;
    }
```

* dfs递归思想，每层使用list链表的数据结构，这样可以头插法，相当反转一个数组。
* 最后将链表转为为数组再输出
```cpp
    vector<list<int>> res;
    vector<vector<int>> ans;
    vector<vector<int>> levelOrder(TreeNode* root) {
        dfs(root, 0);
        ans.resize(res.size());
        for (int i = 0; i < res.size(); ++i) 
            for (auto it : res[i]) ans[i].emplace_back(it);
        return ans;
    }

    void dfs(TreeNode* root, int depth) {
        if (!root) return;
        if (depth == res.size()) res.emplace_back(list<int>());
        if (depth & 1) res[depth].emplace_front(root->val);
        else res[depth].emplace_back(root->val);
        dfs(root->left, depth + 1);
        dfs(root->right, depth + 1);
    }
```

二叉搜索树的后序遍历序列
====================================
[leetcode](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-hou-xu-bian-li-xu-lie-lcof/)
输入一个整数数组，判断该数组是不是某二叉搜索树的后序遍历结果。如果是则返回 true，否则返回 false。假设输入的数组的任意两个数字都互不相同
### 示例
````
     5
    / \
   2   6
  / \
 1   3
输入: [1,6,3,2,5]
输出: false

输入: [1,3,2,6,5]
输出: true
````
### 解题思路
* 只要是根据一个序列来判断是否是某个树得某种遍历,一定都需要两个参数`left`和`right`,因为要框出左子树和右子树。
* 因为后序遍历，所以最后一位即`right`所指一定是这个树得根结点`root`
* 找完root结点，还需要找到左子树和右子树得分界点，因为是二叉搜索树，左子树得所有结点值一定小于右子树，利用while遍历序列发现第一个大于root得结点即为右子树得结点，记为mid。
* 这样一个序列分配完成，right所指为root结点，[left, mid-1] 为左子树结点，[mid, right-1]为右子树 
* 判断：如果右子树中发现一个小于root结点，就不满足二叉搜索树了。
```cpp
    bool verifyPostorder(vector<int>& postorder) {
        int left = 0, right = postorder.size() - 1;
        return dfs(postorder, left, right);
    }

    bool dfs(vector<int>& postorder, int left, int right) {
        if (left >= right) return true;
        int root = postorder[right];
        int mid = 0;
        while (postorder[mid] < root) mid++;
        // mid左为left，< root; mid右为right > root
        for (int i = mid; i < right; ++i) {
            if (postorder[i] < root) return false;
        }
        return dfs(postorder, left , mid - 1) && dfs(postorder, mid, right - 1);
    }
```


二叉树中和为某一值的路径
====================================
[leetcode](https://leetcode-cn.com/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/)
输入一棵二叉树和一个整数，打印出二叉树中节点值的和为输入整数的所有路径。从树的根节点开始往下一直到叶节点所经过的节点形成一条路径。
### 示例:
给定如下二叉树，以及目标和 sum = 22，
````
              5
             / \
            4   8
           /   / \
          11  13  4
         /  \    / \
        7    2  5   1
返回:

[
   [5,4,11,2],
   [5,8,4,5]
]
````
### 解题思路
* 通过深度递归,每经过一个结点sum就减去当前结点值，数组path记录路径经过得点，并继续往下递归
* 当sum减至刚好为0时，且当前结点没有后继，属于叶子结点，说明这是一条路径。加入结果数组中即可。
```cpp
    vector<vector<int>> res;
    vector<vector<int>> pathSum(TreeNode* root, int sum) {
        vector<int> path;
        dfs(root, sum, path);
        return res;
    }

    void dfs (TreeNode* root, int sum, vector<int>& path) {
        if (root == NULL) return;
        path.push_back(root->val);
        sum -= root->val;
        if (root->left == NULL && root->right == NULL && sum == 0) res.push_back(path);
        dfs(root->left, sum, path);
        dfs(root->right, sum, path);
        path.pop_back();
        return; 
    }
```

复杂链表的复制
===========================
[leetcode](https://leetcode-cn.com/problems/fu-za-lian-biao-de-fu-zhi-lcof/)
请实现 copyRandomList 函数，复制一个复杂链表。在复杂链表中，每个节点除了有一个 next 指针指向下一个节点，还有一个 random 指针指向链表中的任意节点或者 null。
### 解题思路
* 因为是深拷贝链表，所以每遍历一个结点就new一个新结点，并赋值
* 链表得链接，只能链接当前结点与上一个结点，只要遍历过得结点才能链接，不能往后链接，因此需要维护一个last指针，指向当前结点得前驱
* 由于本题每个结点还有一个随机链接，所以我们需要两个表，第一个表记录原链表得随机指针指向了那个结点得下标。第二表需要记录，新链表每个结点得地址。
* 链接随机指针时：先查原表当前结点随机指针指得是第几个结点，再根据下标查新表获取新结点地址，再链接。
````cpp
    Node* copyRandomList(Node* head) {
        unordered_map<Node*, int> idx;
        unordered_map<int, Node*> addr;

        Node* cur = head;
        Node* dummy = new Node(-1);
        Node* pre = dummy;
        int i = 0;
        while (cur) {
            idx[cur] = i;
            Node* node = new Node(cur->val);
            addr[i] = node;
            pre->next = node;
            pre = pre->next;
            cur = cur->next;
            i++;
        }
        pre->next = NULL;

        cur = head;
        Node* curr = dummy->next;
        while (cur) {
            if (cur->random)
                curr->random = addr[idx[cur->random]];
            else 
                curr->random = NULL;
            cur = cur->next;
            curr = curr->next;
        } 
        return dummy->next;
    }
````

二叉搜索树与双向链表
===============================
[leetcode](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/)
输入一棵二叉搜索树，将该二叉搜索树转换成一个排序的循环双向链表。要求不能创建任何新的节点，只能调整树中节点指针的指向。
### 解题思路
* 链表得链接一定是往前链接，所以需要维护一个指向上一个结点得指针`pre`
* 因为是一个搜索树，所以选择中序遍历,就是从小到大排好序得。
* 当遍历完后，pre指针正好指向最后一个结点，将其与第一个结点进行链接。
* 注意：用一个全局变量来记录遍历过程中的上一个节点。
* 注意：root节点不是第一个链表的第一节点，head->right才是.
````cpp
    Node* pre = NULL; //上一个结点
    Node* treeToDoublyList(Node* root) {
        if (!root) return NULL;
        Node* head = new Node(-1);
        pre = head;
        inorder(root);
        pre->right = head->right;
        head->right->left = pre;
        return head->right;
    }

    void inorder(Node* root) {
        if (!root) return;
        inorder(root->left);
        pre->right = root;
        root->left = pre;
        pre = root;
        inorder(root->right);
    }
````

序列化二叉树
========================
[leetcode](https://leetcode-cn.com/problems/xu-lie-hua-er-cha-shu-lcof/) 请实现两个函数，分别用来序列化和反序列化二叉树。
````
你可以将以下二叉树：

    1
   / \
  2   3
     / \
    4   5

序列化为 "[1,2,3,null,null,4,5]"

````
### 解题思路
* 对于根据序列来建树得题一般都不简单。本题属于困难
* 本题涉及得技巧：层序遍历、数字转字符串、字符串转数字
* 删除字符串最后一位三种方法：
    * 迭代器：`str.erase(str.end() - 1);`
    * 提取子串：`str.substr(0, str.size() - 1);`
    * 数组：`str.pop_back();`     
* 数字转字符串；我用的是从个位开始往前添加每位数字，再`reverse()`反转字符串。效率很低。
* 本代码写的不好
```cpp
    string serialize(TreeNode* root) {
        if (!root) return "";
        queue<TreeNode*> que;
        que.push(root);
        TreeNode* cur = NULL;
        string res;
        while (!que.empty()) {
            cur = que.front();
            que.pop();
            if (cur) {
                res += toString(cur->val);
                res += ',';
                que.push(cur->left);
                que.push(cur->right);
            } else {
                res += "null,";
            }
        }
        //res.erase(res.end() - 1);         // 迭代器/三种用法
        //res.substr(0, res.size() - 1);    // 子串
        res.pop_back();                     
        //cout << "[" + res + "]"<<endl;
        return "[" + res + "]";
    }

    string toString(int val) {
        string res = "";
        if (val < 0) {  // val < 10
            res += '-';
            res += abs(val) + '0';
        } else {    // val >= 0
            while (val) {
                res += val % 10 + '0';
                val /= 10;
            }
            reverse(res.begin(), res.end());
        }
        return res;
    }


    TreeNode* deserialize(string data) {
        if (data.size() == 0) return NULL; 
        vector<int> data_int;
        int left = 1;
        int right = 1;
        
        while (left < data.size()) {
            while (data[right] != ',' && data[right] != ']') right++;
            int val = toInt(data, left, right - 1);
            data_int.push_back(val);
            left = right + 1;
            right++;
        }       

        TreeNode* root = new TreeNode(data_int[0]);
        queue<TreeNode*> que;
        que.push(root);
    
        double start = 0;   // 子结点起始坐标
        double end = 0;
        double n = 1;  // 层数
        TreeNode* cur = NULL;
        while (!que.empty()) {
            double cnt = pow(2, n++);      
            start = cnt - 1;             
            end = start + cnt - 1;     
            while (start <= end) {
                if (start >= data_int.size()) break;
                cur = que.front();           
                que.pop();
                
                TreeNode* leftNode = NULL;
                TreeNode* rightNode = NULL;
                if (data_int[start] != INT_MIN)
                    leftNode = new TreeNode(data_int[start]);
                
                if (data_int[start + 1] != INT_MIN) 
                    rightNode = new TreeNode(data_int[start + 1]);
                
                
                if (leftNode) que.push(leftNode);
                if (rightNode) que.push(rightNode);
                
                cur->right = rightNode;
                cur->left = leftNode;
                
                start += 2;
            } 
        }
        return root;
    }

    int toInt(string str, int left, int right) {
        if (str[left] == 'n') return INT_MIN;
        int res = 0;
        bool isNeg = false;
        if (str[left] == '-') left++, isNeg = true;
        while (left <= right) {
            res = res * 10 + str[left] - '0';
            left++;       
        }
        return isNeg ? -res : res;
    }
```

字符串的排列
===================
[leetcode](https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/)输入一个字符串，打印出该字符串中字符的所有排列。
你可以以任意顺序返回这个字符串数组，但里面不能有重复元素。
### 示例
```
输入：s = "abc"
输出：["abc","acb","bac","bca","cab","cba"]
```
### 解题思路
* 回溯递归，从第一个字符开始，其他所有字符都属于他的下一结点，
所有需要一个for循环遍历全部，为了防止重复遍历需要一个vis数组，同时还需要一个path记录遍历经过的结果
* 回溯递归结束后还需去重，2种方法：1、使用集合set 2、排序去重unique 

```cpp
    vector<string> permutation(string s) {
        vector<string> res;
        string path;
        vector<bool> isVis(s.size(), false);
        dfs(s, path, isVis, res);
        //unordered_set<string> set(res.begin(), res.end()); //使用集合去重。
        //res.assign(set.begin(), set.end());
        sort(res.begin(), res.end());                       // 排序去重
        auto end = unique(res.begin(),res.end());           // 返回最后一位
        res.erase(end, res.end());                          // 剪掉
        return res;
    }

    void dfs (string s, string& path, vector<bool>& isVis, vector<string>& res) {
        if (path.size() == s.size()) {
            res.push_back(path);
            return; 
        }
        // 在所有得选择列表中继续选择
        for (int i = 0; i < s.size(); ++i) {
            if (isVis[i]) continue;
            isVis[i] = true;
            path += s[i];
            dfs(s, path, isVis, res);
            isVis[i] = false;
            path.pop_back();
        }
    }
```
* 修改版。
```cpp
    vector<bool> isVis;
    string s;
    vector<string> res;
    vector<string> permutation(string s) {
        this->s = s;
        isVis.resize(s.size(), false);
        string path;
        for (int i = 0; i < s.size(); ++i) {
            dfs(i, path);
        }
        unordered_set set(res.begin(), res.end());
        res.assign(set.begin(), set.end());
        return res;
    }

    void dfs(int root, string& path) {
        if (isVis[root]) return;
        isVis[root] = true;
        path += s[root];
        if (path.size() == s.size()) {
            res.push_back(path);
        }
        for (int i = 0; i < s.size(); ++i) {
            dfs(i, path);
        }
        isVis[root] = false;
        path.pop_back();
    }
```

数组中出现次数超过一半的数字
=============================
[leetcode](https://leetcode-cn.com/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/)数组中有一个数字出现的次数超过数组长度的一半，请找出这个数字。
你可以假设数组是非空的，并且给定的数组总是存在多数元素。
### 解题思路
* 哈希表记录次数
```cpp
    int majorityElement(vector<int>& nums) {
        int len = nums.size();
        unordered_map<int, int> cnt;
        for (auto& num : nums) {
            cnt[num]++;
            if (cnt[num] > len / 2) return num;
        }
        return -1;
    }
```
* 先排序，因为至少一半都是一个数字，所以中间值一定是他
```cpp
    int majorityElement(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        return nums[nums.size() / 2];
    }
```
* 摩尔投票法： 有同意和反对票。多数值当作同意票，其他所有值都当做反对票, 正负票正好抵消，
* 需要一个`last`值记录上衣结点的数值，用于比较，vato票数一旦为0就重新更新last值。，由于
* 因为最后一定都是一个数值，所以last保存的就是那个值。
```cpp
    int majorityElement(vector<int>& nums) {
       int last = 0, vote = 0;   // 记录投票数
       for (int i = 0; i < nums.size(); ++i) {
           if (vote == 0) { // 正负票正好抵消，
               last = nums[i];
               vote++;
           } else { // 当前票与上一票进行比较，相同就++，不同就抵消了
               last == nums[i] ?  vote++ : vote--;
           }
       }
       return last; // 最后就剩多数票了
    }
```

最小的k个数
===================
[leetcode](https://leetcode-cn.com/problems/zui-xiao-de-kge-shu-lcof/)输入整数数组 arr ，找出其中最小的 k 个数。例如，输入4、5、1、6、2、7、3、8这8个数字，则最小的4个数字是1、2、3、4。
### 解题思路
* 经典的topK问题
* 求topK最小就用大顶堆。求topK最大就用小顶堆。
* C++用优先队列来实现堆，priority_queue需要三个参数：三个参数：元素类型，容器类型，func类型
* 小顶堆升序排列，大顶堆降序排列。顶top就是队列第一个元素。
* 维护大小为k的大顶堆，当堆满时判断，新插入元素只要小于堆顶（即最大值），就入堆，队顶的最大值弹出。
```cpp
    vector<int> getLeastNumbers(vector<int>& arr, int k) {
        if (k == 0 || arr.size() == 0) return {};
        priority_queue<int, vector<int>, less<int>> que;    
        vector<int> res;
        for (auto& num : arr) {
            if (que.size() == k) { 
                if (num <= que.top())  
                    que.pop(); 
                else 
                    continue;
            }  
            que.push(num);
        }
        while (k--) {
            res.push_back(que.top());
            que.pop();
        }
        return res;
    }
```

* 计数排序解决topK问题
```cpp
    vector<int> getLeastNumbers(vector<int>& arr, int k) {
        int cnt[10001];
        memset(cnt, 0, sizeof(int) * 10001);
        for (auto num : arr) {
            cnt[num]++;
        }
        vector<int> res;
        for (int i = 0; i < 10001; ++i) {
            while (cnt[i]-- && res.size() < k)
                res.push_back(i);
            if (res.size() == k) break;
        }
        return res;
    }
```

连续子数组的最大和
======================
{leetcode](https://leetcode-cn.com/problems/lian-xu-zi-shu-zu-de-zui-da-he-lcof/)输入一个整型数组，数组里有正数也有负数。数组中的一个或连续多个整数组成一个子数组。求所有子数组的和的最大值。
要求时间复杂度为O(n)。
### 解题思路
* 首先想到动态规划
* dp[i]代表到当前i位置时，连续的子数组和得最大值。他与dp[i-1]有关，如果dp[i-1]+num[i]更大，那设为dp[i]，但是如果dp[i-1]+nums[i]还没有本身nums[i]大的话说明前面的dp[i-1]还是个负值，产生负影响，所以前面的i-1个子串都该舍弃。
* 难点在于状态转移方程：因为题意要求必须是连续，所以如果+nums[i]后，还没有本身nums[i]大时，就断开前面得重新开始。
```cpp
    int maxSubArray(vector<int>& nums) {
        int len = nums.size();
        vector<int> dp(len);
        int maxSum = nums[0];
        for (int i = 0; i < len; ++i) {
            if (i == 0) dp[0] = nums[0];
            else dp[i] = max(dp[i - 1] + nums[i], nums[i]); 
            maxSum = max(maxSum, dp[i]);
        }
        return maxSum;
    }
```
* 如果面试要求空间复杂度O(1)时
* 该使用一个变量pre来记录dp[i-1]
* 可以使用技巧：`cur += max(pre, 0);`来代替if else操作。
```cpp
    int maxSubArray(vector<int>& nums) {
        int maxSum = nums[0];
        int pre = nums[0];
        int cur = 0;
        for  (int i = 1; i < nums.size(); i++) {
            cur = nums[i];
            cur += max(pre, 0);
            pre = cur;
            maxSum = max(maxSum, cur);
        }
        return maxSum;
    }
```
* 正常不用技巧
```cpp
    int maxSubArray(vector<int>& nums) {
        int n = nums.size();
        int cur = 0;
        int pre = nums[0];
        int MAX = nums[0];
        for (int i = 1; i < n; ++i) {
            cur = nums[i];
            cur = max(cur + pre, cur);
            MAX = max(MAX, cur);
            pre = cur;
        }
        return MAX;
    }
```

1～n整数中1出现的次数
=======================
[leetcode](https://leetcode-cn.com/problems/1nzheng-shu-zhong-1chu-xian-de-ci-shu-lcof/)
输入一个整数 n ，求1～n这n个整数的十进制表示中1出现的次数。
例如，输入12，1～12这些整数中包含1 的数字有1、10、11和12，1一共出现了5次。
### 解题思路
* 正常思路,对每个数循环取余计算1出现的个数，但是会超时。
```cpp
    int countDigitOne(int n) {
        int res = 0; 
        for (int i = 1; i <= n; ++i) 
            res += count(i);
        return res;
    }

    int count(int num) {
        int cnt = 0;
        while (num) {
            cnt += (num % 10 == 1);
            num /= 10;
        }
        return cnt;
    }
```
* 快速的方法是，直接根据n，统计十进制n中每个位出现1的次数，这样这需遍历n的位数次就能求出结果。
* 需要找到每位出现次数的规律：对于个位只有0~9,1只出现1次，十位0~99会出现10次，百位0~999会出现100次，因此每位出现1的次数与他的位数`digit`有关
* 如果当前位是0的话，例如2304的十位出现1的次数为：因为十位数有`0~99`,十位会出现`10`次1，而`0~99`出现的次数又是`23`次,因此1出现的总次数为：`23 * 10 = 230`，公式:`high * dight`
* 如果当前位是1的话，例如2314，在2304的基础上，在加上 `10，11，12，13，14` 5 个，即 `23 * 10 + 4 + 1` 公式:`high * digit + low + 1`
* 如果当前位是2的话，例如2324, 在2304的基础上，在加上完整的10的是个数`10,12,13,14,15,16,17,18,19`即`23 * 10 + 10` 公式：`high + digit + dight`
* 结束条件：cur遍历完所有的位后。
* 注意更新low cur high digit的先后顺序不能错
```cpp
    int countDigitOne(int n) {
        int high = n / 10, cur = n % 10, low = 0;
        long digit = 1;
        int cnt = 0;
        while (high || cur) {   // 只有同时为0时才结束
            if (cur == 0) cnt += high * digit;
            else if (cur == 1) cnt += high * digit + low + 1;
            else cnt += (high + 1) * digit;
            low += cur * digit;
            cur = high % 10;
            high /= 10;
            digit *= 10;
        }
        return cnt;
    }
```

数字序列中某一位的数字
======================
[leetcode](https://leetcode-cn.com/problems/shu-zi-xu-lie-zhong-mou-yi-wei-de-shu-zi-lcof/submissions/)数字以0123456789101112131415…的格式序列化到一个字符序列中。在这个序列中，第5位（从下标0开始计数）是5，第13位是1，第19位是4，等等。
请写一个函数，求任意第n位对应的数字。
### 解题思路
* 先确定n所指的数字是几位数，通过循环相减确定所在哪个区间。
* 再确定n所指的数字是什么，通过起始值加偏移量确定数子
* 最后确定n所指的位于数字的第几位，通过取余确定
* 最后为了方便取出数字的第几位，先转换为字符串，取出后再转换为整型。
```cpp
    int findNthDigit(int n) {
        long digit = 1, start = 1, cnt = 9;
        while (n > cnt) {
            n -= cnt;
            digit += 1;
            start *= 10;
            cnt = digit * start * 9;
        }
        int num = start + (n - 1) / digit;	// 括号不能省 n-1 是因为从0开始不是从1开始，减去0
        return to_string(num)[(n - 1) % digit] - '0';
    }
```



把数组排成最小的数
======================
[leetcode](https://leetcode-cn.com/problems/ba-shu-zu-pai-cheng-zui-xiao-de-shu-lcof/)输入一个非负整数数组，把数组里所有数字拼接起来排成一个数，打印能拼接出的所有数字中最小的一个。
### 解题思路
* 本质是一个排序问题，需要设计一定得规则将字串排序并输出
* 将所有得数字转换为字符串添加到vector数组中，方便使用sort()函数进行排序
* `[](type parm, type parm){return ;}` 使用lamada表达式建立得匿名函数，作为sort函数得比较cmp函数
* 比较原则：如意两个数字例如：3和30， 如果拼接得字符串330 > 303，就认为3 > 30 
```cpp
    string minNumber(vector<int>& nums) {
        vector<string> res;
        for (auto it : nums) res.push_back(to_string(it));
        sort(res.begin(), res.end(), [](string str1, string str2){return str1 + str2 < str2 + str1;});
        string ans;
        for (auto it : res) ans += it;
        return ans;
    }
```
### python3
* ` join()`：用一个字符去拼接一个字符列表
* `append()`：列表得追加
* `functools.cmp_to_key`：将老式得cmp函数转换为关键词函数，（python3取消了cmp函数使用关键字函数）
```Bash
class Solution:
    def minNumber(self, nums: List[int]) -> str:
        def sort_rule(x, y):
            a, b = x + y, y + x
            if a > b: return 1
            elif a < b: return -1
            else: return 0
        strs = []
        for num in nums:
            strs.append(str(num))
        strs.sort(key = functools.cmp_to_key(sort_rule))
        return ''.join(strs)
```

把数字翻译成字符串
=========================
[leetcode](https://leetcode-cn.com/problems/li-wu-de-zui-da-jie-zhi-lcof/)给定一个数字，我们按照如下规则把它翻译为字符串：0 翻译成 “a” ，1 翻译成 “b”，……，11 翻译成 “l”，……，25 翻译成 “z”。一个数字可能有多个翻译。请编程实现一个函数，用来计算一个数字有多少种不同的翻译方法。

```
输入: 12258
输出: 5
解释: 12258有5种不同的翻译，分别是"bccfi", "bwfi", "bczi", "mcfi"和"mzi"
```
### 解题思路
* 首先想到用动态规划的思路，想想每新增加一个字符对方法数量改变所做的贡献。例如1，只有一种翻译方式，而2加入后可以分两种情况，2翻译成b时，是一种，12一起翻译又是一种方式，
* 注意所谓的贡献指，新增2对方法数量的贡献，新增2之前的方法数是n，新增2后还是n，贡献值为0。
* 状态转移方程：先判断新增的数字与前一个数字合并，是否在1~26之间，如果是则dp[i] = d[i -1] + dp[i - 2],否则还是dp[i-1]
* 题目中还设置了限制，前导0的情况下不算。即01不属于1~26之间。
```cpp
    // 判断与前一个数组能否形成一个字母
    bool helper(int num1, int num2) {
        if (num1 == 0)return false;
        return num1 * 10 + num2 >= 0 && num1 * 10 + num2 <= 25; 
    }

    // 将一个数，按位填入数组中
    vector<int> toVector(int num) {
        vector<int> res;
        if (num == 0) return {0};
        while (num) {
            res.push_back(num % 10);
            num /= 10;
        }
        reverse(res.begin(), res.end());
        return res;
    }
    
    int translateNum(int num) {
        if (num < 10) return 1;
        vector<int> nums = toVector(num);
        vector<int> dp(nums.size());
        dp[0] = 1;
        dp[1] = helper(nums[0], nums[1]) ? 2 : 1;
        for (int i = 2; i < nums.size(); ++i) 
            dp[i] = helper(nums[i - 1], nums[i]) ? dp[i - 1] + dp[i - 2] : dp[i - 1];
        return dp.back();
    }
```

* 改进版：用string替换数组数据结构
```cpp
    bool help(string num, int i) {
        if (num[i - 1] == '1' || (num[i - 1] == '2' && num[i] < '6')) return true;
        return false;
    }

    int translateNum(int num) {
        if (num < 10) return 1;
        string n = to_string(num);
        vector<int> dp(n.size());
        dp[0] = 1;
        dp[1] = help(n, 1) ? 2 : 1;
        for (int i  = 2; i < n.size(); ++i) {
            dp[i] = help(n, i) ? dp[i - 1] + dp[i - 2] : dp[i - 1];
        }
        return dp.back();
    }
```

礼物的最大价值
===================
[leetcode](https://leetcode-cn.com/problems/li-wu-de-zui-da-jie-zhi-lcof/)在一个 m*n 的棋盘的每一格都放有一个礼物，每个礼物都有一定的价值（价值大于 0）。你可以从棋盘的左上角开始拿格子里的礼物，并每次向右或者向下移动一格、直到到达棋盘的右下角。给定一个棋盘及其上面的礼物的价值，请计算你最多能拿到多少价值的礼物？
### 示例
```
输入: 
[
  [1,3,1],
  [1,5,1],
  [4,2,1]
]
输出: 12
解释: 路径 1→3→5→2→1 可以拿到最多价值的礼物
```
### 解题思路
* 矩阵的动态规划问题，要求到矩阵中的任意一格的值，都与当前格子上和左格子值有关。因此状态转移方程为：`dp[i[j] = max(dp[i - 1][j], dp[i][j - 1]) + grid[i][j]`
* 注意边界问题，在第一行和第一列得状态转移方程稍微有所不同，第一个点可以直接跳过比方便遍历
```cpp
    int maxValue(vector<vector<int>>& grid) {
        int row = grid.size();
        int col = grid[0].size();
        vector<vector<int>> dp(row, vector<int>(col, 0));
        dp[0][0] = grid[0][0];
        for (int i = 0; i < row; ++i) {
            for (int j = 0; j < col; ++j) {
                if (i == 0 && j == 0) continue;
                if (i == 0) dp[0][j] = dp[0][j - 1] + grid[0][j];
                else if (j == 0) dp[i][0] = dp[i - 1][0] + grid[i][0];
                else dp[i][j] = max(dp[i - 1][j], dp[i][j - 1]) + grid[i][j];
            }
        }
        return dp[row-1][col-1];
    }
```

最长不含重复字符的子字符串
==========================
[leetcode](https://leetcode-cn.com/problems/zui-chang-bu-han-zhong-fu-zi-fu-de-zi-zi-fu-chuan-lcof/)请从字符串中找出一个最长的不包含重复字符的子字符串，计算该最长子字符串的长度。

### 示例
```
输入: "abcabcbb"
输出: 3 
解释: 因为无重复字符的最长子串是 "abc"，所以其长度为 3。
输入: "pwwkew"
输出: 3
解释: 因为无重复字符的最长子串是 "wke"，所以其长度为 3。
     请注意，你的答案必须是 子串 的长度，"pwke" 是一个子序列，不是子串。
```
### 解题思路
* 子串指连续的，子序列可以不连续
* 一看到子串问题大部分都是用滑动窗口思想解决
* 首先移动右指针，当发现有重复的字符出现时，开始移动左指针，直到没有重复字符出现，记录长度个数。
* 判断有无重复字母可用map记录当前窗口中每个字符出现频率。
```cpp
    int lengthOfLongestSubstring(string s) {
        int left = 0, right = 0;
        int n = s.size();
        map<char, int> cnt;
        int res = 0;
        while (right < n) {
            while (cnt[s[right]] == 0 && right < n) {
                cnt[s[right]]++; 
                res = max(res, right - left + 1);
                right++;
            }
            cnt[s[left]]--;
            left++;
        }
        return res;
    }
```

* 或者使用set来判断是否出现重复数字，记住set的常用操作，`emplace(), erase(), find()`  
```cpp
    int lengthOfLongestSubstring(string s) {
        int left = 0, right = 0;
        int longest = 0;
        int n = s.size();
        unordered_set<char> ch;
        while (right < n) {
            while (ch.find(s[right])  == ch.end() && right < n ) {
                longest = max(longest, right - left + 1);
                ch.emplace(s[right]);
                right++;
            }
            ch.erase(s[left]);  // 此处容易写成right 必须在left++前
            left++;
        }
        return longest;
    }
```

丑数
=============
[leetcode](https://leetcode-cn.com/problems/chou-shu-lcof/)我们把只包含质因子 2、3 和 5 的数称作丑数（Ugly Number）。求按从小到大的顺序的第 n 个丑数。
### 示例
```
输入: n = 10
输出: 12
解释: 1, 2, 3, 4, 5, 6, 8, 9, 10, 12 是前 10 个丑数。
```
### 解题思路
* 此题本质上可以看做是合并三个有序序列，因为丑数序列就是合并后去重而已。
* 因为丑数是前面的丑数乘以2或3或5形成的，因此最终的丑数序列一定是`丑数序列 * 2  丑数序列 * 3  丑数序列 * 5`合并去重后得到的。
* 要无重复的合并三个有序序列，每个序列都需要一个指针，比较三指针所指取最小值加入到丑数序列中，最小值的那个指针后移一位
* 当2个序列指针所指都是最小的。那么这2个序列指针同时后移
```cpp
    int nthUglyNumber(int n) {
        vector<int> ugly(n, 0);
        int p1 = 0, p2 = 0, p3 = 0;
        ugly[0] = 1;
        for (int i = 1; i < n; ++i) {
            int minVal = min(ugly[p1] * 2, min(ugly[p2] * 3, ugly[p3] * 5));
            if (minVal == ugly[p1] * 2) p1++;
            if (minVal == ugly[p2] * 3) p2++;
            if (minVal == ugly[p3] * 5) p3++;
            ugly[i] = minVal;
        }
        return ugly.back();
    }
```


第一个只出现一次的字符
===========================
[leetcode](https://leetcode-cn.com/problems/di-yi-ge-zhi-chu-xian-yi-ci-de-zi-fu-lcof/)
在字符串 s 中找出第一个只出现一次的字符。如果没有，返回一个单空格。 s 只包含小写字母。
### 解题思路
* 建立哈希表记录所有字符出现次数，第二次在遍历s字符串找到出现次数为1的字母

```cpp
    char firstUniqChar(string s) {
        unordered_map<char,int> cnt;
        for (char ch : s) 
            cnt[ch]++;
        for (auto ch : s) 
            if (cnt[ch] == 1) return ch; 
        return ' ';
    }
```


两个链表的第一个公共节点
==========================
[leetcode](https://leetcode-cn.com/problems/liang-ge-lian-biao-de-di-yi-ge-gong-gong-jie-dian-lcof/)输入两个链表，找出它们的第一个公共节点。
### 解题思路
>太浪漫了 两个结点不断的去对方的轨迹中寻找对方的身影，只要二人有交集，就终会相遇❤
```cpp
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* p1 = headA;
        ListNode* p2 = headB;
        while (p1 != p2) {
            p1 = p1 == NULL ? headB : p1->next;
            p2 = p2 == NULL ? headA : p2->next;
        }
        return p1 == NULL ? NULL: p1;
    }
```


在排序数组中查找数字I
=========================
[leetcode](https://leetcode-cn.com/problems/zai-pai-xu-shu-zu-zhong-cha-zhao-shu-zi-lcof/)统计一个数字在排序数组中出现的次数。
### 解题思路
* 既然题目中提到了是排序数组就要利用这个条件，主要还是考二分法
* 因为排好序了，所以目标数字一定都是连续得，只要找到最左边得数字，再往后遍历统计数量即可。

```cpp
    int search(vector<int>& nums, int target) {
        int left = 0, right = nums.size() - 1;
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) right = mid;
            else if (nums[mid] < target) left = mid + 1;
            else right = mid;  
        }
        int cnt = 0;
        while (left < nums.size() && nums[left++] == target)
            cnt++;
        return cnt;
    }
```

0～n-1中缺失的数字
=========================
[leetcode](https://leetcode-cn.com/problems/que-shi-de-shu-zi-lcof/)一个长度为n-1的递增排序数组中的所有数字都是唯一的，并且每个数字都在范围0～n-1之内。在范围0～n-1内的n个数字中有且只有一个数字不在该数组中，请找出这个数字。
### 解题思路
* 排序数组找某个数首先想到二分法，其次找缺失数字两头数组得不同点，加以区分，发现他们与下标得关系不同
* 左边数字与下标相同，而右边数组与下标不同，通过二分法找到缺失的位置
* 边界的判断，如果left指针指向最后一个元素，且当前元素与下标是相等的，说明数组中间并没有缺，缺的是最后一位的数字。
```cpp
    int missingNumber(vector<int>& nums) {
        int left = 0, right = nums.size() - 1;
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] != mid) right = mid;
            else left = mid + 1;
        }
        return left == nums.size() - 1 && nums[left] == left ? left + 1 : left;
    }
```

二叉搜索树的第k大节点
======================
[leetcode](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-di-kda-jie-dian-lcof/)给定一棵二叉搜索树，请找出其中第k大的节点。
### 示例
```
输入: root = [3,1,4,null,2], k = 1
   3
  / \
 1   4
  \
   2
输出: 4
```
### 解题思路
* BST的特点是中序遍历是排好序的，稍作调整，让中序遍历的时候先遍历右子树，最后再遍历左子树，可以实现从大到小的顺序
```cpp
    int res = 0;
    int cnt = 0;
    int kthLargest(TreeNode* root, int k) {
        dfs(root, k);
        return res;
    }
    void dfs(TreeNode* root, int& k) {
        if (!root) return;
        dfs(root->right, k);
        if (--k == 0) {
            res = root->val;
            return ;
        }
        dfs(root->left, k);
    }
```

二叉树的深度
===============
[leetcode](https://leetcode-cn.com/problems/er-cha-shu-de-shen-du-lcof/)输入一棵二叉树的根节点，求该树的深度。从根节点到叶节点依次经过的节点（含根、叶节点）形成树的一条路径，最长路径的长度为树的深度。
### 解题思路
* 因为要求每个节点得高度必须先知道其左右子节点高度信息，所以用后序遍历得到左右子书高度
* 当前节点得高度为左右子树高度最大值 + 1
* 为了防止重复计算某个子树节点高度可以使用哈希表对遍历过得节点高度进行储存。计算得时候直接进行取值

```cpp
    unordered_map<TreeNode*, int> height;
    int maxDepth(TreeNode* root) {
        if (!root) {
            height[root] = 0;
            return 0;
        }
        
        int left = maxDepth(root->left);
        int right = maxDepth(root->right);
        height[root] = max(height[root->left], height[root->right]) + 1;
        return height[root];
    }
```

平衡二叉树
===========
[leetcode](https://leetcode-cn.com/problems/ping-heng-er-cha-shu-lcof/)输入一棵二叉树的根节点，判断该树是不是平衡二叉树。如果某二叉树中任意节点的左右子树的深度相差不超过1，那么它就是一棵平衡二叉树。
### 解题思路
* 要判断当前节点是否满足平衡二叉树条件需要先知道左右子树得高度差，因此需要先遍历左右子树，因此使用后序遍历
* 如果左右子节点有任一不满足，直接返回false
* 如果当前节点不满足也直接返回false
* 因为计算节点得高度也是后序遍历，因此可以同时用哈希表记录遍历过得节点高度

```cpp
    unordered_map<TreeNode*, int> height;
    bool isBalanced(TreeNode* root) {
        if (!root) {
            height[root]  = 0;
            return true;
        }
        if (!isBalanced(root->left) || !isBalanced(root->right)) return false;
        if (abs(height[root->left] - height[root->right]) > 1) return false;
        height[root] = max(height[root->left], height[root->right]) + 1;
        return true;
    }
```

数组中数字出现的次数
======================
[leetcode](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/)一个整型数组 nums 里除两个数字之外，其他数字都出现了两次。请写程序找出这两个只出现一次的数字。要求时间复杂度是O(n)，空间复杂度是O(1)。
### 解题思路
* 普通思路使用哈希表，但一定不是面试官想要得答案
* 主要考点还是位运算：
	* ^异或：x ^ x = 0; 
	* ^异或其他常用用法： i ^ 0 = i; i ^ 1 = ~i; (i表示某一位)
* 全部数字进行异或后，凡是出现两次得数都会抵消掉，因此最后剩下得数就是只出现一次得两个数异或。
* 加入A ^ B = C 数组c得二进制形式下，某一个位出现的1一定来自与A或B中的其中一个。通过这一位来区别A和B
* `int mask = A & (-A)` 可以得A二进制最右边位的1，用这个数mask来做为掩码。
* 通过mask掩码与运算，所以数字都区分为两类，一类是有掩码位为1的数，另一类是掩码位为0的数
* 再次分别异或，最终得到只出现一次的两个数。

```cpp
    vector<int> singleNumbers(vector<int>& nums) {
        int sum = 0;
        for (auto num: nums) 
            sum ^= num;
        int res1 = 0, res2 = 0;
        int mask = sum & (-sum);
        for (auto num : nums) {
            if (mask & num) 
                res1 ^= num;
            else 
                res2 ^= num;
        } 
        return {res1, res2};
    }
```

数组中数字出现的次数II
=======================
[leetcode](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-ii-lcof/)
在一个数组 nums 中除一个数字只出现一次之外，其他数字都出现了三次。请找出那个只出现一次的数字。
### 解题思路
* 统计所有数字二进制形式下，各个位1出现的次数和，保存再`cnt[32]`
* 出现3次数字的位，1的个数一定是3的倍数，因此对cnt[32]各位进行3的取模运算。
* 最终再将cnt[32]转换为整型数字，即为所求
```cpp
    int singleNumber(vector<int>& nums) {
        int cnt[32];
        memset(cnt, 0, sizeof(int) * 32);
        for (auto num : nums) {
            unsigned int mask = 1;  // 每个数都要重新复位一下, 不用无符号会报错
            for (int i = 31; i >= 0; --i) {
                if (num & mask) cnt[i]++;
                mask <<= 1;
            }
        }
        int res = 0;
        for (int i = 0; i < 32; ++i) {
            res <<= 1;      // 必须先左移，否则结果最后会多移一位，变成2倍的值
            res += cnt[i] % 3;   
        }
        return res;
    }
```

* 还有一种更为玄学的操作，了解一下即可  
```cpp
    int singleNumber(vector<int>& nums) {
        int once = 0, twice = 0;
        for (auto num : nums) {
            once = once ^ num & ~twice;
            twice = twice ^ num & ~once;
        }
        return once;
    }
```

和为s的两个数字
===============
[leetcode](https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof/)
输入一个递增排序的数组和一个数字s，在数组中查找两个数，使得它们的和正好是s。如果有多对数字的和等于s，则输出任意一对即可。
### 解题思路
* 既然题目中已经给出了增序数列，一般考的就是二分搜索
```cpp
    vector<int> twoSum(vector<int>& nums, int target) {
        for (auto num : nums) {
            int res = qsort(nums, target - num);
            if (res > 0) return {num , res};
        }
        return {};
    }

    int qsort(vector<int>& nums, int target) {
        int left = 0, right = nums.size() - 1;
        while (left < right) {
            int mid = left + (right - left) / 2;
            if (nums[mid] == target) return target;
            else if (nums[mid] > target) right = mid;
            else left = mid + 1;
        }
        return -1;
    }
```
 * 或者两头使用双指针法遍历
 
```cpp
    vector<int> twoSum(vector<int>& nums, int target) {
        int left = 0, right =nums.size() - 1;
        while (left < right) {
            if (nums[left] + nums[right] > target) right--;
            else if (nums[left] + nums[right] == target) return {nums[left],nums[right]};
            else left++;
        }
        return {};
    }
```

和为s的连续正数序列
===================
[leetcode](https://leetcode-cn.com/problems/he-wei-sde-lian-xu-zheng-shu-xu-lie-lcof/)
输入一个正整数 `target` ，输出所有和为 `target` 的连续正整数序列（至少含有两个数）。
序列内的数字由小到大排列，不同序列按照首个数字从小到大排列。
### 解题思路
* 类似与找连续字串的问题，都要想到滑动窗口思想
* 右指针一直往后移动，知道窗口内的和大于等于`target`,如果等于`target`就存入结果中，如果大于就移动左指针。
```cpp
   vector<vector<int>> findContinuousSequence(int target) {
        int left = 1, right = 1;
        vector<vector<int>> res;
        while (right < target) {
            while ((left + right) * (right - left + 1) / 2 < target) {
                right++;
            }
            if ((left + right) * (right - left + 1) / 2 == target) {
                vector<int> ret;
                for (int i = left; i <= right; ++i) {
                    ret.push_back(i);
                }
                res.push_back(ret);
            }
            left++;
        }
        return res;
    }
```

翻转单词顺序
============
[leetcode](https://leetcode-cn.com/problems/fan-zhuan-dan-ci-shun-xu-lcof/)输入一个英文句子，翻转句子中单词的顺序，但单词内字符的顺序不变。为简单起见，标点符号和普通字母一样处理。例如输入字符串"I am a student. "，则输出"student. a am I"。
### 示例
```
输入: "the sky is blue"
输出: "blue is sky the"
```
### 解题思路
* 反转类型的题，首先想到用栈
* 遍历字符串，分割字符串并生成字符串模板，字符串入栈。
```cpp
    string reverseWords(string s) {
        stack<string> sck;
        for (int i = 0; i < s.size(); ++i) {    
            string str;
            while (i < s.size() && !isblank(s[i])) {
                str += s[i];
                ++i;
            }
            if (!str.empty()) sck.push(str);    // 防止空串入栈
        }
        string res = "";
        while (!sck.empty()) {
            res = res + sck.top() + ' ';
            sck.pop();
        }
        if(!res.empty()) res.pop_back();    // 防止弹出空字符串
        return res;
    }
```

左旋转字符串
=============
[leetcode](https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/)字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。比如，输入字符串"abcdefg"和数字2，该函数将返回左旋转两位得到的结果"cdefgab"。
### 示例
```
输入: s = "abcdefg", k = 2
输出: "cdefgab"
```

### 解题思路
* 因为只是互换位置，字串的长度没有变化，从位置k开始遍历，如果超过len就对`len`取模，形成从头循环。
```cpp
    string reverseLeftWords(string s, int n) {
        int len = s.size();
        string res = "";
        for (int i = 0; i < len; ++i) {
            res += s[(n + i) % len];
        }
        return res;
    }
```
* 偷懒的方式直接使用库函数strstr()提取子串
* `strstr(int begin, int end)` 注意end指最后一位字母的后一位索引。
```cpp
    string reverseLeftWords(string s, int n) {
        return s.substr(n, s.size()) + s.substr(0, n);
    }
```

滑动窗口的最大值
==================
[leetcode](https://leetcode-cn.com/problems/hua-dong-chuang-kou-de-zui-da-zhi-lcof/)
给定一个数组 nums 和滑动窗口的大小 k，请找出所有滑动窗口里的最大值。
### 示例
```
输入: nums = [1,3,-1,-3,5,3,6,7], 和 k = 3
输出: [3,3,5,5,6,7] 
解释: 

  滑动窗口的位置                最大值
---------------               -----
[1  3  -1] -3  5  3  6  7       3
 1 [3  -1  -3] 5  3  6  7       3
 1  3 [-1  -3  5] 3  6  7       5
 1  3  -1 [-3  5  3] 6  7       5
 1  3  -1  -3 [5  3  6] 7       6
 1  3  -1  -3  5 [3  6  7]      7

```
### 解题思路
* 维护一个单调队列，队列头部一直保存窗口里的最大值，如果窗口右移时，窗口左边界正好丢弃的是最大值，那么单调队列头部出列。
* 正常窗口右边界加入的数字都要依次与队列队尾部比较，进加入的数更大，就不断让它往前走，保持队列一直是单调递减的。
* 注意窗口左右边界的运动范围，`1 - k < left < n - k + 1` 和  `0 < right < n` 两个指针同时运动。
```cpp
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        if (nums.size() == 0 || k == 0) return {};
        deque<int> que;
        vector<int> res;
        for (int left = 1 - k, right = 0; right < nums.size(); ++left, ++right) {
            // 删除得元素等于队首元素时，弹出队首 因为left - 1为弹出的元素，所以left指针不能 = 0.
            if (left > 0 && que.front() == nums[left - 1]) que.pop_front();
            // 保持队列单调递减
            while (!que.empty() && nums[right] > que.back()) que.pop_back();
            que.push_back(nums[right]);
            if (left >= 0) res.push_back(que.front()); // left = 0以后才形成窗口，才有最大值出现。
        }
        return res;
    }
```


队列的最大值
============
[leetcode](https://leetcode-cn.com/problems/dui-lie-de-zui-da-zhi-lcof/)
请定义一个队列并实现函数 max_value 得到队列里的最大值，要求函数max_value、push_back 和 pop_front 的均摊时间复杂度都是O(1)。
若队列为空，pop_front 和 max_value 需要返回 -1
### 解题思路
* 维护两个队列，一个存储正常的数据，一个维护当前最大值的队列
* 单调队列：新加入的数组必须不断与队尾比较，直到找到他合适的位置，队列一直时单调递减的
* 删除元素时，相等时同时弹出两个队列头部。
```cpp
class MaxQueue {
public:
    queue<int> data;
    deque<int> maxque;
    MaxQueue() {}
    
    int max_value() {
        if(!maxque.empty()) return maxque.front();
        return -1;
    }
    
    void push_back(int value) {
        while (!maxque.empty() && value > maxque.back()) maxque.pop_back();
        data.push(value);
        maxque.push_back(value);
    }
    
    int pop_front() {
        if (data.empty()) return -1;
        int res = data.front();
        if (res == maxque.front()) maxque.pop_front();
        data.pop();
        return res;
    }
};
```

n个骰子的点数
==============
[leetcode](https://leetcode-cn.com/problems/nge-tou-zi-de-dian-shu-lcof/)
把n个骰子扔在地上，所有骰子朝上一面的点数之和为s。输入n，打印出s的所有可能的值出现的概率。
你需要用一个浮点数数组返回答案，其中第 i 个元素代表这 n 个骰子所能掷出的点数集合中第 i 小的那个的概率。
### 示例
```
输入: 2
输出: [0.02778,0.05556,0.08333,0.11111,0.13889,0.16667,0.13889,0.11111,0.08333,0.05556,0.02778]
```
### 解题思路
* 二维的动态规划问题
* 首先了解概率问题都是统计次数，最后除以总次数，所以问题转化为，投掷n个骰子，所有点数出现的总次数是6^n，因为每个骰子点数都有6种可能
* 我们的目的就是 计算出投掷完 n 枚骰子后每个点数出现的次数。
* 单单看第 n 枚骰子，它的点数可能为 1~6因此投掷完 n 枚骰子后点数 j 出现的次数，可以由投掷完 n-1枚骰子后，对应点数 j-1, j-2, j-3, ... , j-6 出现的次数之和转化过来。
* 状态转移方程：`dp[n][j]= dp[n-1][j-1] + dp[n-1][j-2] + dp[n-1][j-3] + dp[n-1][j-4] + dp[n-1][j-5] + dp[n-1][j-6]`
* 边界处理:投掷完 1枚骰子后，它的可能点数分别为 1, 2, 3, ... , 6并且每个点数出现的次数都是 1
```cpp
    vector<double> twoSum(int n) {
        vector<vector<int>> dp(n + 1, vector<int>(6 * n + 1, 0));
        for (int i = 1; i <= 6; ++i) 
            dp[1][i] = 1;
        
        for (int i = 2; i <= n; ++i) {				// i: 投掷i个骰子
            for (int j = i; j <= 6 * i ; ++j) {     // j: 点数和的范围
                for (int k = 1; k <= 6; ++k) {      // k: 1~6点数  
                    if (j > k) dp[i][j] += dp[i - 1][j - k]; 
                }
            }
        }
        int total = pow(6, n);
        vector<double> res;
        for (int j = n; j <= 6 * n; ++j) {
            res.push_back(dp[n][j] * 1.0 / total);
        }
        return res;
    }

```
 
 
扑克牌中的顺子
===============
[leetcode](https://leetcode-cn.com/problems/bu-ke-pai-zhong-de-shun-zi-lcof/)
从扑克牌中随机抽5张牌，判断是不是一个顺子，即这5张牌是不是连续的。2～10为数字本身，A为1，J为11，Q为12，K为13，而大、小王为 0 ，可以看成任意数字。A 不能视为 14。
### 示例
```
输入: [0,0,1,2,5]
输出: True
```
### 解题思路
* 因为0代表所有牌，所以只要找到数组中不连续的牌，看他们之间能允许插入几张牌才能使他们连续，最后与0牌的数量进行比较即可
* 先递增排序，0会出现在前面，统计0出现的次数
* 因为是递增排序，所以当前数字与后面的数字差大于1说明出现了不连续，如果需要插入0的个数大于已有的0个数，说明不能组成顺子
* off等于0说明重复数字，不算顺子
* off代表前后的偏差
```cpp
    bool isStraight(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int cnt = 0;
        int off = 0;
        for (int i = 0; i < nums.size() - 1; ++i) {
            if (nums[i] == 0) {
                cnt++;
                continue;
            }
            off = abs(nums[i] - nums[i + 1]);
            if (off == 1) continue;
            if (off == 0 || off - 1 > cnt ) return false;
        }
        return true;
    }
```

圆圈中最后剩下的数字
====================
[leetcode](https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/)
0,1,,n-1这n个数字排成一个圆圈，从数字0开始，每次从这个圆圈里删除第m个数字。求出这个圆圈里剩下的最后一个数字。
例如，0、1、2、3、4这5个数字组成一个圆圈，从数字0开始每次删除第3个数字，则删除的前4个数字依次是2、0、4、1，因此最后剩下的数字是3。
### 示例
```
输入: n = 5, m = 3
输出: 3
```
### 解题思路
* 普通人思路：通过新建一个链表来模拟操作，但是对于大数会出现超时
* 模拟一个循环链表,n个数字，需要删除`n - 1`次
* 注意list的erase删除操作，参数必须是迭代器，返回值也是迭代器，而且是删除元素后一个位置的迭代器。
* 移动迭代器只能通过++自增操作。
```cpp
    int lastRemaining(int n, int m) {
        list<int> myList;
        for (int i = 0; i < n; ++i) 
            myList.push_back(i);
        n--;
        auto it = myList.begin();
        while (n--) {
            for (int i = 0; i < m - 1; ++i) {
                it++;
                if (it == myList.end()) it = myList.begin();
            }
            it = myList.erase(it);
            if (it == myList.end()) it = myList.begin();
        }
        return myList.front();
    }
```

股票的最大利润
================
[leetcode](https://leetcode-cn.com/problems/gu-piao-de-zui-da-li-run-lcof/)假设把某股票的价格按照时间先后顺序存储在数组中，请问买卖该股票一次可能获得的最大利润是多少？
### 示例
```
输入: [7,1,5,3,6,4]
输出: 5
解释: 在第 2 天（股票价格 = 1）的时候买入，在第 5 天（股票价格 = 6）的时候卖出，最大利润 = 6-1 = 5 。
     注意利润不能是 7-1 = 6, 因为卖出价格需要大于买入价格。
```
### 解题思路
* 动态规划问题，建立dp数组，则`dp[i]`代表前`i`天能获得的最大利润，结果返回`dp[n-1]`
* `dp[i]` 的值与前一天的最大利润`dp[i-1]`有关，如果前一天的利润比当天卖掉股票的最大利润还要大，那就继续用前一天的利润。
* 如果当天卖股票，就需要知道前面i天当中的最小值，所以可以边遍历边记录最小值。
```cpp
    int maxProfit(vector<int>& prices) {
        int n = prices.size();
        if (n == 0) return 0;
        vector<int> dp(n);
        int minVal = prices[0];
        for (int i = 1; i < n; ++i) {
            minVal = min(minVal, prices[i]);
            dp[i] = max(dp[i -1], prices[i] - minVal);
        }
        return dp.back();
    }
```

求1+2+…+n
===========
[leetcode](https://leetcode-cn.com/problems/qiu-12n-lcof/)
求 1+2+...+n ，要求不能使用乘除法、for、while、if、else、switch、case等关键字及条件判断语句（A?B:C）。
### 解题思路
* 高斯就和法需要用到四则运算,也可以这样抖个机灵。
```cpp
return (int)(pow(n, 2) + n) >> 1; 
```
* 迭代法需要用到循环操作
```cpp
 for (int i = 0; i <= n; ++i) 
      res += i; 
```
* 只能用递归法，不过递归一般需要if()来结束跳出递归，
* 可以使用逻辑运算符的特性，`&&`的短路效果来代替跳出操作。也因此`&& ||`这种运算符无法重载
* 当`n = 1`的时候，对于&&运算已经判断为`false`，就不会执行后面的语句，因此直接`return n`; 此时`n=1`
```cpp
int sumNums(int n) {
        n > 1 && (n += sumNums(n - 1));
        return n;
    }
```

不用加减乘除做加法
===================
[leetcode](https://leetcode-cn.com/problems/bu-yong-jia-jian-cheng-chu-zuo-jia-fa-lcof/)  
写一个函数，求两个整数之和，要求在函数体内不得使用 “+”、“-”、“*”、“/” 四则运算符号。
### 解题思路
* 此题主要想考的是二进制形式下的加法运算，一般会用到位运算符
* 先从一个位考虑
```
不考虑进位时：
0 + 0 = 0
0 + 1 = 1
1 + 0 = 1
1 + 1 = 0
正好是异或运算
```
```
只考虑进位c
00 + 00 = 00  	c = 0
01 + 00 = 01	c = 0
00 + 01 = 01	c = 0
01 + 01 = 10	c = 1 
正好是&运算，但是需要左移一位
```
* 所以两个数之和a + b 就转换位二进制形式下的`s + c` , s代表`a ^ b`,c代表`a & b << 1`
* 但是由于题目要求不能使用加号，所以`s + c` 通过继续循环的方式相加，把s赋值给a,c赋值给b，继续循环计算`a + b`,直到第二个加数为0结束。
* 注意c++里，左移不能作用在负数，因此左移前需要格式转换为无符号类型。 `<<` 的优先级高于 `&`记得加括号。
```cpp
    int add(int a, int b) {
        while (b != 0) {
            int c = (unsigned int)(a & b) << 1;
            a ^= b;
            b = c;
        }
        return a;
    }
```


构建乘积数组
==============
[leetcode](https://leetcode-cn.com/problems/gou-jian-cheng-ji-shu-zu-lcof/)
给定一个数组 A[0,1,…,n-1]，请构建一个数组 B[0,1,…,n-1]，其中 B 中的元素 B[i]=A[0]×A[1]×…×A[i-1]×A[i+1]×…×A[n-1]。不能使用除法。
### 示例
```
输入: [1,2,3,4,5]
输出: [120,60,40,30,24]
```

### 解题思路
* 本质上是一道动态规划，维护两个dp数组
* B数组中的每第i数都是由A数组中A[i]左边的所有数之积和A[i]右边的所有数之积相乘得到的。
* 因此一个dp数组用来记录i以左的乘积，另一个记录i以右的乘积
* 状态转移方程分别为`leftDP[i] = leftDP[i - 1] * a[i - 1]`和`rightDP[i] = rightDP[i + 1] * a[i + 1]`
* 注意边界：左边从第二个数字开始建立dp，右边从倒数第二个数字开始建立dp。
```cpp
    vector<int> constructArr(vector<int>& a) {
        int n = a.size();
        if (n == 0) return {};
        vector<int> leftDP(n, 0);
        vector<int> rightDP(n, 0);
		
        leftDP[0] = 1;
        for (int i = 1; i < n; ++i) {
            leftDP[i] = leftDP[i - 1] * a[i - 1];
        }
        rightDP[n - 1] = 1;
        for (int i = n - 2; i >= 0; --i) {
            rightDP[i] = rightDP[i + 1] * a[i + 1];
        }
   
        vector<int> res(n, 0);
        for (int i = 0; i < n; ++i) {
            res[i] = leftDP[i] * rightDP[i];
        }
        return res;
    }
```

把字符串转换成整数
===================
[leetcode](https://leetcode-cn.com/problems/ba-zi-fu-chuan-zhuan-huan-cheng-zheng-shu-lcof/)
写一个函数 StrToInt，实现把字符串转换成整数这个功能。不能使用 atoi 或者其他类似的库函数。

首先，该函数会根据需要丢弃无用的开头空格字符，直到寻找到第一个非空格的字符为止。

当我们寻找到的第一个非空字符为正或者负号时，则将该符号与之后面尽可能多的连续数字组合起来，作为该整数的正负号；假如第一个非空字符是数字，则直接将其与之后连续的数字字符组合起来，形成整数。

该字符串除了有效的整数部分之后也可能会存在多余的字符，这些字符可以被忽略，它们对于函数不应该造成影响。

注意：假如该字符串中的第一个非空格字符不是一个有效整数字符、字符串为空或字符串仅包含空白字符时，则你的函数不需要进行转换。

在任何情况下，若函数不能进行有效的转换时，请返回 0。

说明：

假设我们的环境只能存储 32 位大小的有符号整数，那么其数值范围为 [−231,  231 − 1]。如果数值超过这个范围，请返回  INT_MAX (231 − 1) 或 INT_MIN (−231) 。

### 示例1
```
输入: "42"
输出: 42
```

### 示例2
```
输入: "   -42"
输出: -42
解释: 第一个非空白字符为 '-', 它是一个负号。
     我们尽可能将负号与后面所有连续出现的数字组合起来，最后得到 -42 
```

### 示例3:
```
输入: "4193 with words"
输出: 4193
解释: 转换截止于数字 '3' ，因为它的下一个字符不为数字。
```

### 示例4:
```
输入: "words and 987"
输出: 0
解释: 第一个非空字符是 'w', 但它不是数字或正、负号。
     因此无法执行有效的转换。
```	 

###示例5:
```
输入: "-91283472332"
输出: -2147483648
解释: 数字 "-91283472332" 超过 32 位有符号整数范围。 
     因此返回 INT_MIN (−231) 。
```

### 解题思路
* 用一个指针i从头到尾遍历
* 忽略空格，遍历到第一个非空格字符为止，判断`+-`正负号,
* 继续往后遍历，如果是数字字符就进行转换，如果不是数字就停止转换将之前的转换的结果输出。
* 注意1：输出数字之前都要先判断正负，再输出。
* 注意2：如果不允许使用long只能用int作为转换数字的容器时，
需要在 `res * 10`之前先判断当前`res`是否已经大于`INT_MAX / 10`,或者当前res已经等于`INT_MAX / 10`,但是最右边新加入的位大于`7`说明这个字符已经超过了32位整数的最大值，需要直接输出INT_MAX。
```cpp
    int strToInt(string str) {
        if(str.empty()) return 0;
        int i = 0;
        // 跳过空格
        while(str[i] == ' ') i++;
        // 判断符号
        bool isNeg = false;
        if (str[i] == '-') {
            isNeg = true;
            i++;
        } else if(str[i] == '+')
            i++;
        // 转换数字
        int res = 0;
        while(i < str.size()) {
            if (str[i] >= '0' && str[i] <= '9') {      
                if (res > INT_MAX / 10 || (res == INT_MAX / 10 && str[i] > '7')) 
					return isNeg == true ? INT_MIN : INT_MAX;    // 数字边界处理
                res = res * 10 + (str[i] - '0'); 	// 括号不能省，因为可能会溢出
                
            } else return isNeg == true ? -res : res;       // 不是数字直接返回前面转换得数字结果 
            i++;
        }
        return isNeg == true ? -res : res;
    }
```
* 如果用能用long，比较麻烦，因为res可以超过int的界限，所以再返回答案之前都需要先判断res是否越界。
```cpp
	....前面都一样
        long res  = 0;
        for (; i < str.size(); ++i) {
            if (res > INT_MAX || res < INT_MIN) return isNeg ? INT_MIN : INT_MAX;
            if (str[i] >= '0' && str[i] <= '9') {
                res = res * 10 + (str[i] - '0');
                continue;
            }
            return isNeg ? -res : res;
        }
        if (res > INT_MAX || res < INT_MIN) return isNeg ? INT_MIN : INT_MAX;
        return isNeg ? -res : res;
    }
```


二叉搜索树的最近公共祖先
========================
[leetcode](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-zui-jin-gong-gong-zu-xian-lcof/)
给定一个二叉搜索树, 找到该树中两个指定节点的最近公共祖先。
百度百科中最近公共祖先的定义为：“对于有根树 T 的两个结点 p、q，最近公共祖先表示为一个结点 x，满足 x 是 p、q 的祖先且 x 的深度尽可能大（一个节点也可以是它自己的祖先）。”
例如，给定如下二叉搜索树:  root = [6,2,8,0,4,7,9,null,null,3,5]
![aa](https://assets.leetcode-cn.com/aliyun-lc-upload/uploads/2018/12/14/binarysearchtree_improved.png)

### 示例
```
输入: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 8
输出: 6 
解释: 节点 2 和节点 8 的最近公共祖先是 6。
```
### 示例
```
输入: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 4
输出: 2
解释: 节点 2 和节点 4 的最近公共祖先是 2, 因为根据定义最近公共祖先节点可以为节点本身。
```

### 解题思路
* 根据BST特性，当前值大于qp，说明p，q都在左子树，就往左子树继续递归，当前值小于qp，说明p，q都在右子树。
* p，q各在一边，说明当前的根就是最近共同祖先。
```cpp
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        if (root == NULL) return NULL;
        if (root->val > q->val && root->val > p->val) return lowestCommonAncestor(root->left, p, q);
        if (root->val < p->val && root->val < q->val) return lowestCommonAncestor(root->right, p, q);
        return root; 
    }
```


二叉树的最近公共祖先
====================
[leetcode](https://leetcode-cn.com/problems/er-cha-shu-de-zui-jin-gong-gong-zu-xian-lcof/)
给定一个二叉树, 找到该树中两个指定节点的最近公共祖先。
百度百科中最近公共祖先的定义为：“对于有根树 T 的两个结点 p、q，最近公共祖先表示为一个结点 x，满足 x 是 p、q 的祖先且 x 的深度尽可能大（一个节点也可以是它自己的祖先）。”
例如，给定如下二叉树:  root = [3,5,1,6,2,0,8,null,null,7,4]
![aa](https://assets.leetcode-cn.com/aliyun-lc-upload/uploads/2018/12/15/binarytree.png)

### 示例
```
输入: root = [3,5,1,6,2,0,8,null,null,7,4], p = 5, q = 1
输出: 3
解释: 节点 5 和节点 1 的最近公共祖先是节点 3。
```

### 解题思路
* pq得公共结点就意味着p和q分别出现在当前节点的左右子树。
* 因此，当递归遍历到pq结点的时候，直接返回该结点，如果没发现就继续往下遍历。
* 当左右子树返回的不是`null`就说明这棵树下面发现了qp节点。
* 如果只有一棵树返回了`null`说明另一棵树发现了qp节点，就继续往上返回它，告诉上游此也树发现了pq节点。
```cpp
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        if (root == NULL) return NULL;
        if (root == p || root == q) return root;
        TreeNode* left = lowestCommonAncestor(root->left, p, q);
        TreeNode* right = lowestCommonAncestor(root->right, p, q);
        if (left && right) return root;
        if (left) return left;
        if (right) return right;
        return NULL;
    }
```
* 另一种思路：前序遍历记录从根节点到qp结点的两条路径，然后路径逐个比较，最后一个相同的结点即为最近公共结点。
```cpp
    vector<vector<TreeNode*>> path;
    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
        vector<TreeNode*> path1;
        vector<TreeNode*> path2;
        getPath(root, p, path1);
        getPath(root, q, path2);
        
        int n = min(path[0].size(), path[1].size());	// 按最短的路径长度比较
        TreeNode* res = NULL;
        for (int i = 0; i < n; ++i) {
            if (path[0][i] == path[1][i])
                res = path[0][i];
        }
        return res;
    }

    void getPath(TreeNode* root, TreeNode* tar, vector<TreeNode*>& path) {
        if (!root) return;
        path.push_back(root);
        if (root == tar) {
            this->path.push_back(path);
            return;
        }
        getPath(root->left, tar, path);
        getPath(root->right, tar, path);
        path.pop_back();
    }
```



















