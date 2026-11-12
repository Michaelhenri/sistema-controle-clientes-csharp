# Sistema de Controle de Clientes em C# (POO)

Projeto desenvolvido como parte das atividades práticas do curso técnico de Programação Back-End (SENAI), com o objetivo de implementar os pilares da **Programação Orientada a Objetos (POO)** e regras de negócio em um sistema de console em C#.

## 🎯 Objetivo e Fins Didáticos

Este sistema foi construído para fins acadêmicos e didáticos para demonstrar a aplicação prática de:
- **Abstração**: Modelagem de entidades do mundo real em classes e objetos.
- **Herança**: Reaproveitamento de atributos e métodos comuns de uma classe pai (`Clientes`) para classes filhas (`Pessoa_Fisica` e `Pessoa_Juridica`).
- **Polimorfismo (`override`)**: Sobrescrita de métodos para alterar o comportamento do cálculo de impostos de acordo com o tipo de cliente.
- **Encapsulamento**: Proteção de dados sensíveis e controle de alteração de propriedades utilizando modificadores de acesso (`protected set`).

---

## ⚙️ Regras de Negócio e Funcionalidades

O sistema interage com o usuário via terminal (console), solicitando dados básicos e aplicando regras tributárias específicas:

1. **Entrada de Dados Dinâmica**: O usuário informa o nome, endereço e escolhe se deseja cadastrar uma **Pessoa Física (`f`)** ou **Pessoa Jurídica (`j`)**.
2. **Pessoa Física**:
   - Requer o preenchimento de **CPF** e **RG**.
   - Aplica uma alíquota de **10% de imposto** sobre o valor da compra informada.
3. **Pessoa Jurídica**:
   - Requer o preenchimento de **CNPJ** e **Inscrição Estadual (IE)**.
   - Aplica uma alíquota de **20% de imposto** sobre o valor da compra informada (*polimorfismo aplicado no método `Pagar_Imposto`*).
4. **Saída Formatada**: Exibe um resumo completo contendo os dados cadastrais, o valor da compra, o imposto calculado e o valor total a pagar formatados em moeda nacional (`R$`).

---

## 🛠️ Como o Código Foi Desenvolvido e Criado

O projeto foi estruturado utilizando o ambiente de desenvolvimento **Visual Studio Code** em conjunto com o **.NET SDK**, seguindo a arquitetura orientada a objetos:

1. **Configuração Inicial do Projeto**:
   - Criação de um aplicativo de console via terminal utilizando o .NET CLI:
```powershell
dotnet new console -o Atividade
```
2. **Implementação da Classe Pai (`Clientes.cs`)**:
   - Contém os atributos genéricos (`nome`, `endereco`, `valor`, `valor_imposto`, `total`) e o método virtual `Pagar_Imposto(float v)`.
3. **Implementação das Classes Derivadas (`Pessoa_Fisica.cs` e `Pessoa_Juridica.cs`)**:
   - Utilização de herança (`: Clientes`) para herdar características da classe pai e adição de atributos específicos.
   - Na classe de Pessoa Jurídica, utilizou-se a palavra-chave `override` para sobrescrever o cálculo do imposto para 20%.
4. **Orquestração e Execução (`Program.cs`)**:
   - Utilização de estruturas condicionais (`if`) para direcionar o fluxo de acordo com a escolha do usuário (`f` ou `j`), capturando as entradas via `Console.ReadLine()` e exibindo os resultados formatados na tela.

---

## 🚀 Como Executar o Projeto

Se você quiser clonar e rodar este projeto na sua máquina, siga os passos abaixo:

1. Certifique-se de ter o **.NET SDK** instalado na sua máquina.
2. Clone o repositório ou baixe os arquivos:
   ```bash
   git clone https://github.com/Michaelhenri/sistema-controle-clientes-csharp.git
   ```
3. Abra a pasta do projeto no seu terminal ou no VS Code.
4. Execute o comando para compilar e rodar a aplicação:
   ```powershell
   dotnet run
   ```

---

## 👨‍💻 Autor
Desenvolvido por **Michael Henrique** durante a jornada de capacitação técnica em Programação Back-End.
