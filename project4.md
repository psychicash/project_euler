```ruby


=begin

A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99.

Find the largest palindrome made from the product of two 3-digit numbers.

=end

# The reverse(x) function converts the variable(int) to a string, reverses the string,
# converts this back to an int and then compares the result to the submitted variable.  
# If it matches it is added to the array and if not, discarded.

def reverse(x) 
  if x.to_s.reverse.to_i == x
     $pal.push(x)
  else

  end
end


# The searching function, defines the math used to iterate through.  I set a limit though
# so to break up the searching into 10 chunks of 100 numbers for the x.  This made it easier
# for the computer to return the data.  otherwise, it always timed out (weak computer) lol


def searching(limit)

#here i am defining the instance variables as starting points.  taking care to only let x iterate
#from the limit up to 99+.  This means 900 to 999, 800 to 899, etc.  The y will go through the whole
# 999 everytime.

  x = limit + 99
  y = 999

#the origy is used to reset the y after each x declination.  this ensures that each y is tested against each x.

origy = 999

 
#now the loop kicks in. 
  until x < limit do
  #this will loop untli x is less than the limit ensuring that is won't stop until x = 899 on the first case.
           
           
           if y == 99                     # this if statement sees if y == 99.  This is the marker for where
             origy -= 1                   # y, one of the numbers to be multiplied, goes from a three digit
             y = origy                    # number, to a two digit.  If so, it's outside the range.  So origy
             x -= 1                       # goes down by 1 because at 999 * 998 (x's new value after the first declination)
             z = x * y                    #  that was already done, it keeps down on repeated products.  Finally 
              reverse(z)                  # a product is produced and sent through the reverse function
          else
             z = x * y                    #if y != 99 then there's no reason to go through all the variable changes because
             reverse(z)                   # we are still  in the middle of a cycle.  So a product is produced, compared and then
             y -= 1                       # y is reduced by 1.
          end
  end                                     #there's no single return for this function because it pushes all of the values that meet
                                          #criteria to the array.
end

# pal is the palindrome array, set to global so everyone can have some fun.

$pal = []

# lim here defines the limit of each individual search.  In this case all numbers 
# 100 to 999 * 900 to 999 are defined in the following loop by this variable.
# it starts at  900 and is subtracted later by 100 increments.

lim = 900


# loop that defines the end limit or end of the iterations while calling the searching 
# function inside of it.  After it pushes the results from the first 100 x values, it 
# subtracts 100 from the limit and does it again.

while lim > 99 do
   searching(lim)
   lim -= 100
end



#finally, just for fun, I had it print all of the values in the array.  There were quite 
#a few of them. After filling up the screen, I had it sort the array from least to 
#largest and then give me the largest value on the screen.

print $pal
puts $pal.sort!.last



```
