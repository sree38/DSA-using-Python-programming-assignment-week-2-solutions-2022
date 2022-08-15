# DSA-using-Python-programming-assignment-week-2-solutions-2022

# Write a function intreverse(n) that takes as input a positive integer n and returns the integer obtained by reversing the digits in n.

def intreverse(n):

  ans = 0
  
  
  while n > 0:
  
  (d,n) = (n%10,n//10)
  
  ans = 10*ans + d
  
  return(ans)

print(intreverse(783))

print(intreverse(242789))

print(intreverse(3))


# Write a function matched(s) that takes as input a string s and checks if the brackets "(" and ")" in s are matched: that is, every "(" has a matching ")" after it and every ")" has a matching "(" before it. Your function should ignore all other symbols that appear in s. Your function should return True if s has matched brackets and False if it does not.

def matched(s):

  nested = 0
  
  for i in range(0,len(s)):
  
    if s[i] == "(":
    
       nested = nested+1
       
    elif s[i] == ")":
    
       nested = nested-1
       
       if nested < 0:
       
          return(False)    

return(nested == 0)

print(matched("a3qw3;4w3(aasdgsd)((agadsgdsgag)agaga)"))

print(matched("(ag(Gaga(agag)Gaga)GG)a)33)cc("))

print(matched("(adsgdsg(agaga)a"))

print(matched("15ababa.agaga[][[["))


# Write a function sumprimes(l) that takes as input a list of integers l and retuns the sum of all the prime numbers in l.

def factors(n):

  factorlist = []

for i in range(1,n+1):

if n%i == 0:

factorlist = factorlist + [i]

return(factorlist)

def isprime(n):

return(factors(n) == [1,n])

def sumprimes(l):

sum = 0

for i in range(0,len(l)):

if isprime(l[i]):

sum = sum+l[i]

return(sum)

import ast

def tolist(inp):

inp = "["+inp+"]"

inp = ast.literal_eval(inp)

return (inp[0],inp[1])

def parse(inp):

inp = ast.literal_eval(inp)

return (inp)

fncall = input()

lparen = fncall.find("(")

rparen = fncall.rfind(")")

fname = fncall[:lparen]

farg = fncall[lparen+1:rparen]

if fname == "intreverse":

arg = parse(farg)

print(intreverse(arg))

elif fname == "matched":

arg = parse(farg)

print(matched(arg))

elif fname == "sumprimes":

arg = parse(farg)

print(sumprimes(arg))

else:

print("Function", fname, "unknown")

print(sumprimes([101,93,97,44]))

print(sumprimes([1001,393,743,59]))

print(sumprimes([11,11,11,13,11,-11]))














