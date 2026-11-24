# CIRA
Central de Intercâmbio e Reutilização de Acervos

## Integrantes

| Apelido | Nome | E-mail | Matrícula |
| ------- | ---- | ------ | --------- |
| OliveiraViktor | Luan Viktor Oliveira Silva | oliveira.silva@aluno.ufca.edu.br | 2026002729 |
| TocaiaLd | Wesley Silva Alves | wesley.alves@aluno.ufca.edu.br | 2026002578 |
| Raimundo77733 | Raimundo Gilmar Pereira Damaceno Junior | raimundo.pereira@aluno.ufca.edu.br | 2026005954 |
| eliseucz | Eliseu Oliveira Ferreira | eliseu.ferreira@aluno.ufca.edu.br | 2026005990 |
| emanuelhilley | Emanuel Hilley Alves Oliveira | emanuel.hilley@aluno.ufca.edu.br | 2026006002 |

## Domínio

O CIRA (Central de Intercâmbio e Reutilização de Acervos) é um sistema destinado ao gerenciamento de livros e à realização de trocas entre usuários. Seu domínio envolve o cadastro de usuários, o gerenciamento de livros, o registro de avaliações, a organização de listas de desejos e o gerenciamento de pontos de troca.

A classe `Usuario` representa os participantes do sistema, armazenando informações como CPF, apelido, nome e nota de avaliação. Cada usuário pode possuir endereços, livros, listas de desejos, trocas e avaliações recebidas.

A classe `Livro` representa os livros pertencentes aos usuários. Cada livro possui um identificador, um dono, uma nota e uma coleção de avaliações. Também mantém o relacionamento com as trocas das quais participa.

A classe `ExemplarLivro` representa as informações bibliográficas de uma obra, incluindo título, subtítulo, sinopse, autor, edição, ano e local de publicação e idioma. Essa classe especializa `Livro`, acrescentando informações específicas do exemplar e suas avaliações.

O sistema possui três tipos de avaliação:

- `AvaliacaoUsuario`: registra avaliações de usuários, contendo CPF, nota e descrição.
- `AvaliacaoLivro`: registra avaliações de livros, contendo identificador, nota de desgaste e descrição.
- `AvaliacaoExemplar`: registra avaliações de exemplares, contendo identificador, nota e descrição.

A classe `ListaDesejo` permite que um usuário mantenha uma coleção de livros desejados. Cada item dessa lista é representado por `LivroDesejado`, que possui a data em que o livro foi adicionado à lista.

A classe `Endereco` armazena informações de localização, como estado, cidade, bairro, rua, número e complemento. Os endereços podem estar associados aos usuários e aos pontos de troca.

A classe `PontoTroca` representa os locais destinados à realização dos intercâmbios. Cada ponto possui identificador, nome, administrador responsável, endereço e uma coleção de trocas relacionadas.

A classe `Administrador` representa a administração dos pontos de troca, mantendo uma coleção dos pontos sob sua responsabilidade.

Por fim, a classe `Troca` representa uma operação de intercâmbio entre dois usuários, envolvendo dois livros, um ponto de troca e uma data. Também disponibiliza operações para realizar a troca, verificar se determinado usuário participa dela e identificar o outro participante.

## Complexidade do Sistema

O CIRA apresenta complexidade relacionada ao gerenciamento de diferentes entidades e seus relacionamentos, principalmente usuários, livros, avaliações, listas de desejos, pontos de troca e operações de intercâmbio.

**Gerenciamento de usuários:** o sistema permite representar usuários por meio de informações cadastrais, endereços, livros associados, listas de desejos, trocas e avaliações recebidas.

**Gerenciamento de livros e exemplares:** é necessário manter os dados dos livros e suas informações bibliográficas. A especialização `ExemplarLivro` permite representar informações adicionais sobre uma obra, enquanto a classe `Livro` mantém os dados relacionados ao proprietário e às trocas.

**Sistema de avaliações:** o modelo possui avaliações específicas para usuários, livros e exemplares. Cada tipo apresenta informações próprias, como notas e descrições, permitindo registrar diferentes aspectos relacionados aos elementos avaliados.

**Listas de desejos:** o sistema permite que os usuários mantenham listas de livros desejados. Cada lista possui uma coleção de registros `LivroDesejado`, que armazenam a data em que o desejo foi registrado.

**Gerenciamento dos pontos de troca:** os pontos possuem identificação, nome, endereço e administrador responsável. Também mantêm o relacionamento com as operações de troca realizadas em cada local.

**Coordenação das trocas:** cada troca relaciona dois usuários, dois livros, um ponto de troca e uma data. Isso permite registrar as informações necessárias para representar os intercâmbios realizados.

**Persistência dos dados:** o sistema possui uma estrutura de repositórios responsável pela criação, consulta, atualização e remoção de registros das diferentes entidades.

## Diagrama UML

![Diagrama UML do CIRA](./docs/cira.svg)

## Hierarquias Previstas

O diagrama UML apresenta duas hierarquias explícitas de herança.

**1. ExemplarLivro e Livro**

A classe `ExemplarLivro` especializa a classe `Livro`, herdando suas características e acrescentando informações específicas da obra.

Enquanto `Livro` representa o registro associado ao proprietário, à nota, às avaliações e às trocas, `ExemplarLivro` acrescenta atributos bibliográficos:

- título;
- subtítulo;
- sinopse;
- autor;
- edição;
- ano de publicação;
- local de publicação;
- idioma;
- nota de avaliação;
- avaliações do exemplar.

Essa especialização permite separar as informações gerais de um livro das informações bibliográficas específicas de sua edição ou exemplar.

**2. Repositórios especializados e Repositorio**

A classe `Repositorio` representa a estrutura base de persistência do sistema, contendo operações para criação das tabelas necessárias ao armazenamento dos dados.

As seguintes classes especializam essa estrutura:

- `RepositorioUsuario`: operações relacionadas a usuários e administradores.
- `RepositorioLivro`: operações relacionadas aos livros.
- `RepositorioPontoTroca`: operações relacionadas aos pontos de troca.
- `RepositorioTroca`: operações relacionadas às trocas.
- `RepositorioExemplares`: operações relacionadas aos exemplares.
- `RepositorioAvaliacao`: operações relacionadas às avaliações.

Essa hierarquia permite organizar as operações de persistência de acordo com as responsabilidades de cada conjunto de entidades.

## Padrões de Projeto

O diagrama apresenta a utilização do padrão **Repository (Repositório)**, utilizado para separar as operações de persistência das entidades e suas responsabilidades de domínio.

**Repository (Repositório)**

O padrão Repository é representado pela classe `Repositorio` e suas especializações.

A classe base `Repositorio` possui métodos responsáveis pela criação das tabelas utilizadas pelo sistema, enquanto suas classes derivadas implementam operações específicas para cada conjunto de dados.

Exemplos:

- `RepositorioUsuario`: disponibiliza métodos para criar, consultar, atualizar e excluir usuários, além de consultar administradores.
- `RepositorioLivro`: disponibiliza operações de gerenciamento dos livros.
- `RepositorioPontoTroca`: disponibiliza operações de gerenciamento dos pontos de troca.
- `RepositorioTroca`: disponibiliza operações para realizar e consultar trocas.
- `RepositorioExemplares`: disponibiliza operações de gerenciamento dos exemplares.
- `RepositorioAvaliacao`: disponibiliza operações para criar, consultar, atualizar e excluir avaliações.

Essa organização permite centralizar o acesso aos dados em componentes específicos, evitando que as entidades do domínio precisem implementar diretamente as operações de persistência.

## Princípios SOLID

A organização das classes apresentada no UML permite identificar algumas aplicações dos princípios SOLID na estrutura do CIRA.

**1. Single Responsibility Principle (SRP) — Princípio da Responsabilidade Única**

Cada classe possui uma responsabilidade específica dentro do sistema.

Por exemplo:

- `Usuario` representa os participantes e suas informações.
- `Livro` representa os livros associados aos usuários.
- `Troca` representa as operações de intercâmbio.
- `PontoTroca` representa os locais de realização das trocas.
- `AvaliacaoUsuario`, `AvaliacaoLivro` e `AvaliacaoExemplar` representam diferentes tipos de avaliação.
- As classes `Repositorio` e suas especializações concentram as operações de persistência.

Essa divisão permite organizar o sistema em componentes com responsabilidades distintas.

**2. Open/Closed Principle (OCP) — Princípio Aberto/Fechado**

A utilização de herança permite estender funcionalidades sem necessariamente modificar as classes existentes.

No CIRA, a classe `ExemplarLivro` especializa `Livro`, acrescentando informações bibliográficas e características específicas dos exemplares.

A hierarquia de repositórios também permite especializar a estrutura de persistência para diferentes entidades.

**3. Liskov Substitution Principle (LSP) — Princípio da Substituição de Liskov**

A classe `ExemplarLivro`, por herdar de `Livro`, deve preservar os comportamentos esperados da classe base.

Assim, um objeto `ExemplarLivro` deve poder ser utilizado em contextos que esperam um objeto `Livro`, sem comprometer o funcionamento do sistema.

O mesmo princípio deve ser respeitado pelas especializações de `Repositorio`, preservando os contratos definidos pela classe base.

**4. Interface Segregation Principle (ISP) — Princípio da Segregação de Interfaces**

O sistema apresenta repositórios especializados, cada um responsável por operações relacionadas a determinado conjunto de entidades.

Essa separação evita concentrar todas as operações de persistência em um único componente especializado, permitindo que cada repositório disponibilize métodos relacionados à sua responsabilidade.

**5. Dependency Inversion Principle (DIP) — Princípio da Inversão de Dependência**

A estrutura de repositórios apresenta uma classe base, `Repositorio`, da qual derivam implementações especializadas.

Essa organização estabelece uma estrutura de especialização para as operações de persistência. Entretanto, o diagrama não apresenta explicitamente interfaces ou injeção de dependências.

Portanto, a aplicação completa do princípio DIP dependeria de uma implementação em que os componentes de alto nível dependessem de abstrações de persistência, em vez de dependerem diretamente das implementações concretas.

A utilização dos princípios SOLID contribui para a organização das responsabilidades, a redução do acoplamento e a facilidade de manutenção e evolução do sistema.