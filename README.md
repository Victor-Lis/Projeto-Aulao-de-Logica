# Projeto-Aulao-de-Logica

Projeto realizado 09/05 com o intuito de ensinar lógica de programação aos primeiro anistas da Etec Professor Carmine Biagio Tundisi

# Configurando ambiente

-   Acessar [GDBOnline](https://www.onlinegdb.com/);
- Selecionar no canto superior direito em "Language" a linguagem de programação "Java";
- Agora todas as vezes que for escrito um novo trecho de código basta clicar no botão verde "Run" e para cancelar basta clicar em "Stop"

# Lições

## java.util.Scanner 
O java.util.Scanner é uma ferramenta poderosa para ler valores via terminal. Portando o utilizaremos para podermos ler dados escritos no prompt pelo usuário, tornando assim os códigos interativos

### Etapa 1 
Precisamos orientar o Java de onde devemos buscar essa ferramenta que vamos utilizar, pois ela não é nativa do próprio Java, mas sim é uma biblioteca externa.

Então precisamos na primeira linha de código escrever o seguinte comando:
```java
import java.util.Scanner;
```

### Etapa 2
Agora que já dissemos para o Java onde ele pode buscar as informações sobre esse "Scanner", precisamos de fato utiliza-lo. 

Para isso vamos declarar esse "Scanner" dentro da class Main (classe Principal), igual no código abaixo:
```java
public class Main
{
	public static void main(String[] args) {
	    Scanner leia = new Scanner (System.in);
	}
}

```


### Etapa 3
Agora nosso sabe onde buscar esse "Scanner" e também já sabe o nome dele (no nosso caso "leia"), agora vamos de fato utilizar ele!

Vamos definir uma váriavel de tipo String para salvar o nosso nome:
```java
    String nome;
```

Agora que já temos uma váriavel para salvar o nome, vamos exibir na tela a necessidade do nosso usuário de escrever um valor (no caso o nome):

```java
    System.out.print("Escreva seu nome: ");
```

Após isso, iremos indicar que nosso sensor deve "escanear" o que foi digitado pelo usuário e atribuir valor a nossa variável:

```java
    nome = leia.next();
```

Agora que já salvamos o nome de nosso usuário, podemos escrever a mensagem "Olá (nome), tudo bem?"

```java
	System.out.println("Olá "+nome+", tudo bem?");
```

## Resultado Esperado
Agora que já foram realizadas as etapas, o código deve estar assim:
```java
import java.util.Scanner; // Indicando de onde vem esse Scanner

public class Main
{
	public static void main(String[] args) {
	    Scanner leia = new Scanner (System.in); // Dando nome e criando o Scanner no nosso código
	    String nome;
	    
	    System.out.print("Escreva seu nome: ");
	    nome = leia.next(); // Lendo o nome do usuário através do Scanner e salvando na variável 'nome'
	    
	    System.out.println("Olá "+nome+", tudo bem?"); // Exibindo nome do usuário
	}
}

```

## Recebendo valores Int e Float/Double;

### Etapa 1
Para isso iremos continuar o código acima, porém recebendo agora recebendo a "Idade" e o "Saldo Bancário" do nosso usuário, após a declaração do nosso nome iremos declarar duas novas variáveis "idade" e "saldoBancario"
```java
    String nome;
	int idade;
    float saldoBancario = 0;
```

### Etapa 2
Após a declaração de nossas váriaveis iremos sinalizar novamente para o usuário que ele precisa escrever os respectivos valores, abaixo de onde fizemos o mesmo para o nome:

```java
	System.out.print("Escreva seu nome: ");
	nome = leia.next(); // Lendo o nome do usuário através do Scanner e salvando na variável 'nome'

    System.out.print("Escreva sua idade: ");

    System.out.print("Escreva seu saldo bancário: ");
```

### Etapa 3
Agora que já sinalizamos para o usuário a eventual necessidade de escrita, precisamos de fato possibilitar isso e além disso receber os valores, então vamos lá:

#### Recebendo a idade
Vamos instruir o Scanner a ler o que foi digitado no tipo "Int", pois a idade é um tipo "Inteiro"
```java
    System.out.print("Escreva sua idade: ");
	idade = leia.nextInt();

```

#### Recebendo o saldo bancário
Vamos instruir o Scanner a ler o que foi digitado no tipo "Float", pois o saldo bancário pode incluir números pós virgula, como alguns centavos
```java
    System.out.print("Escreva seu saldo bancário: ");
    saldoBancario = leia.nextFloat();
```

### Exibindo valores
Após o trecho que exibe o nome do usuário iremos colocar um espaço e em seguida exibir sua idade e seu saldo:
```java
System.out.println(" ");
System.out.println("Olá "+nome+", tudo bem?");
System.out.println("Você tem "+idade+" anos");
System.out.println("Seu saldo é de R$"+saldoBancario);
```

## Resultado Esperado

```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {
	    Scanner leia = new Scanner (System.in);
	    String nome;
	    int idade;
        float saldoBancario = 0;
	    
	    System.out.print("Escreva seu nome: ");
	    nome = leia.next();
	    
	    System.out.print("Escreva sua idade: ");
	    idade = leia.nextInt();

        System.out.print("Escreva seu saldo bancário: ");
        saldoBancario = leia.nextFloat();

        System.out.println(" ");	    
	System.out.println("Olá "+nome+", tudo bem?");
        System.out.println("Você tem "+idade+" anos");
        System.out.println("Seu saldo é de R$"+saldoBancario);
	}
}
```

## Trabalhando com 'if' e 'else'
Nesse próximo exemplo iremos de acordo com a idade do usuário exibir ou não seu saldo para treinarmos o uso de if e else

### Operadores lógicos
```
> < | Maior e menor
```

```
&& | E
```

```
|| | Ou
```

### Etapa 1
Após o trecho em que iremos receber a idade do usuário iremos escrever if para caso a idade seja menor de 18 exibir que ele é menor de idade, ou seja menor de 18 anos:
```java
	System.out.print("Escreva sua idade: ");
	idade = leia.nextInt();
    if(idade < 18){
        System.out.println("Menor de idade!");
    }
```

### Etapa 2 
Agora iremos adicionar um else(então) para caso o usuário tenha 18 anos ou mais logo abaixo do if:
```java
	System.out.print("Escreva sua idade: ");
	idade = leia.nextInt();
    if(idade < 18){
        System.out.println("Menor de idade!");
    }else{
        System.out.println("Maior de idade!");
    }
```

### Etapa 3 
Então iremos mover a parte em que recebemos o saldo bancário para dentro do else e apenas exibir esse saldo se for maior de idade
```java
else{
    System.out.println("Maior de idade!");
            
    System.out.print("Escreva seu saldo bancário: ");
    saldoBancario = leia.nextFloat();
}
```

E agora iremos colocar outro if, para exibir apenas se o usuário for maior de idade, ou seja maior ou igual a 18 anos (no fim do código):
```java
    if(idade >= 18){
        System.out.println("Seu saldo é de R$"+saldoBancario);
    }
```

## Funções
Agora vamos trabalhar de uma maneira diferente, iremos chamar uma função que irá tomar conta de exibir ou não o saldo do usuário:

### Etapa 1
Iremos declarar nossa função "exibirSaldo" para ficar responsável por essa função:

Seguindo a seguindo explicação:
- public - Acessado de todos os arquivos do projeto
- static - Não sofrerá alteração
- void - Não retorna nenhum valor
- nome - Nome para chamar a função posteriormente
- (int idade, float saldo) - São nossos parâmetros, para executar o trecho de código da função precisamos passar esses parâmetros

```java
	public static void exibirSaldo(int idade, float saldo){
		
	}
```

### Etapa 2
Adicionaremos a mesma lógica de programação já aplicada no código:
Exibiremos a idade, se a idade for maior de 18 anos ele pulará linha e exibirá o saldo, se não ele completará a mensagem de idade exibindo quanto tempo falta para o usuário ter um saldo bancário.
```java
	public static void exibirSaldo(int idade, float saldo){
	    System.out.print("Você tem "+idade+" anos");
	    if(idade >= 18){
	        System.out.println("");
	        System.out.println("Seu saldo é de R$"+saldo);
	    }else{
	        System.out.print(", em "+(18-idade)+" anos você podera ter um saldo bancário!");
	    }
	}
```

### Etapa 3 
Agora iremos subistituir as mensagens de idade e saldo pela chamada da função
#### Antes
```java
        System.out.println(" ");	    
	System.out.println("Olá "+nome+", tudo bem?");
        System.out.println("Você tem "+idade+" anos");
        System.out.println("Seu saldo é de R$"+saldoBancario);
```

#### Depois
```java
        System.out.println(" ");	    
	System.out.println("Olá "+nome+", tudo bem?");
        exibirSaldo(idade, saldoBancario);
```

## Resultado Esperado
```java
import java.util.Scanner;

public class Main
{
	public static void main(String[] args) {
	    Scanner leia = new Scanner (System.in);
	    String nome;
	    int idade;
        float saldoBancario = 0;
	    
	    System.out.print("Escreva seu nome: ");
	    nome = leia.next();
	    
	    System.out.print("Escreva sua idade: ");
	    idade = leia.nextInt();

        if(idade < 18){
            System.out.println("Menor de idade!");
        }else{
            System.out.println("Maior de idade!");
            
            System.out.print("Escreva seu saldo bancário: ");
            saldoBancario = leia.nextFloat();
        }

        System.out.println(" ");	    
	    System.out.println("Olá "+nome+", tudo bem?");
        exibirSaldo(idade, saldoBancario);
	}
	
	public static void exibirSaldo(int idade, float saldo){
	    System.out.print("Você tem "+idade+" anos");
	    if(idade >= 18){
	        System.out.println("");
	        System.out.println("Seu saldo é de R$"+saldo);
	    }else{
	        System.out.print(", em "+(18-idade)+" anos você podera ter um saldo bancário!");
	    }
	}
}
```

## Autores
- [@Victor Lis](https://github.com/Victor-Lis)

Agradeço também a ajuda de meus dois amigos, que fizeram esse projeto ser possível:
- [@Cauã de Oliveira](https://github.com/CauaStos)
- [@Juliano Santos](https://github.com/sntoosk)
