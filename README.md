using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Logistics
{
    class Logistics
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());

            int miniBus = 0;
            int truck = 0;
            int train = 0;

            for (int i = 0; i < n; i++)
            {
                int tones = int.Parse(Console.ReadLine());

                if (tones < 4)
                {
                    miniBus += tones;
                }
                else if (tones < 12)
                {
                    truck += tones;
                }
                else
                {
                    train += tones;
                }
            }

            int allTones = miniBus + train + truck;

            double miniBusPercentage = ((double)miniBus / allTones) * 100;
            double truckPercentage = ((double)truck / allTones) * 100;
            double trainPercentage = ((double)train / allTones) * 100;

            decimal averagePrice = (miniBus * 200.00m) + (truck * 175.00m) + (train * 120.00m);
            averagePrice /= (decimal)allTones;

            Console.WriteLine($"{averagePrice:f2}");
            Console.WriteLine($"{miniBusPercentage:f2}%");
            Console.WriteLine($"{truckPercentage:f2}%");
            Console.WriteLine($"{trainPercentage:f2}%");
        }
    }
}
