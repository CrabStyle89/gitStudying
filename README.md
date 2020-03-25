# gitStudying


First Task:
Solve the longest common prefix problem on leetcode in C#. Create a github project, document the task and solution in a README.md, add a screenshot that shows that all tests pass. Add comments in code, mention the computational complexity of the solution. Add a link in a post in this doc.


Solution:


  public class Solution
    {
        public string LongestCommonPrefix(string[] strs)
        {
            string prefix = "";
            for (int j = 0; j < strs[0].Length; j++)    // start checking from letters in words
            {
                int count = 0;                          //this count is for checking how many similarities we have
                for (int i = 0; i < strs.Length; i++)  // incrementing counter for words
                {
                    char a = strs[i][j];                //only for checking status while debuging
                    char b = strs[0][j];                //only for checking status while debuging
                    if (a == b)
                    {
                        count++;
                        if (count == strs.Length)       //if number of similarities is equal to length of massive 
                            prefix += a;                // we add to our prefix single char 
                    }
                    else if (a != b && prefix != "")    //if condition is true than we have the end of our checking
                    {
                        return (prefix);
                    }
                    else if (a != b && prefix == "")    //if condition is true than there are no common prefix in our massive 
                    {
                        Console.WriteLine("there is no common prefix");
                        return (null);
                    }

                }

            }
            return (prefix);
        }
    }
}
