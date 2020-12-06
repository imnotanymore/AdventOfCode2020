using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text.RegularExpressions;

namespace AdventOfCode
{
    public class Day2Part1
    {

        static void Main(string[] args)
        {
            string[] f = File.ReadAllLines(@"input.txt");



            int valid = 0;

            foreach (var password_policy in f)
            {
                string line = password_policy.Split(':')[0];
                string pw = password_policy.Split(':')[1].Trim();
                string policy = line.Split(' ')[0];
                string letter = line.Split(' ')[1];
                int min = Convert.ToInt32(policy.Split('-')[0]);
                int max = Convert.ToInt32(policy.Split('-')[1]);
                int letterCount = Regex.Matches(pw, letter).Count;

                if (letterCount >= min && letterCount <= max)
                {
                    valid++;
                }       
            }

            Console.WriteLine(valid);
        }
        
   
            




    }
}
    

