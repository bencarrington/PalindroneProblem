# Palindrone Problem
C# how to solve a palindrone problem.


```CSharp
using System;
using System.Text.RegularExpressions;

namespace Palindrone
{
    class Program
    {
        static void Main(string[] args)
        {
			Regex regex = new Regex(@"[A-Za-z0-9]");
			bool isPalindrone = false;

			string phrase = "Too bad--I hid a boot1.";
			var regResults = regex.Matches(phrase.ToLower());

			int compares = regResults.Count / 2;
			int length = regResults.Count - 1;

			for (int i = 0; i < compares; i++)
			{
				Console.WriteLine($"Compare {regResults[i].Value} : {regResults[length].Value}");
				if (regResults[i].Value == regResults[length].Value)
				{
					isPalindrone = true;
					length--;
					continue;
				}
				else
				{
					isPalindrone = false;
					break;
				}
			}

			Console.Write(isPalindrone);
			Console.ReadKey();
        }
    }
}

```

# C# Very Large sum
[A Very Big Sum (HackerRank)](https://www.hackerrank.com/challenges/a-very-big-sum/problem)

```C#
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Collections;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Text.RegularExpressions;
using System.Text;
using System;

class Solution {

    // Complete the aVeryBigSum function below.
    static long aVeryBigSum(long[] ar) {
        long sum = 0;
        foreach(long num in ar)
        {
            sum += num;
        }
        return sum;
    }

    static void Main(string[] args) {
        TextWriter textWriter = new StreamWriter(@System.Environment.GetEnvironmentVariable("OUTPUT_PATH"), true);

        int arCount = Convert.ToInt32(Console.ReadLine());

        long[] ar = Array.ConvertAll(Console.ReadLine().Split(' '), arTemp => Convert.ToInt64(arTemp))
        ;
        long result = aVeryBigSum(ar);

        textWriter.WriteLine(result);

        textWriter.Flush();
        textWriter.Close();
    }
}

```
# Diagonal Difference
[HackerRank Diagonal Difference](https://www.hackerrank.com/challenges/diagonal-difference/problem)

```C#
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Collections;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Text.RegularExpressions;
using System.Text;
using System;

class Result
{

    /*
     * Complete the 'diagonalDifference' function below.
     *
     * The function is expected to return an INTEGER.
     * The function accepts 2D_INTEGER_ARRAY arr as parameter.
     */

    public static int diagonalDifference(List<List<int>> arr, int n)
    {
        int sum1 = 0;
        int sum2 = 0;
        for(int i = 0; i < n; i++)
        {
            sum1 += arr[i][i];
            sum2 += arr[(n-1)-i][i];
        }
        return Math.Abs(sum1 - sum2);
    }

}

class Solution
{
    public static void Main(string[] args)
    {
        TextWriter textWriter = new StreamWriter(@System.Environment.GetEnvironmentVariable("OUTPUT_PATH"), true);

        int n = Convert.ToInt32(Console.ReadLine().Trim());

        List<List<int>> arr = new List<List<int>>();

        for (int i = 0; i < n; i++)
        {
            arr.Add(Console.ReadLine().TrimEnd().Split(' ').ToList().Select(arrTemp => Convert.ToInt32(arrTemp)).ToList());
        }

        int result = Result.diagonalDifference(arr,n);

        textWriter.WriteLine(result);

        textWriter.Flush();
        textWriter.Close();
    }
}

```
# Steps Challenge

```C#
using System.CodeDom.Compiler;
using System.Collections.Generic;
using System.Collections;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.IO;
using System.Linq;
using System.Reflection;
using System.Runtime.Serialization;
using System.Text.RegularExpressions;
using System.Text;
using System;

class Solution {

    // Complete the staircase function below.
    static void staircase(int n) {
        for(int i = 1; i <= n; i++){
            for(int j = 0; j < n-i; j++){
                Console.Write(" ");
            }
            for(int k = 0; k < i; k++){
                Console.Write("#");
            }
            Console.WriteLine();
        }
    }

    static void Main(string[] args) {
        int n = Convert.ToInt32(Console.ReadLine());

        staircase(n);
    }
}

```
