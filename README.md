# MajorityElement
Find Majority Element of given an array

```html
Given an array of size n, find the majority element. 
The majority element is the element that appears more than ⌊ n/2 ⌋ times.

You may assume that the array is non-empty and the majority element always exist in the array.
<a href="https://ibb.co/pjGHfY3"><img src="https://i.ibb.co/PG32cq5/Majority-Element.jpg" alt="Majority-Element" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</br>
```csharp
 public static int MajorityElement(int[] nums) {
            IEnumerable sayis = nums.ToList().Distinct();
            Dictionary<int,int> indisandValues = new Dictionary<int, int>();
            foreach (var item in sayis){
                int k = 0;
                for (int j = 0; j < nums.Length; j++){
                    if(Convert.ToInt32(item) == nums[j])
                        k++;
                }
                indisandValues.Add(Convert.ToInt32(item),k);
            }
            int max = 0;
            int majorityNumber = 0;
            foreach (var item in indisandValues){
                if (max < item.Value){
                    max = item.Value;
                    majorityNumber = item.Key;
                }
            }
            int resultCode = 0;
            if (max >= nums.Length / 2)
                resultCode = majorityNumber;
            return majorityNumber;
        }
