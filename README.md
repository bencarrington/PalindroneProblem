# PalindroneProblem
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
