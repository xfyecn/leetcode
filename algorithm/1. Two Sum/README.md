#1. Two Sum

第一反应是用两个嵌套循环遍历，先试了下Accept了。

但是这个方法是比较笨的，如果3个数或者4个数时间成本太大了，所以还有更优的方法。

先用sort对数组排序，然后用双向指针遍历数组。

如果arr[i]+arr[j] > target,那右指针得左移一位, j--

如果arr[i]+arr[j] < target,那左指针得右移一位，i++

如果arr[i]+arr[j] === target,那就是咱们要找的那个值

接下来要寻找找到的值的在原数组的位置，使用indexOf函数即可。值得注意的是，**如果找到的两个值是相等的，即arr[i] === arr[j]，那第二个值得从第一个值的下标后面开始找起，即j = nums.indexOf(arr[j], i+1)**