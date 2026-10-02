# Registro individual — AV1.2

> **Como usar:** copie este modelo e substitua os espaços em branco pelas suas respostas. Consulte o [passo a passo da aula](README.md) e o [guia com exemplo de evidência](../README.md). Remova esta orientação da entrega; mantenha suas respostas e evidências em até uma página.

**Limite: uma página.** Estudante: Samya de Lara Pinheiro — Data: 01/10/2026 
**Critérios antes da análise:** como conferir a classificação por R1: (impacto=1, urgencia=1) == baixa / (impacto=1, urgencia=2) == baixa / (impacto=2, urgencia=1) == baixa / (impacto=2, urgencia=2) == media / (impacto=3, urgencia=1) == media / (impacto=1, urgencia=3) == media / (impacto=3, urgencia=2) == alta / (impacto=2, urgencia=3) == alta / (impacto=3, urgencia=3) == alta; o que seria necessário para sustentar uma afirmação sobre outras entradas ou repetições: Testar casos representativos de todo o escopo.

| Entrada de A (impacto, urgência) | Cálculo e esperado por R1 | Trecho da resposta A | Conclusão por inspeção |
|---|---|---|---|
| (2, 3) | 2 + 3 = 5 (esperado: 'alta') | "... Portanto, (impacto=2, urgencia=3) é media ..." | Resultado divergente |
| (3, 1) | 3 + 1 = 4 (esperado: 'media') | "... e (impacto=3, urgencia=1) é alta ..." | Resultado divergente |

**B — trecho analisado:** "... classifique impacto=2, urgencia=3’. As três saídas foram ‘alta’ ..."
**O que posso concluir sobre o par citado em B:** A resposta B reporta um comportamento esperado.
**Afirmação geral de B: o que falta para sustentá-la:** A afirmação de geral de B não foi baseada em um teste amplo de todos os critérios de aceite. Em B não se declarou avaliar casos de outros níveis de prioridade.
**Contraexemplo ou condição não coberta:** Não foram testados casos de prioridade baixa (exemplo ‘classifique impacto=1, urgencia=1’) ou média (exemplo ‘classifique impacto=2, urgencia=1’)

**Decisão A + motivo:** Rejeitar, pois resultados estão diferentes do esperado.
**Decisão B + motivo:** Aceitar parcialmente, a decisão B cobre apenas parte dos casos aprovados no contrato.
**Alternativa de verificação e condição que mudaria uma decisão:** Avaliaria a validade da resposta B com assistência da IA, solicitando contraexemplos caso existam. 

**Origem dos dados e como fiz a análise:** respostas didáticas simuladas; cálculos/inspeções próprios: realizados sem assistência; execução real: não realizada. Tokens/custo/latência/configuração: não informados.
**IA na produção do registro:** não utilizada

**Revisão:** [ ] critérios; [X] dois pares; [X] análise de B; [X] decisões/limites; [X] uma página.
