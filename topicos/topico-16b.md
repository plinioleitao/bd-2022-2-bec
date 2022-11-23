## [Tópico T16b] - Álgebra Relacional - Exercícios
###### *by Prof. Plinio Sa Leitao-Junior (INF/UFG)*

Para apoiar os exercícios e exemplo sobre as operações da Álgebra Relacional, considere a ilustração abaixo do **BD Empresa**.

<img src="../media/fig-mr-2.jpg" width="450">

Escreva em álgebra relacional as seguintes consultas:

1. Qual o nome dos projetos que o funcionário "João B Silva" trabalha em?<br>
1. Qual o nome das pessoas que trabalham em pelo menos um dos projetos que o funcionário "João B Silva" trabalha em?<br>
ρ CPF_JOAO ( π Cpf (σ <sub>Pnome="João" AND Minicial="B" AND Unome="Silva"</sub> (FUNCIONARIO) ) )<br>
ρ PROJ_JOAO (π Pnr (TRABALHA_EM &#8904; <sub>Fcpf=Cpf</sub> CPF_JOAO) )<br>
ρ GOLF_CPF (Cpf)( (π Fcpf (PROJ_JOAO * TRABALHA_EM) ) - CPF_JOAO )<br>
π <sub>Pnome, Minicial, Unome</sub> ( GOLF_CPF * FUNCIONARIO )

3. Qual o nome das pessoas que não trabalham em qualquer dos projetos que o funcionário "João B Silva" trabalha em? Pessoas que não trabalham em qualquer projeto ESTÃO INCLUÍDAS no resultado da consulta.<br>
4. Qual o nome das pessoas em que todos os projetos que trabalham em estão entre os projetos que o funcionário "João B Silva" trabalha em? Pessoas que não trabalham em qualquer projeto NÃO ESTÃO INCLUÍDAS no resultado da consulta.<br>

IMPORTANTE: Use a sintaxe da Álgebra Relacional conforme os exemplos apresentados até então.