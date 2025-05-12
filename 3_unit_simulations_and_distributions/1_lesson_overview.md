# Array Pair Sum ➕

## The problem

Write a program that

- takes an array of integers (array) and a target integer sum (sum)
- finds all the pairs of integers in the array that when added together equals the target sum
- return array of integer pairs (eg [[2,3], [1,4]]).

## Understand the Problem

Before tackling the main problem, let's warm up with a simpler task to get you comfortable with the concept of searching
for pairs in an array.

- Consider the array [1, 2, 3] and a target sum of 4. Can you find a pair of numbers in this array that adds up to the
  target sum?
- (1, 2)
  - Not quite. The sume of 1+2=3. We need it to sum to 4.
- (1, 3)
  - Yes, the pair (1, 3) adds up to 4.
- (4)
  - Not quite right. Re-read the previous sections and try again.
    {: .choose_best #problem_example title="Consider the array [1, 2, 3] and a target sum of 4" points="1"
    answer="[2]" }

Keep this process in mind as we move to the coding problem. Make sure your program works with the randomly sampled
arrays and sums below, then get the tests to pass. Remember, the goal is not just to find the solution but to understand
the process and improve your problem-solving skills. Take your time, experiment with different approaches, and see what
works best for you.

## Think Aloud

Remember, interviewers want to see how you approach problems. Verbalize your thought process and write pseudocode as you
break down the problem and explore solutions. It’s okay to start with a simpler, less efficient solution. You can always
refine it later.

```ruby
arrays = [
  [1, 2, 3, 4, 5],
  [0, -1, 2, -3, 1],
  [11, -4, 7, 8, -10]
]
sums = [5, -2, 3]
array = arrays.sample
sum = sums.sample
# write your program using this method
def two_sum(array, sum)

end

puts two_sum(array, sum)
```

{app-coding-practice&num=1}

```starter-code
def two_sum(array, sum)

end
```
```tests
describe "Array Pair Sum" do
  it "finds pairs that sum to 5 in the array [1, 2, 3, 4, 5]" do
    result = two_sum([1, 2, 3, 4, 5], 5)
    expected = [[1, 4], [2, 3]]
    expect(result.map(&:sort)).to match_array(expected.map(&:sort))
  end
end
---
describe "Array Pair Sum" do
  it "finds pairs that sum to -2 in the array [0, -1, 2, -3, 1]" do
    result = two_sum([0, -1, 2, -3, 1], -2)
    expected = [[-3, 1]]
    expect(result.map(&:sort)).to match_array(expected.map(&:sort))
  end
end
---
describe "Array Pair Sum" do
  it "finds pairs that sum to 3 in the array [11, -4, 7, 8, -10]" do
    result = two_sum([11, -4, 7, 8, -10], 3)
    expected = [[-4, 7]]
    expect(result.map(&:sort)).to match_array(expected.map(&:sort))
  end
end
---
describe "Array Pair Sum" do
  it "efficiently handles a very large array, suggesting O(n) time complexity" do
    large_array = Array.new(100000) { rand(-10000..10000) }
    target_sum = rand(-20000..20000)
    start_time = Time.now
    result = two_sum(large_array, target_sum)
    end_time = Time.now
    expect(end_time - start_time).to be < 1 # Test should complete quickly for an O(n) solution
  end
end
```

## Tips and Clues for Solving the Problem

- **Nested Loops**: One way to approach this is by using two nested loops to check every possible pair of numbers in the
  array. This is straightforward but not the most efficient.
- **Hash**: A more efficient method involves using a [hash](https://ruby-doc.org/3.2.2/Hash.html). As you iterate
  through the array, check if the complement (target sum - current number) exists in the hash. If it does, you've found
  a pair. If not, add the current number to the hash and move on.

<aside>
  There are multiple terms used to describe this key-value data structure: Dictionary, Map, Hash Map, Hash Table, etc. For our purposes, we will simply use the term Hash.
</aside>

- **Edge Cases**: Don't forget to consider edge cases. What happens if the array is empty or contains only one element?
- **Duplicates**: How will your program handle duplicate pairs or numbers? Make sure to test your solution against such
  cases.
