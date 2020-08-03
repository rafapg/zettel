# Testes Unitários

2020-08-03 18-17
> tags: #testes #software #desenvolvimento #devops
>
> references:

---

Intuitivamente definimos Testes Unitários como a classe de teste que garante o funcionamento de uma unidade do software. Não existe um consenso sob a medida para o termo unidade de software, porém as definições mais comuns de unidade são Classe (ou Arquivo), Função (ou Método) e, em alguns casos ainda, Regra de Negócio em arquiteturas limpas (hexagonal, ports and adapter, clean architecture).

Não parece prudente utilizar testes unitários no nível de função isolada, pois com essa granularidade, qualquer alteração pequena no software vai refletir em uma necessidade de correção de um número massivo de casos de teste. Manter-se entre funções públicas ou regras de negócio parece fazer sentido para a maioria dos casos, uma vez que uma alteração de comportamento deveria, realmente, tornar os casos de teste dessas funções obsoleto.

---

Links:

> -
