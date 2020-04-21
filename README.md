# module1-task3-
﻿using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
namespace DemoApplication
{
    class Market
    {
        public int price;
        public string title;
        public Market(string title = "",  int price = 0)
        {
            this.title = title;
            this.price = price;
        }
       
    }
    class Pprod:Market
    {
        public Pprod(string title = "", int price = 0)
        {
            this.title = title;
            this.price = price;
        }
        
    }
    class Wprod : Market
    {
        public Wprod(string title = "", int price = 0)
        {
            this.title = title;
            this.price = price;
        }
        
    }
    class Serv : Market
    {
        public Serv(string title = "", int price = 0)
        {
            this.title = title;
            this.price = price;
        }
        
        static void Main(string[] args)
        {
            Pprod m1 = new Pprod("pp1", 196);
            Pprod m2 = new Pprod("pp2", 197);
            Pprod m3 = new Pprod("pp3", 199);
            Wprod m4 = new Wprod("wp1", 296);
            Wprod m5 = new Wprod("wp2", 297);
            Wprod m6 = new Wprod("wp3", 299);
            Serv m7 = new Serv("s1", 96);
            Serv m8 = new Serv("s2", 97);
            Serv m9 = new Serv("s3", 99);
            Market[] a = { m1, m2, m3, m4, m5, m6, m7, m8, m9};
            Console.WriteLine("Enter percent(0-100): ");
            int p = Int32.Parse(Console.ReadLine());
            
            int cost = 0;
            int pcost = 0;
            for (int i = 0; i < a.Length; i++)
            {
                cost+=a[i].price*p;
                if (a[i] is Pprod)
                {
                    pcost += a[i].price * p;
                }
            }
            float fcost = Convert.ToSingle(cost) / 100;
            Console.WriteLine("Cost of purchase: "+fcost.ToString() + " $");
            float bcost = Convert.ToSingle(pcost) / 100;
            Console.WriteLine("Bonus: " + bcost.ToString() + " $");
        }
    }
    
}
