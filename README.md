# Jagged_Array_Table
C# Program to create a Jagged Array Table in which random ratings are placed for each pool. The ratings are later used to find the average rating per pool


using System;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.Linq;
using System.Security.Cryptography.X509Certificates;

namespace ArrayLearn
{
    class Program
    {
       static private int[][] jagged1;
       static private string [] name;
       static private string [] names;
        static void Main(string[] args)
        {// The purpose of the program is to place random inputs to a table using a jagged array to  The rating 
            // will be used to match each pool from a group of Occupants A to H if The occupants don't rate some pools 
            // The average is calculated for each pool.

           jagged1 = RandomValues.Arrays(); // The Jagged array variable jagged is passed to jagged1
            name = RandomValues.Names(); // The row names are  returned to as a string array
            names = RandomValues.ColName(); // The column names are returned to as a column name
            RandomValues.Looping(jagged1,name, names); // The Random values are jagged multidimensional array values The name and name string array passed arguments.


        }

        

    }
   class RandomValues
    {

        public static int[][] Arrays()
        {
            Console.WriteLine("The random pool depth out of 20 rating" );// The prompt necessary for the display of a 20 rating
            Random r = new Random(); // Create a random class

            //use int[] here
            
            int rand = r.Next(20); // Random method to see the next value out of 20 or 0 to 19
            int rand1 = r.Next(20);
            int rand2 = r.Next(20);
            int rand3 = r.Next(20);
            int rand4 = r.Next(20);
            int rand5 = r.Next(20);
            int rand6 = r.Next(20);
            int rand7 = r.Next(20);
            int rand8 = r.Next(20);
            int rand9 = r.Next(20);
            int rand10 = r.Next(20);
            int rand11 = r.Next(20);
            int rand12 = r.Next(20);
            int rand13 = r.Next(20);
            int rand14 = r.Next(20);
            int rand15 = r.Next(20);
            int rand16 = r.Next(20);
            int rand17 = r.Next(20);
            int rand18 = r.Next(20);
            int rand19 = r.Next(20);
           int[][]  jagged =                                                         
            {// Declare a jagged array with the input of random integers  with varying lengths
               new int[] {rand,rand1,rand2,rand3},
               new int[] {rand4,rand5, rand6,rand7, rand8, rand9, rand10,rand11},
               new int[] {rand12,rand13,rand14},
               new int[] {rand15,rand16},
               new int[] {rand17,rand18, rand19}
           };
            return jagged;// Return The jagged array jagged.

        }
        public static string[] Names()
        {// The Row names are created as a string to be returned as a string array
            string[] names = { "John Pool Rating ", "Peter's Pool Rating", "Musa Pool Rating", "Harry Pool Rating", "Mansa Pool Rating " };
            return names;    // names is is returned as  a string array.
        }
        public static string[] ColName()
        {// The name of the occupants average group rating.
            string[] colnames = { " A ", " B ", " C ", " D ", " E " , " F " , " G " , " H " };
            return colnames; // return the column names as col name
        }
        public static void Looping(int[][] jagged, string[] name, string[] n)// The parameters are passed down from the main method
        {
            int[] sum = new int[5];

            Console.Write("       \t\t");// The program prompt is created for the space created
            for (int a = 0; a < n.Count(); a++)
            {
                Console.Write( n[a] + "\t"); // The column name are looped to the console.
            }
            Console.WriteLine();
            for (int i = 0; i < name.Count(); i++)// Use the Count() keyword works especially well with jagged arrays.
            {
                Console.Write(name[i] + "\t");
                foreach (var item in jagged[i])// The jagged array from the index of the columns index is created to foreach in the for loop.
                {
                    Console.Write(item + "\t");// The iteration from the jagged array is created and the full values are printed out.
                    
                }
                Console.WriteLine("\n"); // A line is created after every row
            }
            Console.WriteLine();
            Console.WriteLine("Blank spaces are the places in which the occupants chose not to vote to at the survey out of 20 " );
            // A prompt is created to inform the user.
            for (int a = 0; a < name.Count(); a++)
            {
                Console.Write(name[a]);
            // The name iteration is created to display every name 
            }
            for (int b = 0; b < jagged.Count(); b++)
            {
                for (int i = 0; i < jagged[b].Count(); i++)
                {
                   sum[b] += jagged[b][i]; // The sum is calculated to a sum integer array by the jagged array : jagged.
                }
            
            }
            Console.WriteLine();
            for (int f = 0; f < sum.Count(); f++)// The for loop is neccessary for each iteration.
            {
                decimal avg;
                avg = sum[f] / jagged[f].Count(); // The average is used to  be placed in the output prompt by dividing the sum array with 
                // The jagged array length jagged[f].Count();

                Console.WriteLine("The average is :" + name[f] + " " + avg);// The name of the Pool Guy and the 
            }

        }
        


    }

}
