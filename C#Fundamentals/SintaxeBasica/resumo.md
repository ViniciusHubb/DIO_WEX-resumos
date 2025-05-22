# Primeiros passos com DotNet e C#

### 1. Instalar o .NET SDK

- Acesse o site oficial: https://dotnet.microsoft.com/download
- Baixe e instale a versão recomendada do .NET SDK para seu sistema operacional
- Após instalação, no terminal do computador escreva o seguinte comando para saber se o dotnet foi instalado corretamente

```bash
dotnet --info
```

### 2. Instalar um editor de código

- **Visual Studio Code** (recomendado para iniciantes): [https://code.visualstudio.com](https://code.visualstudio.com/)
    - Instale também a extensão **C#** (desenvolvida pela Microsoft).
- Ou utilize o **Visual Studio Community** (Windows) para uma IDE mais completa: [https://visualstudio.microsoft.com](https://visualstudio.microsoft.com/)

### 3. Criar seu primeiro projeto

No terminal (Prompt de Comando, PowerShell ou Terminal do VS Code):

```bash
dotnet new console -n MeuPrimeiroProjeto
cd MeuPrimeiroProjeto

```

- Isso cria um projeto do tipo "console app" chamado MeuPrimeiroProjeto.

### 4. Rodar o projeto

No terminal, ainda dentro da pasta do projeto:

```bash
dotnet run

```

- Você verá uma mensagem como “Hello World!” no console.

### 5. Editar o código

- Abra o arquivo `Program.cs` no editor e faça modificações, por exemplo:
    
    ```csharp
    Console.WriteLine("Olá, .NET!");
    
    ```
    
- Salve e rode novamente com `dotnet run` para ver o resultado.

## Criando classes em C# no .Net

- Clicar com botão direito em uma pasta e escolher a opção `New C#`  → `class` . No exemplo abaixo vemos uma classe chamada Pessoa que está vazia

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;

namespace first_project.Models
{
    public class Pessoa
    {
        
    }
}
```

### Incrementando a classe criada

```csharp
**using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;

namespace first_project.Models
{
    public class Pessoa
    {
        public string Nome { get; set; }
        public int Idade { get; set; }
        public void Apresentar()
        {
            Console.WriteLine($"Olá meu Nome: {Nome}, E tenho: {Idade} anos");
        }
    }
}**
```

Agora temos uma classe chamada `Pessoa` que possui duas propriedades  `**public string Nome { get; set; }`  e `public int Idade { get; set; }` e um método `public void Apresentar() {}`  que imprime uma frase no console através do código que está  dentro desse método `Console.WriteLine($"Olá meu Nome: {Nome}, E tenho: {Idade} anos");`**

### Utilizando a classe Pessoa

```csharp
using first_project.Models;

Pessoa p = new Pessoa();
p.Nome = "dotnet";
p.Idade = 25;
p.Apresentar();

```

No código acima a classe `Pessoa`  no arquivo Program.cs e para isso é necessário importar a classe com `using first_project.Models;` . Com o comando `dotnet run`  no console do VS Code deverá ter como resposta: `Olá meu Nome: dotnet, E tenho: 25 anos`  no console

## Exemplo de códigos C#  .NET

### switch case e while

```csharp
string opcao;
bool exibirMenu = true;

while (exibirMenu)
{
    Console.WriteLine("Digite uma opção: ");
    Console.WriteLine("1 - Cadastrar cliente");
    Console.WriteLine("2 - Buscar cliente");
    Console.WriteLine("3 - Apagar cliente");
    Console.WriteLine("4 - Sair");
    opcao = Console.ReadLine();

    switch (opcao)
    {
        case "1":
            Console.WriteLine("Cadastrar cliente");
            break;
        case "2":
            Console.WriteLine("Buscar cliente");
            break;
        case "3":
            Console.WriteLine("Apagar cliente");
            break;
        case "4":
            Console.WriteLine("Sair");
            exibirMenu = false;
            break;
        default:
            Console.WriteLine("Opção inválida");
            break;
    }
}
Console.WriteLine("O Programa foi encerrado...");
```

Copie esse código no arquivo Programa.cs e escreva `dotnet run` no console do terminal da IDE para executar o código. Esse código é um menu interativo simples que utiliza conceitos de `switch case` e a estrutura de repetição `while`, conceitos comuns em diversas outras linguagens de programação.

### Arrays

declarando, aumentando o tamanho e copiando arrays

```csharp
int[] arrayInteiros = new int[4];

arrayInteiros[0] = 1;
arrayInteiros[1] = 2;
arrayInteiros[2] = 3;
arrayInteiros[3] = 4;

int[] arrayInteirosDobrado = new int[arrayInteiros.Length * 2];
Array.Copy(arrayInteiros, arrayInteirosDobrado, arrayInteiros.Length);
```

## Laços de repetição - for e foreach

```csharp
// fazer um array de inteiros e imprimir os valores com for e foreach
int[] arrayInteiros = new int[4];

arrayInteiros[0] = 1;
arrayInteiros[1] = 2;
arrayInteiros[2] = 3;
arrayInteiros[3] = 4;

Console.WriteLine("Percorrendo o array com for");
for (int i = 0; i < arrayInteiros.Length; i++)
{
    Console.WriteLine($"Posição Nº {i} - {arrayInteiros[i]}");
}

Console.WriteLine("Percorrendo o array com foreach");
foreach (int i in arrayInteiros)
{
    Console.WriteLine(i);
}
```

## Listas no C#

```csharp
List<string> nomes = new List<string>();

nomes.Add("Lucas");
nomes.Add("Ana");
nomes.Add("João");

for (int i = 0; i < nomes.Count; i++)
{
    Console.WriteLine($"Posição Nº {i} - {nomes[i]}");
}

foreach (string item in nomes)
{
    Console.WriteLine($"Nome: {item}");
}
```

## Próximos passos sugeridos

- Explore outros templates com `dotnet new --list` (por exemplo, web, API, classlib).
- Leia a documentação oficial: https://learn.microsoft.com/pt-br/dotnet/