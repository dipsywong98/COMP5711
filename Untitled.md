

At the middle of insertion process, which $X$ and $Y$ is non empty, suppose we are inserting $y\in X$ to $Y$ behind $y_i$. Define $X_i\subset X$, $X_i$ is the set of $x$ that is pointed by $y_i$ and shall be inserted after $y_i$. We relabel the pointers associated with $X_i$. For instance, for each $x\in X_i$, if $x<y$, keep the original pointers of $x$ points to $y_i$ and $y_i$ points to $x$, else update the pointers so that $x$ points to $y$ and $y$ points to $x$. The time for each incremental step is linear to the size of $X_i$, and size of $X_i$ will be shrink by at least $1$. 

The proof is similar to randomized quick sort.

For each insertion we divide a partition in $X$ to $2$ smaller partitions. In later steps we further insert elements in the two partitions using the same policy, so the process have a recurrence relationship. Define a good division as the choice of newly inserted element can divide the partition into 2 smaller ones of 25%~75% of original, then we have the recurrence
$$
T(n)=T(\frac{1}{4}n)+T(\frac{3}{4}n)+n=\Theta(n\log{n})
$$
Since the element is chosen uniformly, we have probability of 0.5 to have a good division, then we can expect a good division after 2 divisions, so that the largest partition will shrink by at least 1/4. Hence the expected run time of both good and bad division are both $O(n\log n)$



This is similar to randomized quick sort, where $X_i$ is the list of elements to be sorted in quick sort, $y$ is the pivot, and the elements in $X_i$ less than $y$ is the left partition and elements in $X_i$ greater than $y$ is the right partition. Each incremental step is the recursive step of quick sort 



---------------------------------------

Suppose we are inserting $x_i$ from $X$ to $Y$ behind $y_i$. For rest of all $x$ pointed by and to $y$ which is behind $x_i$, change $x$ to point to and by $x_i$ instead of $y_i$. 

Proof the expected run time using backward analysis. Suppose now $|Y| = m, |X| = n-m$, 

