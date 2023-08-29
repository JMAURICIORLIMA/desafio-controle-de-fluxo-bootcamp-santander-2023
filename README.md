# DIO - Trilha Java Básico
www.dio.me

#### Autores
- [Gleyson Sampaio](https://github.com/glysns)

## Controle de Fluxo - Desafio

Vamos exercitar todo o conteúdo apresentado no módulo de Controle de Fluxo codificando o seguinte cenário.

O sistema deverá receber dois parâmetros via terminal que representarão dois números inteiros, com estes dois números você deverá obter a quantidade de interações (for) e realizar a impressão no console (System.out.print) dos números incrementados, exemplo:

* Se você passar os números 12 e 30, logo teremos uma interação (for) com 18 ocorrências para imprimir os números, exemplo: `"Imprimindo o número 1"`, `"Imprimindo o número 2"` e assim por diante.
* Se o primeiro parâmetro for MAIOR que o segundo parâmetro, você deverá lançar a exceção customizada chamada de `ParametrosInvalidosException` com a segunda mensagem: "O segundo parâmetro deve ser maior que o primeiro"


1. Crie o projeto `DesafioControleFluxo`
2. Dentro do projeto, crie a classe `Contador.java` para realizar toda a codificação do nosso programa.
3. Dentro do projeto, crie a classe `ParametrosInvalidosException` que representará a exceção de negócio no sistema.

Abaixo temos um trecho de código no qual você poderá seguir alterando as partes que contenham `??`

```java
public class Contador {
	public static void main(String[] args) {
		Scanner terminal = new Scanner(System.in);
		System.out.println("Digite o primeiro parâmetro");
		int parametroUm = terminal.??;
		System.out.println("Digite o segundo parâmetro");
		int parametroDois = terminal.??;
		
		try {
			//chamando o método contendo a lógica de contagem
			contar(parametroUm, parametroDois);
		
		}catch (? exception) {
			//imprimir a mensagem: O segundo parâmetro deve ser maior que o primeiro
		}
		
	}
	static void contar(int parametroUm, int parametroDois ) throws ParametrosInvalidosException {
		//validar se parametroUm é MAIOR que parametroDois e lançar a exceção
		
		int contagem = parametroDois - parametroUm;
		//realizar o for para imprimir os números com base na variável contagem
	}
}
```

### Passo a passo da resolução.

1. O nome do projeto ficou com `exercicio-controle-de-fluxo`.
2. Foi criada a classe principal `Contador`.
3. Também foi criada a classe de exceção `ParametrosInvalidosException`.

#### Fluxo do programa - com "exceção".

1. variáveis `parametroUm` e `parametroDois`, necessitavam `nextInt()` para funcionar.
2. Ao fornecer os valores informados, segue o fluxo para o try.
3. Dentro do try, há uma chamada para o método contar que recebe 2 parametros.
4. Dentro do método contar, os parametros são verificados.
5. Caso o `parametroDois` seja menor ou igual ao `parametroUm`, o mesmo receberá uma mensagem de "erro".
6. A exceção será capturada através do catch, disparando a mensagem.
7. O fluxo assim terminará.

#### Fluxo do programa - "Normal".

1. Os passos anteriores de 1 ao 4 são identicos.
2. O `parametroDois` maior que o `parametroUm`.
3. A validação no método `contar` é falsa e o fluxo segue adiante.
4. A variável `contagem` irá realizar uma subtração.
5. Com o valor armazenado na variável local contagem, o fluxo controlado (for) é executado.
6. Dentro do for, haverá a excução do fluxo e impressão da quantidade de interações referentes.

#### Tratamento contra entrada inválida de dado.

> Como desenvolvedor, tomei a frente para realizar tratamento contra dados inconssistentes.
> 
> Adicionei um `try` para pegar toda entrada de dados e o `catch` de `InputMismatchException`.
> 
> Informando a inconsistência e evitando uma mensagem desconhecida para o usuário.