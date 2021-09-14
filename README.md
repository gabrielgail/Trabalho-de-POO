//# Trabalho-de-POO
//Trabalho desenvolvido por Gabriel Gail Ferreira e Bruna Cannavan Lanna

class Data {
    int dia, mes, ano;
    
    public Data(int dia, int m, int a){
        this.dia = dia;
        mes = m;
        ano = a;
    }
    
    public String toString(){
        return Integer.toString(dia) + "/" + Integer.toString(mes) + "/" + Integer.toString(ano);
    }
    
}

/*class Conta {
    private int agencia;
    private String cliente;
    private double saldo;

    public Conta(String c,int a,double s){
        cliente = c;
        this.agencia = a;
        this.saldo = s;
    }
    public void consulta(){
        System.out.printf("Nome: %s, Saldo: %.2f",this.cliente, this.saldo);
    }
    public void depositar(double valor){
        saldo = saldo + valor;
    }
    public void depositar(Conta c){
        c.depositar(valor);
    }
    public void transferir(double v,Conta c){
        saldo = saldo - v;
        c.depositar(v);
    }
    public int getAgencia(){
        return this.agencia;
    }
    public String getCliente(){
        return cliente;
    }
    public double getSaldo(){
        return this.saldo;
    }
    public void setAgencia(int a){
        this.agencia = a;
    }
    public void setCliente(String c){
        this.cliente = c;
    }
    public void setSaldo(double s){
        this.saldo = s;
    }
}*/

class Cliente {
    String nome;
    Data data_consulta;
    public static int total_clientes = 0;
    
    public Cliente (String n){
        nome = n;
        data_consulta = new Data (0,0,0);
        total_clientes = total_clientes + 1;
    }
    
    public Cliente (String n, Data data){
        nome = n;
        data_consulta = data;
        total_clientes = total_clientes + 1;
    }
    
    public String toString(){
        return "Nome: " + nome + "\nData Marcada: " + data_consulta.toString();
    }
    
}

public class Principal{
    public static void main (String[] args){
        Cliente c1,c2,c3,c4,c5;
        Data d1 = new Data (1,9,2021);
        Data d2 = new Data (2,9,2021);
        Data d3 = new Data (3,9,2021);
        c1 = new Cliente ("Maria",d1);
        c2 = new Cliente ("Ana",d1);
        c3 = new Cliente ("Francisca",d2);
        c4 = new Cliente ("Bia",d3);
        c5 = new Cliente ("Yasmin",d3);
        
        System.out.printf("Total de clientes: %d\n\n", Cliente.total_clientes);
        
        System.out.printf("%s\n\n",c1.toString());
        System.out.printf("%s\n\n",c2.toString());
        System.out.printf("%s\n\n",c3.toString());
        System.out.printf("%s\n\n",c4.toString());
        System.out.printf("%s\n\n",c5.toString());
    }
}
