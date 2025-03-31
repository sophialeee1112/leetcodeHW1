# leetcodeHW1
#題目一:Climbing Stairs https://leetcode.com/problems/climbing-stairs/description/
'''python
class Solution:
    def climbStairs(self, n: int) -> int:
        if n <= 2:
            return n

        
        a = 1  # 走到第(n-2)階的方法數
        b = 2  # 走到第(n-1)階的方法數
        for i in range(3, n + 1):
            total = a + b  # 第n階的走法 = 前兩階走法加總
            a = b          # 更新：a變成前一階
            b = total      # 更新：b變成現在階
        return b 
#題目二:Maximum Depth of Binary Tree https://leetcode.com/problems/maximum-depth-of-binary-tree/description/
'''python
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0
        left_depth = self.maxDepth(root.left)
        right_depth = self.maxDepth(root.right)
        return max(left_depth, right_depth) + 1

 #題目三:Merge Two Sorted Lists https://leetcode.com/problems/merge-two-sorted-lists/description/
 '''python
 class Solution():
    def mergeTwoLists(self, list1, list2):
        listNode = ListNode()
        curr = listNode

        while list1 and list2:
            if list1.val < list2.val:
                curr.next = list1
                list1 = list1.next
            else:
                curr.next = list2
                list2 = list2.next
            curr = curr.next  
        curr.next = list1 if list1 else list2  

        return listNode.next

#題目四:Length of Last Word https://leetcode.com/problems/length-of-last-word/
'''python
class Solution():
    def lengthOfLastWord(self, s):
        return len(s.strip().split(‘ ’)[-1])
#題目五:plus on  https://leetcode.com/problems/plus-one/description/
'''python
def plus_one(digits):
   
    n = len(digits)
    
    for i in range(n - 1, -1, -1):
        if digits[i] < 9:
            digits[i] += 1
            return digits
        digits[i] = 0
    
    return [1] + digits
#題目六:Roman to Integer  https://leetcode.com/problems/roman-to-integer/description/
'''python
class Solution:
    def romanToInt(self, s:str)->int:
        roman_to_int={
            'I':1,'V':5,'X':10,'L':50,'C':100,'D':500,'M':1000
        }
        result =0

        for i in range(len(s)):
            if i+1<len(s) and roman_to_int[s[i]]<roman_to_int[s[i+1]]:
                result-=roman_to_int[s[i]]
            else:
                    result+= roman_to_int[s[i]]
        return result
test = [ "III", "IV", "IX", "LVIII", "MCMXCIV"]
for case in test:
    print(Solution().romanToInt(case))

  
  
