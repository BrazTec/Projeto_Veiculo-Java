# Veículos: exercício de POO em Java

Exercício acadêmico de abstração, herança e encapsulamento.

**Integrantes:** Eduardo Braz de Oliveira e Willian Makoto Maeda.

O cenário do enunciado menciona uma empresa de aluguel, mas o código é uma demonstração de classes e mensagens no console. Não implementa locação, cadastro persistente ou gestão de frota.

## Estrutura

| Arquivo | Papel |
| --- | --- |
| `Veiculo.java` | Classe abstrata com marca, modelo, ano, cor e VIN |
| `Carro.java`, `Moto.java`, `Caminhao.java` | Subclasses que implementam `acelerar()` e `frear()` |
| `Main.java` | Cria um objeto de cada tipo, atribui VIN e chama os métodos |

As quatro classes de veículos declaram `package Automovel;`, embora os arquivos estejam na raiz. `Main` está no pacote padrão e importa as subclasses.

## Conceitos para revisão

- **Abstração:** `Veiculo` reúne características comuns e declara os comportamentos abstratos `acelerar` e `frear`. Não pode ser instanciada diretamente.
- **Herança:** as subclasses usam `extends Veiculo` e `super(...)` para reaproveitar o construtor da classe base.
- **Sobrescrita:** cada implementação imprime uma mensagem específica para seu tipo.
- **Encapsulamento:** apenas `VIN` é privado e acessado por `getVIN()` e `setVIN()`. Os demais atributos são públicos. O setter não valida o VIN nem o torna imutável.

O enunciado cita um método hipotético `mover()`; o código utiliza `acelerar()` e `frear()`.

## Compilar e executar

Com um JDK instalado, execute na raiz:

```sh
javac -encoding UTF-8 -d build Veiculo.java Carro.java Moto.java Caminhao.java Main.java
java -cp build Main
```

A opção `-d build` organiza as classes compiladas conforme seus pacotes. O programa mostra os VINs de exemplo e mensagens de aceleração e frenagem de carro, moto e caminhão.

Não há Maven/Gradle, testes automatizados ou validação de dados. Os métodos de movimento apenas imprimem texto; não simulam velocidade.

## Perguntas do exercício

1. Quais atributos e comportamentos são comuns aos veículos? Compare os campos de `Veiculo` com seus métodos abstratos.
2. Por que a classe base é abstrata? Observe como cada subclasse completa os comportamentos.
3. Qual a vantagem da herança? Identifique os dados inicializados uma única vez pelo construtor da classe base.
4. Como proteger o VIN? Observe o campo privado e os acessores, distinguindo acesso controlado de validação.
5. Quais limites do encapsulamento atual? Compare o VIN privado com os quatro atributos públicos.

A documentação mantém o caráter didático e a autoria do trabalho; nenhum fonte foi alterado.
