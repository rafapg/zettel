# Complexidade e custo de testes automatizados

2020-08-03 18-02
> tags:
>
> references:
> [Martin Fowler, Test Pyramid](https://martinfowler.com/bliki/TestPyramid.html)

---

É simples perceber que quanto mais partes móveis possui um teste, mais complexo é para construí-lo e mais caro é para mantê-lo, uma vez que a quantidade de dependências é muito grande. Testes mais complexos também demoram mais tempo para serem executados.

A partir dessa observação é proposta a pirâmide dos testes automatizados, na qual a maior parte do de casos de teste produzidos está na base da pirâmide, onde testamos as partes menores do software e garantimos o seu funcionamento para diversas situações (geralmente os testes unitários) e a menor quantidade de casos de teste está nos no topo da pirâmeide (geralmente testes E2E), onde nos preocupamos em cobrir apenas os cenários mais críticos para o negócio (com casos de testes de sanidade, por exemplo).

---

Links:

> -
