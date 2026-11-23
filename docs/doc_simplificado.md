# Requisitos do Projeto

## Requisitos gerais

- **Interface:** CLI ou API.
- **Justificativa de POO:** explicar por que um design orientado a objetos é necessário.
- **Fluxo:** não pode ser um fluxo linear único.

---

## Classes

- **Quantidade:** 12 classes, distribuídas em 8 domínios.
- **Responsabilidade:** cada classe deve ter uma responsabilidade claramente definida.
- **Métodos e encapsulamento:** devem ser coerentes entre si.
- **Justificativa textual:** a proposta deve incluir uma explicação escrita da modelagem, não apenas a lista de classes.

---

## Encapsulamento

- Usar `@property` quando fizer sentido e para validação de dados.

---

## Hierarquia

- **Classe abstrata:** uma classe abstrata com pelo menos uma subclasse especializada, com comportamentos diferentes.
- **Variação de comportamento:** uma hierarquia que varie de comportamento por meio de polimorfismo.

---

## Herança múltipla

- Pelo menos um uso (por exemplo, com **Mixins**).

---

## Polimorfismo

- Deve existir e depender de abstrações. O professor informou que o tema será dado em aula.

---

## Relações

- **Composições:** 2, com ciclo de vida independente entre as partes.
- **Agregações:** 2, com independência entre os objetos (por exemplo, os locais e os endereços).

---

## Modularização e arquitetura

- **Camadas:** podem ser domínio / aplicação / infraestrutura, modelos / serviços / interfaces, ou outra organização justificada pela equipe.
- **Regra de dependência:** camadas inferiores não podem depender das superiores.

---

## Princípios SOLID

O projeto deve aplicar os cinco princípios:

- **SRP:** Single Responsibility Principle (Responsabilidade Única)
- **OCP:** Open/Closed Principle (Aberto/Fechado)
- **LSP:** Liskov Substitution Principle (Substituição de Liskov)
- **ISP:** Interface Segregation Principle (Segregação de Interfaces)
- **DIP:** Dependency Inversion Principle (Inversão de Dependência)

Material de referência: https://colab.research.google.com/drive/1xkozxpFJVzV-k25SBE3Cf0dx1YGmWWHE

---

## Padrões de projeto

- **Quantidade:** pelo menos dois padrões.
- **Opções:** Factory / Abstract Factory, Strategy, Template Method, Observer, State ou Decorator.
- **Critério:** os padrões devem resolver um problema real do sistema, não ser usados de forma decorativa.

Referência: https://refactoring.guru/pt-br/design-patterns

---

## Código

- Seguir a PEP 8.

Referência: https://pythonacademy.com.br/blog/o-guia-de-estilos-pep8-do-python

---

## Primeira entrega: Proposta (24/11/2026)

O documento pode ser entregue em .docx ou Google Docs e deve conter:

- Nome da equipe
- Nomes dos integrantes, com o respectivo username no GitHub
- Descrição detalhada do domínio
- Justificativa da complexidade do sistema
- Diagrama UML com classes e relações
- Hierarquias previstas

Propostas superficiais serão devolvidas para revisão.
