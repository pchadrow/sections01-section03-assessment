# Necessary Goals
You will
- Section01
    - a. create a word counts dictionary
    - b. find most common word
- Section02
    - a. calculate the mean and standard deviation of the word counts
- Section03
    - write a function that takes in a parameter to complete a task
    - write a function that takes in multiple parameters to complete a task

# Level Up Goals
- write a function that solves a particular logical task
- write a lambda function to complete a task


```python
# just run this cell
from importlib import reload
import solutions.solutions as sol
reload(sol)
```




    <module 'solutions.solutions' from 'C:\\Users\\damni\\flatiron-ds-course\\sections01-section03-assessment\\solutions\\solutions.py'>



# Section 01: Strings
Using the variable `lyrics` below, please solve the following questions


```python
# this cell will just load and open the lyrics
# just run this cell
with open("data/lyrics.txt", "r") as f:
    lyrics = f.read()
lyrics
```




    "She'll only come out at nights\nThe lean and hungry type\nNothing is new\nI've seen her here before\nWatching and waiting\nOoh, she's sittin' with you\nBut her eyes are on the door\n\nSo many have paid to see\nWhat you think\nYou're gettin' for free\nThe woman is wild\nA she-cat tamed\nBy the purr of a Jaguar\nMoney's the matter\nIf you're in it for love\nYou ain't gonna get too far\n\n(Oh-oh, here she comes)\nWatch out boy\nShe'll chew you up\n(Oh-oh, here she comes)\nShe's a maneater\n(Oh-oh, here she comes)\nWatch out boy\nShe'll chew you up\n(Oh-oh, here she comes)\nShe's a maneater\n\nI wouldn't if I were you\nI know what she can do\nShe's deadly man\nAnd she could really rip your world apart\nMind over matter\nOoh, the beauty is there\nBut a beast is in the heart\n\n(Oh-oh, here she comes)\nWatch out boy\nShe'll chew you up\n(Oh-oh, here she comes)\nShe's a maneater\n(Oh-oh, here she comes)\nWatch out boy\nShe'll chew you up\n(Oh-oh, here she comes)\nShe's a maneater\n\n[Instrumental Interlude]\n\nOoooooooh\n(Oh-oh, here she comes)\nHere she comes\nWatch out boy\nShe'll chew you up\n(Whoa-oh, here she comes\n(Watch out) she's a maneater\n(Oh-oh, here she comes)\n(She's a maneater)\nOoh, she'll chew you up\n(Oh-oh, here she comes)\nHere she comes, she's a maneater\n(Oh-oh, here she comes)\n(Watch out)\nShe'll only come out at night, ooh-oh\n(Oh-oh, here she comes)\nHere she comes\nShe's a maneater\n(Oh-oh, here she comes)\n(She's a maneater)\nThe woman is wild, whoooa\n(Oh-oh, here she comes)\nHere she comes\nWatch out boy, watch out boy\n(Oh-oh, here she comes)\nOh, watch out, watch out\nWatch out, watch out\n(Oh-oh, here she comes)\n(Yeah, yeah) she's a maneater\n(Oh-oh, here she comes)\n(She's a maneater)\nShe's watching and waiting, ooh-oh\n(Oh-oh, here she comes)\nOh, she's a maneater"



## S01 - Part A
create a dictionary called `word_counter` that counts the number of words in `lyrics`.
- remove all puntuation using `string punctuation`
- lowercase the entire string
- split by `" "`


```python
# build your word_counter here
# Your code here
import string
lyrics = lyrics.lower()
for punc in string.punctuation:
    lyrics_stripped = lyrics.replace(punc, "")

word_list = lyrics_stripped.split()

#print(word_list)
word_dict = {}
for word in word_list:
    if word in word_dict:
        word_dict[word] += 1
    else:
        word_dict[word] = 1
print(word_dict)  #unsure why some '()' and '[]' are not filtered out
word_counter = word_dict
```

    {"she'll": 8, 'only': 2, 'come': 2, 'out': 11, 'at': 2, 'nights': 1, 'the': 8, 'lean': 1, 'and': 4, 'hungry': 1, 'type': 1, 'nothing': 1, 'is': 5, 'new': 1, "i've": 1, 'seen': 1, 'her': 2, 'here': 25, 'before': 1, 'watching': 2, 'waiting': 1, 'ooh,': 3, "she's": 12, "sittin'": 1, 'with': 1, 'you': 10, 'but': 2, 'eyes': 1, 'are': 1, 'on': 1, 'door': 1, 'so': 1, 'many': 1, 'have': 1, 'paid': 1, 'to': 1, 'see': 1, 'what': 2, 'think': 1, "you're": 2, "gettin'": 1, 'for': 2, 'free': 1, 'woman': 2, 'wild': 1, 'a': 15, 'she-cat': 1, 'tamed': 1, 'by': 1, 'purr': 1, 'of': 1, 'jaguar': 1, "money's": 1, 'matter': 2, 'if': 2, 'in': 2, 'it': 1, 'love': 1, "ain't": 1, 'gonna': 1, 'get': 1, 'too': 1, 'far': 1, '(oh-oh,': 19, 'she': 26, 'comes)': 19, 'watch': 11, 'boy': 6, 'chew': 6, 'up': 6, 'maneater': 9, 'i': 3, "wouldn't": 1, 'were': 1, 'know': 1, 'can': 1, 'do': 1, 'deadly': 1, 'man': 1, 'could': 1, 'really': 1, 'rip': 1, 'your': 1, 'world': 1, 'apart': 1, 'mind': 1, 'over': 1, 'beauty': 1, 'there': 1, 'beast': 1, 'heart': 1, '[instrumental': 1, 'interlude]': 1, 'ooooooooh': 1, 'comes': 4, '(whoa-oh,': 1, '(watch': 2, 'out)': 2, "(she's": 3, 'maneater)': 3, 'comes,': 1, 'night,': 1, 'ooh-oh': 2, 'wild,': 1, 'whoooa': 1, 'boy,': 1, 'oh,': 2, 'out,': 2, '(yeah,': 1, 'yeah)': 1, 'waiting,': 1}
    


```python
# get actual word_counter here
# just run this cell

word_counter_test = sol.section1_partA(lyrics)
print(word_counter_test)
```

    {'shell': 8, 'only': 2, 'come': 2, 'out': 15, 'at': 2, 'nights': 1, 'the': 8, 'lean': 1, 'and': 4, 'hungry': 1, 'type': 1, 'nothing': 1, 'is': 5, 'new': 1, 'ive': 1, 'seen': 1, 'her': 2, 'here': 25, 'before': 1, 'watching': 2, 'waiting': 2, 'ooh': 3, 'shes': 15, 'sittin': 1, 'with': 1, 'you': 10, 'but': 2, 'eyes': 1, 'are': 1, 'on': 1, 'door': 1, '': 6, 'so': 1, 'many': 1, 'have': 1, 'paid': 1, 'to': 1, 'see': 1, 'what': 2, 'think': 1, 'youre': 2, 'gettin': 1, 'for': 2, 'free': 1, 'woman': 2, 'wild': 2, 'a': 15, 'shecat': 1, 'tamed': 1, 'by': 1, 'purr': 1, 'of': 1, 'jaguar': 1, 'moneys': 1, 'matter': 2, 'if': 2, 'in': 2, 'it': 1, 'love': 1, 'aint': 1, 'gonna': 1, 'get': 1, 'too': 1, 'far': 1, 'ohoh': 19, 'she': 26, 'comes': 24, 'watch': 13, 'boy': 7, 'chew': 6, 'up': 6, 'maneater': 12, 'i': 3, 'wouldnt': 1, 'were': 1, 'know': 1, 'can': 1, 'do': 1, 'deadly': 1, 'man': 1, 'could': 1, 'really': 1, 'rip': 1, 'your': 1, 'world': 1, 'apart': 1, 'mind': 1, 'over': 1, 'beauty': 1, 'there': 1, 'beast': 1, 'heart': 1, 'instrumental': 1, 'interlude': 1, 'ooooooooh': 1, 'whoaoh': 1, 'night': 1, 'oohoh': 2, 'whoooa': 1, 'oh': 2, 'yeah': 2}
    


```python
# Test your code here
# just run this cell

try:
    assert word_counter==word_counter_test
    print('test passed')
except Exception as e:
    print("word_counter does not equal word_counter_test")
```

    word_counter does not equal word_counter_test
    

## S01 - Part B


```python
# Find the word with the highest counts
# Your code here
def most_common(stuff):
    tups = list(stuff.items())
    sorted_tups = sorted(tups, key=lambda x: x[1])
    return sorted_tups[-1]
most_common_word = most_common(word_counter)[0]
print(most_common_word)
```

    she
    


```python
# get actual most_common_word
# just run this cell

most_common_word_test = sol.section1_partB(lyrics)
print(most_common_word_test)
```

    she
    


```python
# test your solution here
# just run this cell

try:
    assert most_common_word==most_common_word_test
    print('test passed')
except Exception as e:
    print("most_common_word does not equal most_common_word_test")
```

    test passed
    

# Section 02: Mean and Standard Deviation
using the dictionary `word_counter` from above, solve the following problems

## S02 - Part A


```python
# calculate the mean word counts
# Your code here
# you can write a function or just do it outright. 
word_count_list = list(word_counter.values())
def mean_count():
    return sum(word_count_list)/len(word_count_list)
mean_word_counts = mean_count()
print(mean_word_counts)
```

    2.90990990990991
    


```python
# get actual mean word counts
# just run this cell

mean_word_counts_test = sol.section2_partA(lyrics)
print(mean_word_counts_test)
```

    3.257425742574257
    


```python
# test your solution here
# just run this cell

try:
    assert mean_word_counts==mean_word_counts_test
    print('test passed')
except Exception as e:
    print("mean_word_counts does not equal mean_word_counts_test")
```

    mean_word_counts does not equal mean_word_counts_test
    

## S02 - Part B


```python
# calculate the standard deviation of the word_counts
# you can write a function or just calculate it out right.  It's up to you.
# Your code here
def stnd_dev(count_list):
    to_be_summed = []
    for number in count_list:
        to_be_summed.append((number - mean_count())**2)
    return sum(to_be_summed)/len(to_be_summed)
        
std_word_counts = stnd_dev(word_count_list)**.5
print(std_word_counts)
```

    4.5983732915913595
    


```python
# get actual standard deviation of word counts
# just run this cell

std_word_counts_test = sol.section2_partB(lyrics)
print(std_word_counts_test)
```

    5.202157711791059
    


```python
# test your solution here
# just run this cell

try:
    assert std_word_counts==std_word_counts_test
    print('test passed')
except Exception as e:
    print("std_word_counts does not equal std_word_counts_test")
```

    std_word_counts does not equal std_word_counts_test
    

# Section03 - Functions

## S03 - Part A


```python
# Your code here
# write the function below
def transform_odds(lst):
    #"""
    #this function should count
    #the number of odds in a list
    #then do the following calculation for every odd
    #- multiply each odd by 3
    #- add 1 to each odd number
    #return the sum of all of these numbers
    #"""
    new_list = []
    for number in lst:
        if number % 2 != 0:
            new_list.append(number*3+1)
    return sum(new_list)
    
   
```


```python
# run cell to generate a list of 100 random numbers
# just run this cell

import random
random_nums = [random.randint(0, 1000) for i in range(100)]
```


```python
# run this cell to transform the random_numbers and store them to transformed_odds
# just run this cell

transformed_odds = transform_odds(random_nums)
```


```python
# run this cell to get the actual value of transformed odds
# just run this cell

transformed_odds_test = sol.section3_partA(random_nums)
```


```python
# test your solution here
# just run this cell

try:
    assert transformed_odds==transformed_odds_test
    print('test passed')
except Exception as e:
    print("transformed_odds does not equal transformed_odds_test")
```

    test passed
    

## S03 - Part B


```python
# Your code here
# write a function that checks the numbers in a list numbers
# and checks if any of the numbers are divisible in a list of divisors divisors
# it should return the all numbers in order they're given in the list 
# as a string"""
    #Example: 
    #find_if_divisible([10, 19, 15, 20, 23, 30, 50, 100], [2, 8, 5])
    #should return 
    #"1015203050100"
    
    #since all of these numbers are divisible by at least one number in the divisors list
    #"""

def find_if_divisible(numbers, divisors):
    numstr = ''
    for num in numbers:
        if any(num%div == 0 for div in divisors):
            numstr = numstr + str(num)
    return numstr
```


```python
# run this cell to get a random set of numbers and divisors
# just run this cell

numbers = [random.randint(0, 50) for i in range(200)]
divisors = [random.randint(1, 20) for i in range(5)]
```


```python
# get your solution for the random numbers above
# just run this cell

number_string = find_if_divisible(numbers=numbers, divisors=divisors)
```


```python
# get the actual solution for the random numbers above
# just run this cell

number_string_test = sol.section3_partB(numbers, divisors)
```


```python
# test your solution here
# just run this cell

try:
    assert number_string==number_string_test
    print('passed test')
except Exception as e:
    print("number_string does not equal number_string_test")
```

    passed test
    

# Level Up (Optional) Problems

## Level Up - Part A


```python
# Your code here

def is_prime(n):
    """
    write a function that determines if a number is prime
    return True if n is prime else return False
    
    a number, n, is prime if the only divisors of the number are 1 and n 
    """
    if n > 1:
        for x in range(2, n):
            if n % x == 0:
                return False
                break
        else: 
            return True
    else:
        return False

```


```python
# run all tests in this cell
# just run this cell

random_nums = [random.randint(5, 50) for i in range(10)]
for n in random_nums:
    actual_result = is_prime(n)
    expected_result = sol.levelUp_partA(n)
    try:
        assert expected_result==actual_result
        print('test passed')
    except Exception as e:
        print("expected_result does not equal actual_result")
        print(f"{n}  is {'NOT'*(1-expected_result)} prime but you returned {actual_result}")
```

    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    

## Level Up - Part B


```python
# complete this function
# Your code here

def find_common_elements(lst1, lst2):
    """
    write a function that returns a set
    of all of the elements that are in both
    lst 1 and lst2
    
    Example
    input:
       - lst1 = [2, 3, 5, 3, 5, 3]
       - lst2 = [3, 5, 6]
       
    return:
       - (3, 5)
    """
    #return set(set(lst1) & set(lst2)) found that this works too but the more I think about why the less I understand why lol
    
    #answ = set()
    #for thing in lst1:
      #  if thing in lst2:
     #       answ.add(thing)
            
    #return answ

    return set(lst1).intersection(set(lst2)) #we didn't really cover sets formally so this was kind of cool to learn and play with
```


```python
# run the following tests
# just run this cell

for i in range(10):
    lst1 = [random.randint(0, 100) for i in range(random.randint(15, 20))]
    lst2 = [random.randint(0, 100) for i in range(random.randint(15, 20))]
    actual_result = find_common_elements(lst1, lst2)
    expected_result = sol.levelUp_partB(lst1, lst2)
    try:
        assert expected_result==actual_result
        print('test passed')
    except Exception as e:
        print("expected_result does not equal actual_result")
```

    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    test passed
    

## Level Up - Part C


```python
# write a lambda function called rng that returns the range of a list of numbers
# Your code here
rng = lambda nums: max(nums)-min(nums)
```


```python
# run these tests
# just run this cell

# this cell goes through 2 tests. 
# 1. did you write a function called rng that is actually a lambda function
# 2. is written correctly
try:
    assert '<lambda>'==rng.__name__
    print("rng is a lambda function! great work so far")
    print("running 10 random tests now")
    print("-"*50)
    for i in range(10):
        lst = [random.randint(-1000, 1000) for i in range(random.randint(10, 20))]
        actual_range = rng(lst)
        expected_range = sol.levelUp_partC(lst)
        try:
            assert actual_range==expected_range
            print('test passed, ranges are equal')
        except:
            print("expected_result does not equal actual_result")
    
except:
    print("rng is not a lambda function, must be a lambda function to continue")
```

    rng is a lambda function! great work so far
    running 10 random tests now
    --------------------------------------------------
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    test passed, ranges are equal
    


```python
# Convert this notebook to README by running this cell!
!jupyter nbconvert --to markdown assessment.ipynb && mv assessment.md README.md
```
