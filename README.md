# Santander Boot Camp 2025

* 🐾 PetMachine - Sistema Automatizado de Banho para Pets

* Projeto Java para simulação de uma máquina de banho para pets com:
* Controle de estoque de água e shampoo
* Gerenciamento do estado de limpeza do pet e da máquina
* Fluxo interativo via terminal
* Validações de regras de negócio para operações
 
* 🛠️ Tecnologias Utilizadas
* Java 17+
* Scanner para entrada de dados
* Classes especializadas (Pet e PetMachine)
* Encapsulamento de propriedades
* Menu interativo com switch-case
* Validações de estado para operações
 
* 📚 Pré-requisitos
* Java JDK 17 ou superior
* Conhecimento básico de compilação Java
* Terminal/Console para execução
 
* 🚀 Como Executar
* Compile o programa:
* bash
* javac -d bin src/Main.java src/Pet.java src/PetMachine.java
* Execute o programa:
 
* bash
* java -cp bin Main
* Siga o fluxo interativo:
 
 
* ===Escolha uma das opções===
* 1 - Dar banho no pet
* 2 - Abastecer a máquina com água
* 3 - Abastecer a máquina com shampoo
* 4 - Verificar água da máquina
* 5 - Verificar shampoo da máquina
* 6 - Verificar se tem pet no banho
* 7 - Colocar pet na máquina
* 8 - Retirar pet da máquina
* 9 - Limpar a máquina
* 0 - sair
 
* 🎯 Funcionalidades Implementadas
* ✔️ Sistema completo de banho para pets
* ✔️ Controle de estoque de água (capacidade 30L) e shampoo (capacidade 10L)
* ✔️ Validação de estado da máquina (limpa/suja)
* ✔️ Menu interativo com 9 operações
* ✔️ Verificação de pet presente na máquina
* ✔️ Controle de limpeza do pet e da máquina
* ✔️ Incremento controlado de água/shampoo (2L por operação)
* ✔️ Consumo padrão por banho (10L água e 2L shampoo)
 
* 📝 Exemplo de Uso
 
* ===Escolha uma das opções===
* 1 - Dar banho no pet
* ... Escolha uma opção: 7
 
* Informe o nome do pet: Rex
* O pet Rex foi colocado na máquina
 
* Escolha uma opção: 1
* O pet Rex está limpo
 
* Escolha uma opção: 8
* O pet Rex foi tirado da máquina
 
* ⚠️ Regras Importantes
* Só é possível colocar pet na máquina se ela estiver limpa
* Não é possível ter mais de um pet na máquina simultaneamente
* A máquina só pode ser limpa após retirar o pet
* Cada banho consome 10L de água e 2L de shampoo
* O abastecimento é feito em incrementos de 2L

````mermaid
classDiagram
    class Main {
        -scanner: Scanner
        -petMachine: PetMachine
        +main(String[] args)
    }

    class Pet {
        -name: String
        -clean: boolean
        +Pet(String name)
        +getName(): String
        +isClean(): boolean
        +setClean(boolean clean)
    }

    class PetMachine {
        -clean: boolean
        -water: int
        -shampoo: int
        -pet: Pet
        +takeAShower()
        +addWater()
        +addShampoo()
        +getWater(): int
        +getShampoo(): int
        +hasPet(): boolean
        +setPet(Pet pet)
        +removePet()
        +wash()
    }

    Main --> PetMachine
    PetMachine --> Pet : Contém
````

* 🔄 Fluxograma Básico
 
* [Início]
* ↓
* [Máquina criada: limpa, 30L água, 10L shampoo, sem pet]
* ↓
* [Menu de opções]
* ↓
* ├─ Dar banho → Verifica pet/estoque → Executa banho
* ├─ Abastecer água → Verifica capacidade → Adiciona 2L
* ├─ Abastecer shampoo → Verifica capacidade → Adiciona 2L
* ├─ Colocar pet → Verifica limpeza → Adiciona pet
* ├─ Retirar pet → Atualiza estado → Remove pet
* ├─ Limpar → Verifica sem pet → Limpa máquina
* └─ Sair → Encerra programa
 
* 📌 Observações
* Todas as operações exigem interação via terminal
* O sistema mantém histórico do estado entre operações
* As capacidades máximas são fixas (30L água e 10L shampoo)
* A máquina fica suja após retirar um pet não lavado