core idea?
- Every composite number must be visited and marked by its smallest prime factor (SPF) exactly once
	- Fundamental Theorem of Arithmetic?
	- here, because p is the smallest prime factor, it cannot be strictly graeater then any prime factor dividing 
	- ![[Pasted image 20261004233803.png]]
	- `p > spf[i]` is equivalent to stopping after `i % p == 0`
	>each number -> unique prim factors = (its smallest prime factor) $\times$ (everything else)  
	> to avoid duplicates -> num i is only allowed to form from its biggest  number remaining * smallest prime factor it has
	> eg - 36 = 2 * 18