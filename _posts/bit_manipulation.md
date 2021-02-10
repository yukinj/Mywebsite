```python
def combinationSum(A):
    res= [0] * (1<<len(A))
    for i in range(len(A)):
        for mask in range(0,(1<<i)):
            res[mask|(1<<i)] = res[mask] + A[i]
     
    #print(res)
    return res 
A = [3,4]
print(combinationSum(A)) #[0,3,4,7]
A = [1,2]
print(combinationSum(A)) #[0,1,2,3]

```