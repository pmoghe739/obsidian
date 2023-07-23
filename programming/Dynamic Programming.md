Each dp problem should be able to be classified into sub problems , that are being repeatedly computed .
Than our goal is to solve i by 2 approaches ,1 memoization where we store all results. (this is simple to implement since we only need to add cache to the brute force recursive solution.)
 2 bottom up DP where we break the DP into sub problems and create. a directed "acyclic graph" of the dependency and then solve the dependencies first and keep going untill all is resolved.

Approach.

Break thne problem into sub problems on which it depends, based on the choice we have like for maximizing at iyth step , what all options we have among which we need to find maximum.

for example in fibonacci -< f(n) = f(n-1)+f(n-2)
for flowerbox. problem f(n) = Math.max(f(n+1), f(n+2)+arr[i]) because fere at each step i we need to maximize the height and we have two choices whether to plant flower here or not. each choice results in different sub problem which need to be solved to solve the current height problem. 
