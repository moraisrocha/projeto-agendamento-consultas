Com base no contexto apresentado, utilizei a LLM do Gemini para apoiar a identificação de riscos associados ao projeto.

```text
Entregável esperado
+ lista de riscos identificados;
+ descrição breve de cada risco;
+ contexto em que podem ocorrer.
```
# Prompt

```text
Persona: Você atua como um especialista em gerenciamento de riscos em projetos de software, com experiência na identificação de riscos técnicos, organizacionais e de processo, especialmente em contextos de alta incerteza.

Tarefa: Identificar possíveis riscos associados ao projeto, com base nas informações fornecidas, considerando fatores que podem impactar o andamento, a qualidade ou os resultados do projeto.

Contexto: Considere que:
● Trata-se de um projeto de desenvolvimento de software;
● Os requisitos estão em evolução, podendo sofrer mudanças ao longo do tempo;
● A equipe é distribuída, podendo envolver desafios de comunicação e coordenação.

A análise deve se limitar às informações fornecidas e suas implicações diretas.

Resultado:
Apresente o resultado em uma arquivo de formato markdown denominado etapa-01-identificacao.md seguindo a estrutura conforme o modelo abaixo:

1. Lista de riscos identificados
Para cada risco:
○ Identificacao: numeracao unica para cada risco, iniciando com o prefixo RSC 
○ Risco: descrição clara e objetiva;
○ Descrição: explicação breve do risco;
○ Contexto de ocorrência: situação ou condição em que o risco pode se manifestar.

Restrições e diretrizes:
● Não assumir informações que não foram fornecidas explicitamente.
● Indicar claramente quando houver incerteza ou necessidade de validação.
● Evitar generalizações excessivas ou riscos genéricos.

```
## 1. Lista de riscos identificados

| Identificação | Risco | Descrição | Contexto de Ocorrência |
|---|---|---|---|
| **RSC-01** | **Incompatibilidade ou falha crítica na integração** | Falha na consolidação da integração com o prontuário externo (crítico para o projeto) devido a mudanças frequentes e falta de documentação da API. | Durante ciclos de desenvolvimento/testes das rotas de integração ou quando o fornecedor externo atualiza o sistema sem aviso prévio. |
| **RSC-02** | **Atraso na entrega por gargalo de QA** | Sobrecarga do único tester da equipe (proporção de 4 devs para 1 tester) diante do aumento de demanda e complexidade. | No final de cada ciclo de entrega, quando as demandas concluídas pelos desenvolvedores acumulam na fila de testes simultaneamente. |
| **RSC-03** | **Desalinhamento e retrabalho de escopo** | Alterações tardias e novas regras de negócio solicitadas por stakeholders no fluxo de agendamento que já estava parcialmente implementado. | Durante a implementação e homologação das novas validações e regras modificadas no fluxo de agendamento. |
| **RSC-04** | **Fadiga da equipe e atraso acumulado** | Esgotamento da equipe e perda de previsibilidade de prazos devido ao aumento relatado de carga de trabalho e subestimação das estimativas. | No planejamento e execução das entregas, caso as estimativas não sejam revisadas para refletir a capacidade real do time de 4 desenvolvedores. |
| **RSC-05** | **Ruídos de comunicação por distribuição do time** | Atraso na resolução de problemas complexos devido a desafios de coordenação em uma equipe geograficamente distribuída. | Durante a ocorrência de bugs críticos ou impedimentos de integração que exijam colaboração síncrona e rápida. |
