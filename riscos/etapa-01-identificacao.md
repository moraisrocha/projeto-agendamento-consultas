Com base no contexto apresentado, utilizei a LLM do Gemini para apoiar a identificação de riscos associados ao projeto.

```text
Entregável esperado
● lista de riscos identificados;
● descrição breve de cada risco;
● contexto em que podem ocorrer.
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
