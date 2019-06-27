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
