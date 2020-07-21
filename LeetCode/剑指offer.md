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
* [36.字符串的排列](#字符串的排列）
* [37.数组中出现次数超过一半的数字](#数组中出现次数超过一半的数字)
* [38.最小的k个数](#最小的k个数)
* [39.连续子数组的最大和](#连续子数组的最大和)
* [40.把数组排成最小的数](#把数组排成最小的数)


数组中重复的数字
===========
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

剪绳子II
==================
[leetcode](https://leetcode-cn.com/problems/jian-sheng-zi-ii-lcof/)
给你一根长度为 n 的绳子，请把绳子剪成整数长度的 m 段（m、n都是整数，n>1并且m>1），每段绳子的长度记为 k[0],k[1]...k[m - 1] 。请问 k[0]*k[1]*...*k[m - 1] 可能的最大乘积是多少？例如，当绳子的长度是8时，我们把它剪成长度分别为2、3、3的三段，此时得到的最大乘积是18。
答案需要取模 1e9+7（1000000007），如计算初始结果为：1000000008，请返回 1。
### 解题思路
* 本题与上一题得区别在于存在大数操作，`2 <= n <= 1000`
* 对于本题需要了解数学知识，要想使成绩最大化，就需要将绳子尽可能的多分段，因此每段长度有，1，2，3中长度考虑，1显然不行，2或3中，3更合适，因此此题就变为求3的幂操作。
* 循环求幂：
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
``

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
        Node* cur = head;
        // 求长度
        int len = 0;
        while (cur) {
            len++;
            cur = cur->next;
        }
        
        unordered_map<Node*, int> oldmap(len);
        unordered_map<int, Node*> newmap(len);
        
        int index = 0;
        Node* newListDummy = new Node(-1); // 新链表头节点
        Node* curr = newListDummy;         // 新链表遍历指针
        cur = head;
        while (cur) {
            // 新建结点
            Node* newNode = new Node(cur->val);
            curr->next = newNode;
            // 建表
            newmap[index] = newNode;
            oldmap[cur] = index;
            index++;
            // 遍历
            curr = curr->next;
            cur = cur->next;
        }
        
        // 同步遍历、链接random
        curr = newListDummy->next;
        cur = head;
        while (cur) {
            if (cur->random) {
                int idx = oldmap[cur->random];
                curr->random = newmap[idx];
            } else {
                curr->random = NULL;
            }
            curr = curr->next;
            cur = cur->next;
        }
        return newListDummy->next;
    }
````

二叉搜索树与双向链表
===============================
[leetcode](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/)
输入一棵二叉搜索树，将该二叉搜索树转换成一个排序的循环双向链表。要求不能创建任何新的节点，只能调整树中节点指针的指向。
### 解题思路
* 链表得链接一定是往前链接，所以需要维护一个指向上一个结点得指针`last`
* 因为是一个搜索树，所以选择中序遍历,就是从小到大排好序得。
* 当遍历完后，last指针正好指向最后一个结点，将其与第一个结点进行链接。

````cpp
    Node* last = NULL; //上一个结点
    Node* treeToDoublyList(Node* root) {
        if (!root) return NULL;
        Node* head = new Node(-1);
        last = head;
        inorder(root);
        last->right = head->right;
        head->right->left = last;
        return head->right;
    }

    void inorder(Node* root) {
        if (!root) return;
        inorder(root->left);
        last->right = root;
        root->left = last;
        last = root;
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
* 回溯递归，从第一个字符开始，其他所有字符都属于他的下一结点，所有需要一个for循环遍历全部，为了防止重复遍历需要一个vis数组，同时还需要一个path记录遍历经过的结果
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

