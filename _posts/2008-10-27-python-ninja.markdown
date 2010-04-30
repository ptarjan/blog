--- 
permalink: /2008/10/python-ninja.html
layout: post
title: Python Ninja
tags: 
- ninja
- python
- code
---
I've been doing a few programming problems from <a href='http://projecteuler.net'>Project Euler</a> and having a ton of fun. Here are a few functions that I found useful and I'm sure someone else would as well.

<h3>Prime Iteration</h3>

If you want to go through a list of integers and also know their prime factors, you could create some functions (the names should tell you what they do):

<pre class="code">
def primeFactor(n, primeSet = None) :
        ret = []
        if primeSet == None : primeSet = primesToN(int(n ** 0.5))
        for p in primeSet :
                while n % p == 0 :
                        ret.append(p)
                        n /= p
        if n != 1: ret.append(n)
        return ret

def primesToN(n):
        if n==2 : return [2]
        elif n < 2 : return []
        s = range(3, n+1, 2)
        mroot = n ** 0.5
        half = (n+1) / 2 - 1
        i = 0
        m = 3
        while m <= mroot:
                if s[i]:
                        j = (m * m - 3) / 2
                        s[j] = 0
                        while j < half:
                                s[j] = 0
                                j+ = m
                i = i + 1
                m = 2*i + 3
        return [2] + [x for x in s if x]

def primes() :
        yield 2
        D = {}
        q = 3
        while True:
                p = D.pop(q, 0)
                if p:
                        x = q + p
                        while x in D: x += p
                        D[x] = p
                else:
                        yield q
                        D[q*q] = 2*q
                q += 2
</pre>

And then you could just do this:

<pre class="code">
primeRange = itertools.imap(lambda x : (tuple(util.primeFactor(x)), x), xrange(2, 1000))
for factors, number in primeRange :
    # do something with the factors and number
</pre>

Now, this gets REALLY slow once you hit big numbers (like a million). So I wrote a generator that will go through all the numbers to n, generating them from primes instead of finding the primes from the number.

<pre class="code">
for factors, number in prange(1000) :
   # do something with factors and number

primeRange = itertools.imap(lambda x : (tuple(util.primeFactor(x)), x), xrange(2, 10))

# Same thing in different order

range(2, 1000) == prange(1000) # False
set( range(2, 1000) ) == set( prange(1000) ) # True
</pre>

And finally the prange function:

<pre class="code">
def prange(n) :
        """
prange(n) -> generator

Returns a generator for numbers from (2 to n-1) in prime base order
e.g. 
[x[1] for x in prange(10)] = [2, 3, 5, 7, 4, 6, 9, 8]

ignoring order this is a complicated way to get a range
e.g.
set([x[1] for x in prange(1000)]) == set(range(2, 1000))

The first term is a tuple (primes, powers) where len(primes) == len(powers)
e.g. 
[x[0] for x in prange(10)] = 
[(2,), (3,), (5,), (7,), (2, 2), (2, 3), (3, 3), (2, 2, 2)]

And to make sure the sums are right.
[prod(p) for p in [x[0] for x in prange(1000)]] == [x[1] for x in prange(1000)]
        """
        for count in itertools.count(1) :
                done = True
                for d, comb in primeLists(lambda : util.primes(), count, n) :
                        done = False
                        yield comb, d
                if done : break

def prod(list) :
        return reduce(operator.mul, list)

def pow(a, b) :
        return prod( [ a[i] ** b[i] for i in xrange(min(len(a), len(b)))] )

def powers(comb, lim) :
        def iterFunc() :
                for c in itertools.count(1) : yield c
        return walkIters(iterFunc, len(comb), lambda nums : pow(comb, nums), lim)

def primeCombinations(primeFunc, count, lim) :
        return walkIters(primeFunc, count, prod, lim, alwaysAscending = True)

def primeLists(primeFunc, count, lim) :
        return walkIters(primeFunc, count, prod, lim, alwaysAscending = True, allowDuplicated = True)

def walkIters(generator, count, evalFunc, lim, alwaysAscending = False, allowDuplicated = False) :
        """
walkIters(iterFunc, count, evalFunc, lim, alwaysAscending = False) -> <generator>

walks an iterator returning a tuple of (evalFunc(ret), ret) for each row, where ret = (iterval0, iterval1, ...) and it is guarenteed that evalFunc(ret) < lim
        """
        iters = [generator() for i in xrange(count)]
        nums = [i.next() for i in iters]
        pos = 0
        while pos >= 0 :
                if alwaysAscending :
                        for i in xrange(pos + 1, count) :
                                if allowDuplicated :
                                        while nums[i] < nums[i-1] :
                                                nums[i] = iters[i].next()
                                else :
                                        while nums[i] <= nums[i-1] :
                                                nums[i] = iters[i].next()

                d = evalFunc(nums)
                if d < lim :
                        yield (d, tuple(nums))
                        pos = count -1
                        nums[pos] = iters[pos].next()

                else :
                        if pos == 0 : break

                        pos -= 1
                        nums[pos] = iters[pos].next()

                        for num in xrange(pos+1, count) :
                                iters[num] = generator()
                                nums[num] = iters[num].next()

</pre>

Or if you need the primes in order of unique prime factors:

<pre class="code">
def prangePrimeOrder(n) :
        """
prange(n) -> generator

Note: This is about 2x slower than prange(n) so if you don't care about order, use prange()

Returns a generator for numbers from (2 to n-1) in prime base order
e.g. 
[x[1] for x in prange(10)] = [2, 4, 8, 3, 9, 5, 7, 6]

ignoring order this is a complicated way to get a range
e.g.
set([x[1] for x in prange(1000)]) == set(range(2, 1000))

The first term is a tuple (primes, powers) where len(primes) == len(powers)
e.g. 
[x[0] for x in prange(10)] = 
[((2,), (1,)), ((2,), (2,)), ((2,), (3,)), ((3,), (1,)), ((3,), (2,)), ((5,), (1,)), ((7,), (1,)), ((2, 3), (1, 1))]
which says [2^1, 2^2, 2^3, 3^1, 3^2, 5^1, 7^1, 2^1 * 3^1]

If you want it paired in the other direction
e.g. 
[zip(z[0], z[1]) for z in [x[0] for x in prange(10)]] =
[[(2, 1)], [(2, 2)], [(2, 3)], [(3, 1)], [(3, 2)], [(5, 1)], [(7, 1)], [(2, 1), (3, 1)]]
        """
        for count in itertools.count(1) :
                done = True
                for d, comb in primeCombinations(lambda : util.primes(), count, n) :
                        done = False
                        for pownum, nums in powers(comb, n) :
                                yield (comb, nums), pownum
                if done : break
</pre>

If anyone can speed up my code, please submit any changes. And feel free to use the code however you see fit. BSD License.
