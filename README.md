//# Trabalho-de-POO
//Trabalho desenvolvido por Gabriel Gail Ferreira e Bruna Cannavan Lanna

import java.util.Scanner;

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
class Conta{
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
}

public class Principal{
    public static void main (String[] args){
        public static final int max_cliente_dia = 5;
        int vetor_clientes[] = new int[max_cliente_dia];
        int i;
        
        Scanner entrada = new Scanner(System.in);
        
        System.out.println("BEM VINDO AO NOSSO SALÃO DE BELEZA!\n\n");
        
        System.out.println("De acordo com sua preferência, marque a opção que melhor lhe atende\n1 - Caso queira marcar uma consulta\n2 - Caso já tenha uma consulta marcada e queira conferir seus dados/n3 - Caso queira deixar o nosso sistema\n ");
        int numero = entrada.nextLine();
        
        switch (numero){
            case 1:
                for(i=0;i<max_cliente_dia;i++){
                    System.out.printf("/nDigite seu primeiro nome");
                    vetor_clientes.nome[i] = entrada.nextLine();
                    System.out.printf("/nAgora, a data em que deseja marcar a consulta");
                    System.out.printf("/nDia:");
                    vetor_clientes.dia[i] = entrada.nextLine();
                    System.out.printf("/nMês:");
                    vetor_clientes.mes[i] = entrada.nextLine();
                    System.out.printf("/nAno:");
                    vetor_clientes.ano[i] = entrada.nextLine();
                    
                }
                System.out.println("/nDesculpe, mas atingimos o limite de cadastros no dia, tente voltar amanhã!");
                break;
            case 2:
                String teste;
                System.out.printf("/nNome");
                teste = entrada.nextLine();
                do{
                    if(teste==vetor_clientes.nome[i]){
                        
                    }else{
                        
                    }
                    i++;   
                }(while teste!=vetor_clientes.nome[i] && i<5);
                break;
            default: System.exit(0);
        }
        
        Cliente c1,c2,c3,c4,c5;
        Data d1 = new Data (1,9,2021);
        Data d2 = new Data (2,9,2021);
        Data d3 = new Data (3,9,2021);
        c1 = new Cliente ("Maria",d1);
        c2 = new Cliente ("Ana",d1);
        c3 = new Cliente ("Francisca",d2);
        c4 = new Cliente ("Bia",d3);
        c5 = new Cliente ("Yasmin",d3);
        
        Conta c1,c2,c3;
        c1 = new Conta("Maria",1010,1000);
        
        c1.depositar(500);
        double valor = c1.getSaldo()/2;
        c1.transferir(valor,c2);
        
        c1.consulta();
        c2.consulta();*/
        
        System.out.printf("Total de clientes: %d\n\n", Cliente.total_clientes);
        
        System.out.printf("%s\n\n",c1.toString());
        System.out.printf("%s\n\n",c2.toString());
        System.out.printf("%s\n\n",c3.toString());
        System.out.printf("%s\n\n",c4.toString());
        System.out.printf("%s\n\n",c5.toString());
    }
}
