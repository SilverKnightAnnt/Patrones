# Patrones

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using CapaLogica;

namespace OpercionesBasicas
{
    class UI
    {
        static Gestor miGestor = new Gestor();

        static void Main(string[] args)
        {
            MostrarMenu();
        }

        static void MostrarMenu()
        {
            int opcion = -1;

            while (opcion != 5)
            {
                Console.WriteLine();
                Console.WriteLine("----MENÚ PRINCIPAL----");
                Console.WriteLine();
                Console.WriteLine("1. Suma.");
                Console.WriteLine("2. Resta.");
                Console.WriteLine("3. Multiplicación.");
                Console.WriteLine("4. División.");
                Console.WriteLine("5. Salir.");
                Console.WriteLine();
                Console.WriteLine("Seleccione la operación a realizar: ");
                Console.WriteLine();
                opcion = Int32.Parse(Console.ReadLine());
                ProcesarOpcion(opcion);
            }            
        }

        static void ProcesarOpcion(int popcion)
        {
            switch (popcion)
            {
                case 1:
                    PedirValoresSuma();
                   
                    break;

                case 2:
                    PedirValoresResta();
                    break;

                case 3:
                    PedirValoresMultiplicacion();
                    break;

                case 4:
                    PedirValoresDivision();
                    break;

                case 5:
                    Console.WriteLine("Gracias por usar el sistema.");
                    break;
                default:
                    Console.WriteLine("Opción incorrecta.");
                   
                    break;
            }
        }

        

        static void PedirValoresResta()
        {
            double valor1;
            double valor2;
            String tipo = "Resta";

            Console.WriteLine("Digite el primer número: ");
            valor1 = int.Parse(Console.ReadLine());
            Console.WriteLine("Digite el segundo número: ");
            valor2 = int.Parse(Console.ReadLine());

            Operacion tmpOperacion = new Operacion(tipo, valor1, valor2, 0);
            Console.WriteLine();
            Console.WriteLine("Resta: " + miGestor.procesar(tmpOperacion).resultado);
            
        }

        static void PedirValoresMultiplicacion()
        {
            double valor1;
            double valor2;
            String tipo = "Multiplicación";

            Console.WriteLine("Digite el primer número: ");
            valor1 = int.Parse(Console.ReadLine());
            Console.WriteLine("Digite el segundo número: ");
            valor2 = int.Parse(Console.ReadLine());

            Operacion tmpOperacion = new Operacion(tipo, valor1, valor2, 0);
            Console.WriteLine();
            Console.WriteLine("Multiplicación: " + miGestor.procesar(tmpOperacion).resultado);
           
        }

        static void PedirValoresDivision()
        {
            double valor1;
            double valor2;
            String tipo = "División";

            Console.WriteLine("Digite el primer número: ");
            valor1 = int.Parse(Console.ReadLine());
            Console.WriteLine("Digite el segundo número: ");
            valor2 = int.Parse(Console.ReadLine());

            Operacion tmpOperacion = new Operacion(tipo, valor1, valor2, 0);
            Console.WriteLine();
            Console.WriteLine("División: " + miGestor.procesar(tmpOperacion).resultado);
           
        }
    }


}
