using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text.RegularExpressions;

namespace AdventOfCode
{
    class Program
    {
        static void Main(string[] args)
        {
            string[] f = File.ReadAllLines(@"input.txt");
            int valid = 0;

            foreach (var password_policy in f)
            {
                string policy = password_policy.Split(':')[0];
                string pw = password_policy.Split(':')[1].Trim();
                string position = policy.Split(' ')[0];
                string letter = policy.Split(' ')[1];
                int first = Convert.ToInt32(position.Split('-')[0]);
                int second = Convert.ToInt32(position.Split('-')[1]);


                if ((pw[first - 1].ToString() == letter && pw[second - 1].ToString() != letter) ||
                     (pw[first - 1].ToString() != letter && pw[second - 1].ToString() == letter))
                {
                    valid++;
                }
            }

            Console.WriteLine(valid);
            
        }
    }
}
