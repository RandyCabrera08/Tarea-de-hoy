#using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace proyecto3
{
    class Cliente
    {
        private string nombre;
        private int monto;

        public Cliente(string nom)
        {
            nombre = nom;
            monto = 0;
        }

        public void Depositar(int m)
        {
            monto = monto + m;
        }

        public void Extraer(int m)
        {
            monto = monto - m;
        }

        public int RetornarMonto()
        {
            return monto;
        }

        public void Imprimir()
        {
            Console.WriteLine(nombre+" tiene depositado la suma de "+monto);
        }
    }

    class Banco
    {
        private Cliente cliente1, cliente2, cliente3;

        public Banco() 
        {
            cliente1=new Cliente("Randy Cabrera");
            cliente2=new Cliente("Miguel Angel");
            cliente3=new Cliente("Pedro Matinez"); 
        }

        public void Operar()
        {
            cliente1.Depositar(10000);
            cliente2.Depositar(15000);
            cliente3.Depositar(20000);
            cliente3.Extraer(15033);
        }

        public void DepositosTotales()
        {
            int t = cliente1.RetornarMonto () + 
                    cliente2.RetornarMonto () + 
                    cliente3.RetornarMonto ();
            Console.WriteLine ("El total de dinero en el banco es:" + t);
            cliente1.Imprimir();
            cliente2.Imprimir();
            cliente3.Imprimir();
        }

        static void Main(string[] args)
        {
            Banco banco1 = new Banco();
            banco1.Operar();
            banco1.DepositosTotales();
            Console.ReadKey();
        }
    }
}
