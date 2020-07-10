🎨剑指offer🎨
=======
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
* 

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

旋转数组的最小数字
==========
[leetcode](https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/)
把一个数组最开始的若干个元素搬到数组的末尾，我们称之为数组的旋转。输入一个递增排序的数组的一个旋转，输出旋转数组的最小元素。例如，数组 [3,4,5,1,2] 为 [1,2,3,4,5] 的一个旋转，该数组的最小值为1。  
### 解题思路
* 典型的二分查找，要查找的数左右两边的特点，他的左边都是大于数组的最后一个数，他的右边都是小于数组最后一个数。
* 套二分查找的模板
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


机器人的运动范围
======================
[leetcode](https://leetcode-cn.com/problems/ji-qi-ren-de-yun-dong-fan-wei-lcof/)
地上有一个m行n列的方格，从坐标 [0,0] 到坐标 [m-1,n-1] 。一个机器人从坐标 [0, 0] 的格子开始移动，它每次可以向左、右、上、下移动一格（不能移动到方格外），也不能进入行坐标和列坐标的数位之和大于k的格子。例如，当k为18时，机器人能够进入方格 [35, 37] ，因为3+5+3+7=18。但它不能进入方格 [35, 38]，因为3+5+3+8=19。请问该机器人能够到达多少个格子？
### 解题思路
* 此题的难度在于理解上面，并不是暴力的遍历全部结点，判断哪个符合条件，因为题目时运动范围即，所以符合要求的结点都时连接在一起的。
* 因为数组中的值仅仅为两位数，因此' x / 10 + x %10'就是个位与十位的数位和
* 这里用了一个二维数组记录访问过的结点，一定要初始化二维数组。
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
(建了dp数组实际跟动规并没有任何关系）
* 暴力解决  
* 要想积最大，每段长度都尽量相等或接近就行，首先想到用平均值avg，如果平均下来有剩余值，就降剩余值再平均前面每个值上，就变avg + 1，所以最终分段完每段的长度不是avg就是avg + 1
* 设分了m段,那么余数有多少，就有多少个avg + 1,剩下的就是avg
* dp数组用于记录分m（2 ~ n)段得到得积，最后排序取最大值。
* pow(int num, int exp);求乘方函数。
```cpp
    int cuttingRope(int n) {
        vector<int> dp(n);
        for (int m = 2; m <=n; ++m) {
            int avg = n / m; 
            int ans = n % m ? pow(avg, m - n % m) * pow(avg + 1, n % m) : pow(avg, m);
            dp.push_back(ans); 
        }
        sort(dp.begin(), dp.end());
        return dp.back();
    }
```
