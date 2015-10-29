# What is the expected running time of the following C# code?

* Explain why using Markdown.
* Assume the array's size is n.

```c#
long Compute(int[] arr)
{
    long count = 0;
    for (int i=0; i<arr.Length; i++)
    {
        int start = 0, end = arr.Length-1;
        while (start < end)
            if (arr[start] < arr[end])
                { start++; count++; }
            else 
                end--;
    }
    return count;
}
```

**The complexity is quadratic O(n<sup>2</sup>) - each of the elements is processed 2 times. First in the for cycle then it the while cycle.**


# What is the expected running time of the following C# code?

* Explain why using Markdown.
* Assume the input matrix has size of n * m.

```c#
long CalcCount(int[,] matrix)
{
    long count = 0;
    for (int row=0; row<matrix.GetLength(0); row++)
        if (matrix[row, 0] % 2 == 0)
            for (int col=0; col<matrix.GetLength(1); col++)
                if (matrix[row,col] > 0)
                    count++;
    return count;
}
```

**The complexity is O(n*m)**


# What is the expected running time of the following C# code?

* Explain why using Markdown.
* Assume the input matrix has size of n * m.

```c#
long CalcSum(int[,] matrix, int row)
{
    long sum = 0;
    for (int col = 0; col < matrix.GetLength(0); col++) 
        sum += matrix[row, col];
    if (row + 1 < matrix.GetLength(1)) 
        sum += CalcSum(matrix, row + 1);
    return sum;
}

Console.WriteLine(CalcSum(matrix, 0));
```

**The expected complexity is n * m as the for cycle in the CalcSum method is of complexity O(n) and the method itself is called m times, so the total expected running time is O(n * m).**

