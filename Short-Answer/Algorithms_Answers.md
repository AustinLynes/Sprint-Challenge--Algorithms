#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
a = 0  ==> O(1)
while a < n^3 : a = a + n * n O(log n)

i believe this one is O(log n)
because we are traversing over the list and we are only hitting a portion

b)
sum = 0  O(1)
for i in range(n): o(n)  the size of the list will grow in proportion to n
    j = 1  O(1)
    while j < n: hmm... j will increment by 2s to get to n  1/2(n) soo... n?
        j *= 2 
        sum += 1

O(n) * o(n)

i believe this one is O(n^2)
because the outer loop is going to grow with the size of n
and the inner while loop is going to go twice the speed to catch up to n 
so n * n  = n^2


c)

def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)  # this is going to recursivly call itself for every bunny it sees

recursion... O(n) because it grows linearly with bunnies

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.

hmmm...

UNDERSTAND 

o .
___ .                                                   there are n amount of floors
f10|   .                                                  we want to minimize the amount of eggs broken and drops
f9 |     .
f8 |       .
f7 |        .
f6 |        .
f5 |        .
f4 |        .
f3 |        .
f2 |        .
f1 |      \ V /


n = 10

[ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ]

say i throw an egg from the 5th story.  half of the list
it doesn't break.  move up and try again..
we need to try again. but with 6-10 

[ 6, 7, 8, 9, 10 ]

now we throw from the 8th story 
it breaks... move down and try again
we need to try again.. but with 6 - 7

[ 6, 7 ]

tries 7 
it breaks. .. there is only two options return the other


My Method Binary Search Tree


create an array with values from 1 to the nth floor                        " because you cannot throw an egg from the basement"
walk through each floor inside the array, 
start at the halfway point of the array len(arr) // 2 
make a toss
if it breaks. we need to move downward..
if it doesn't break... we need to move upward
if at any point we only have two values to check after we see if it broke or not.. return the other value

depending on if it broke or not, 
we will recursivly call this function with the half of the list top or bottom to see if the mid point will break or not.


depending on the size of the input...
i believe this would come out to be O(log n)
because it would take much fewer steps to complete than the actual size of the input but its not constant.