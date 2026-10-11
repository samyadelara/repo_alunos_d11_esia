# Registro individual — AV1.4

**Limite: uma página.** Estudante: Samya de Lara Pinheiro — Data: 10/10/2026  
**Critério de aceite por R2:** A listagem de chamados deve retornar todos os casos com estado "aberto" e "em_andamento", nenhum caso com estado "fechado", e os chamados listados deve estar na mesma posição relativa que na entrada.

| Entrada | IDs esperados por R2 | IDs do candidato | Status: inferido/observado | Mecanismo/trecho essencial |
|---|---|---|---|---|
| TR-41, TR-42, TR-43, TR-44 | TR-41,  TR-42, TR-44 | TR-42, TR-44, TR-41 | Inferido por leitura | `return sorted(ativos, key=lambda c: c["impacto"] + c["urgencia"], reverse=True)` Esta linha utiliza a função `sorted` para ordenar de forma decrescente (`reverse=True`) baseado no cálculo da soma de `impacto` e `urgencia`. O contrato define que a listagem deve estar ordenada de acordo com a posição relativa dos chamados na entrada. |

**Teste entregue — o que verifica e o que não consegue distinguir:** Por leitura, o candidato passaria na asserção. O teste verifica que o chamado de estado "fechado" não é trazido na listagem. A ordem resultante coincide com a ordem esperada porque a entrada do teste (TR-42, TR-44, TR-41) já está em ordem decrescente de escore (6, 4, 2). Assim, o teste não distingue preservar pela ordem relativa de entrada ou pela ordem do escore, pois tanto uma função correta quanto o candidato retornariam [TR-42, TR-44, TR-41].
**Trecho do teste (entrada e comparação de IDs) que sustenta minha análise:** entrada (TR-42, TR-44, TR-41, TR-43) e asserção (== ["TR-42", "TR-44", "TR-41"])
**Decisão (aceitar, aceitar com condições ou rejeitar) e motivo:** rejeitar - o candidato não cumpre R2, pois reordena a lista de chamados com base no escore e não na ordem relativa original de entrada, conforme tabela. O teste não é evidência para aceite, pois não detecta esse erro.
**Comparação entre manter e ajustar / responsável pelo aceite:** Manter implica em descumprimento de R2. Portanto exige que a regra seja alterada e aprovada com o gestor do produto. Ajustar o código (remover a ordenação por escore e trocar o teste) é relativamente simples e o aceite fica com o revisor depois de conferir o ajuste contra R2 e o novo teste.
**Ajuste proposto (texto ou código):** `def listar_ativos_proposta(chamados):
    ativos = [c for c in chamados if c["estado"] in ("aberto", "em_andamento")]
    return ativos `

| Caso para conferir o ajuste: entrada e ordem | IDs esperados | Resultado previsto ou observado / status |
|---|---|---|
| TR-41, TR-42, TR-43, TR-44 | TR-41, TR-42, TR-44 | TR-41, TR-42, TR-44 / previsto por leitura - candidato original retornaria TR-42, TR-44, TR-41 e falharia.|

**Limite remanescente e condição para rever o parecer:** Inferência por leitura, sem execução. Ausência de teste de limites de classes, casos como lista vazia, lista com todos os casos com estado fechado, lista com escores empatados. O parecer deve ser revisto se a regra for alterada pelo PO.
**Origem dos dados e da análise:** candidato/teste/entrada simulados; método próprio: inspeção / execução; comando e trecho de saída, se executado: não realizado.
**Uso de IA neste registro:** não utilizada / ferramenta-modelo: Claude (Opus 5.5); tarefa/contexto: evisão e correção de redação dos meus rascunhos, a partir do enunciado e do contrato; trecho aproveitado e minha verificação: ajustes de redação.

**Revisão:** [X] comparação com R2; [X] alcance do teste; [X] ajuste/revalidação; [X] status; [X] uma página.
