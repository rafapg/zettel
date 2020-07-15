# Arquitetura Limpa para Software

2020-07-15 15-57

> tags:
> #desenvolvimento #arquitetura

> references:
> [Clean Architecture Blog Post - Robert C. Martin](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
---
A Arquitetura Limpa de Desenvolvimento de Software é um conjunto de regras que, quando seguidas, promovem uma maior portabilidade do código, redução de dependências de entidades externas, torna o código mais robusto e facilida a implementação e adoção de políticas de testes automatizados.
A proposta dessa arquitetura é que o código seja estruturado em camadas, onde cada camada mais externa só pode ter dependências dentro da mesma camada ou de camadas mais internas. O padrão de camadas mais comuns de ser adotado é:

- Enterprise Business Rules (também chamado de Entities)
- Use Case (também conhecido como Domain ou Command)
- Interface Adapters
- External Services and Resources (Frameworks e Libraries)

Com base neste formato de estruturação do código e o fato de cada camada depender somente de camadas internas, todo o código dos UseCases e Enterprise Business Rules concentrarão as lógicas de negócio do software e serão completamente portáveis, pois não tem dependência de bibliotecas, frameworks e sistemas externos.

## Camadas

### Enterprise Business Rules

São as regras de negócio mais abrangentes, que dizem respeito a diversas funcionalidades e devem, necessariamente, ter a mesma implementação em todos os lugares.

### Use Case

Cada Use Case é a implementação da regra de negócio de uma funcionalidade específica. Essa implementação pode depender de alguma regra do tipo Enterprise Business Rule, mas o restante da lógica deve ser todo implementado dentro dessa mesma camada. 

Para ter acesso a dados externos (como serviços, bancos de dados, etc..) são criados Gateways nessa camada. Os gateways são interfaces para implementações de adpters (da camada Interface Adapters) que são setados via Injeção de Dependência. Dessa forma não existe uma dependência direta para a implementação, mas sim uma dependência para uma interface que é definida dentro da própria camada Use Case

### Interface Adapters

Nesta camada estão as implementações concretas dos Gateways definidos nas camadas mais internas. O objetivo dessa camada é abstrair os detalhes de implementação das dependências externas (que são setadas via Injeção de Dependência), como o acesso à um recurso externo , o registro um banco de dados, as informações recebidas em um request. Os Adapters trafegam para as camadas internas sempre Data Transfer Objects bem definidos.

### External Services and Resources

Camada formada em maior parte pelas dependências externas, como bibliotecas, frameworks, ORMs e outras dependências. Nessa camada a maior parte do código escrito é usado apenas para fazer as adaptações necessárias para o propósito dos Adapters da camada seguinte.

## Considerações

O conceito de Arquitetura Limpa não nos obriga ter uma quantidade pré-estabelecida de camadas, sendo possível utilizar um número menor ou maior de camadas conforme a necessidade. De qualquer maneira, a divisão em 4 partes parece ser a mais empregada por desenvolvedores que adotam esse padrão de arquitetura.

---

Links:

>   - 