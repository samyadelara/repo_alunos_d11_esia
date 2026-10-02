# Registro individual — AV1.3

> **Como usar:** copie este modelo e substitua os espaços em branco pelas suas respostas. Consulte o [passo a passo da aula](README.md) e o [guia com exemplo de evidência](../README.md). Remova esta orientação da entrega; mantenha suas respostas e evidências em até uma página.

**Limite: uma página.** Estudante: Samya de Lara Pinheiro — Data: 01/10/2026 
**O que a listagem e a documentação precisam cumprir, conforme R2/R4:** Incluir todos os chamados com estado == 'aberto'; Incluir todos os chamados com estado == 'em_andamento'; Excluir todos os chamados com estado == 'fechado'. A posição de entrada não deve ser alterada.

| Caso / estado a verificar | Entrada (IDs e ordem) | IDs esperados na ordem | Obrigação de R2 e como verificar |
|---|---|---|---|
| 1 / aberto | [(TR-31, 1), (TR-33, 3)]| [TR-31, TR-33] | TR-31["estado"] == 'aberto' ou 'em_andamento'; TR-33["estado"] == 'aberto' ou 'em_andamento'|
| 2 / em_andamento | [(TR-31, 1), (TR-32, 2)]| [TR-31] | TR-31["estado"] == 'aberto' ou 'em_andamento'; TR-32["estado"] == 'fechado'|
| 3 / fechado | [(TR-32, 2)]| [] | TR-32["estado"] == 'fechado'|

**Entrada combinada TR-31, TR-32, TR-33 → IDs esperados:** [TR-31, TR-33]
**Como conferiria a ordem (compare a posição dos IDs na entrada e na saída esperada):** Avaliaria se TR-31 ocorreu/foi registrado antes de TR-33 na entrada.
**Documentação proposta (até três frases):** Ao usar a funcionalidade listar_ativos, são recuperados APENAS os chamados ativos disponíveis, incluindo todos os casos em que o estado seja 'aberto' ou 'em_andamento'. Nenhum chamado com estado 'fechado' é recuperado. A ordem de registro dos chamados é preservada, independente do tipo de estado.

**Etapa em que admitiria IA / tarefa que ela faria / pessoa responsável por conferir:** Solicitar à IA a geração de casos para revisão/verificação. Escrita da documentação a partir do contrato, e revisão feita feitas.
**O que essa pessoa deve verificar antes de aprovar:** Se todas as regras do contrato estão descritas e são cobertas nos casos e documentação proposta. A documentação também não deve propor novas regras.
**Alternativa sem IA e comparação:** Escrever os casos e documentar. A IA teria mais agilidade na criação dos casos e documentação.
**O que os casos não verificam e o que me faria rever a aprovação:** A garantia da ordem de registros não é varificada. Sugeriria para ia, contraexemplos para essa aprovação.

**Origem dos dados e como fiz a análise:** entrada fictícia do enunciado; esperado por contrato: inspeção de R2 e R4 no contrato aprovado; inspeção própria: sim; execução opcional (comando/resultado, se houver): não realizada.
**Uso de IA neste registro:** não utilizada.

**Revisão:** [X] três estados; [X] ordem; [X] texto; [X] aceite/limite; [X] uma página.
