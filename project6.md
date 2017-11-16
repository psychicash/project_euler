```Ruby
=begin
Really proud of this. Completed without having to look up more than the syntax.  I was super close
but I knew what needed to be done. Instead of creating a storage array and iterating numbers into,
I'm learning how to use the languages built in storage and iteration systems.  Excited learning 
new things.
=end

timer_start = Time.now  #this is debug code, shows how long it takes. I use it to see if 
                        #alternative methods are faster. Brute force takes longer LOL


=begin
The problem

Problem 6 
The sum of the squares of the first ten natural numbers is,

12 + 22 + ... + 102 = 385
The square of the sum of the first ten natural numbers is,

(1 + 2 + ... + 10)2 = 552 = 3025
Hence the difference between the sum of the squares of the first ten 
natural numbers and the square of the sum is 3025 − 385 = 2640.

Find the difference between the sum of the squares of the first
one hundred natural numbers and the square of the sum.


=end



sum_of_sqr = (1..100).inject(0) { |x, y| x + y**2}    
      
      #step 1, find the sum of all natural numbers squared from 1 to 100.  Ruby has a built in 
      #function for this.  Named a variable set it equal to the function.  What's happening is 
      #that the range 1-100 (including 100) are injected into the following formula. the 0 sets
      #the base and since we don't need anything added to it I set it to zero, though I suppose 
      #I could set it to 1 and have the math compute 2..100? HmmM? wonder if that's quicker?  
      #Either way, it takes the result (x) and adds it to the element (y**2).  Y is squared and 
      #then added to the result.  the result is saved via the inject method and used on the next
      #iteration until the final sum is totaled and saved
      
      
sqr_of_sum = ((1..100).inject(0) { |x, y| x + y} **2)
     
     #then step 2.  find the square of the sum of all natural numbers.  Same deal except I squared
     #the whole function not just y.
  
p result = sqr_of_sum - sum_of_sqr
     
     #then I printed it to the screen (p or puts) and set a variable to be printed as the 
     #difference of the previous 2. 3 lines of code. I'm a happy little coder. :D


p "Elapsed Time: #{(Time.now - timer_start)*1000} milliseconds"  #bottom half of that debug code
     
     #15.6 ms and I got the right answer. 
     
     
```
