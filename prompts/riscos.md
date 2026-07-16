Com base no contexto apresentado, utilizei a LLM do Gemini para apoiar a identificação de riscos associados ao projeto.

# Prompt - identificacao

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

# Prompt - analise

Persona: Você atua como um analista de riscos em projetos de software, com experiência na análise qualitativa de riscos e aplicação de matrizes de probabilidade e impacto.

Tarefa: Realizar uma análise estruturada dos riscos previamente identificados, descrevendo seus impactos e fatores associados, e posteriormente organizá-los em uma matriz qualitativa de probabilidade vs. impacto, para apoiar a compreensão dos riscos.

Contexto: Considere que:
● Os riscos já foram previamente identificados;
● O projeto está em contexto de desenvolvimento de software;
● As informações disponíveis podem variar em nível de detalhe.

Saída:
Apresente o resultado em formato estruturado, conforme o modelo abaixo:

1. Análise estruturada dos riscos

Para cada risco:
+ Risco: nome ou descrição breve;
+ Descrição: detalhamento do risco;
+ Possíveis impactos no projeto: impactos potenciais em prazo, esforço, qualidade ou coordenação;
+ Fatores que influenciam a ocorrência: condições, dependências ou características do projeto que aumentam ou reduzem a probabilidade de ocorrência
+ Probabilidade (qualitativa): Baixa / Média / Alta
+ Impacto (qualitativo): Baixo / Médio / Alto
+ Justificativa da classificação

2. Matriz Qualitativa de Riscos

| Probabilidade\Impacto | Baixo | Médio | Alto |
| ----------------------- | ----- | ----- | ---- |
| **Alta** | | | |
| **Média** | | | |
| **Baixa** | | | |

Restrições e diretrizes:
● Não atribuir valores numéricos de probabilidade ou impacto.
● Indicar incertezas quando necessário.

# Prompt - respostas

Persona: Você atua como um gerente de projetos com experiência em resposta a riscos, com conhecimento em estratégias clássicas de tratamento de riscos em projetos de software, como evitar, mitigar, transferir e aceitar riscos, considerando diferentes contextos e níveis de incerteza.

Tarefa: Sugerir possíveis estratégias de resposta para os riscos previamente identificados e analisados, explorando alternativas viáveis e suas implicações, sem realizar uma escolha definitiva.

Contexto: Considere que:
● Os riscos já foram identificados e analisados previamente.
● O projeto está em contexto de desenvolvimento de software.
● As informações disponíveis podem variar em nível de detalhe.
● A análise servirá como apoio à tomada de decisão posterior.

Saída:
Apresente o resultado em formato estruturado, conforme o modelo abaixo:

1. Estratégias Possíveis por Risco
Para cada risco:
○ Risco: nome ou descrição breve.
○ Descrição: detalhamento do risco.
○ Estratégias de resposta possíveis:

i. Evitar: descrição de como essa abordagem poderia ser aplicada ao risco;
ii. Mitigar: descrição de como reduzir a probabilidade ou impacto;
iii. Transferir: descrição de como o risco poderia ser compartilhado ou transferido;
iv. Aceitar: descrição de quando e por que essa abordagem pode ser considerada.

2. Considerações sobre aplicação das estratégias
○ Situações em que cada tipo de estratégia tende a ser mais adequada.
○ Limitações ou trade-offs associados a cada abordagem.

3. Observações gerais
○ Dependência de contexto adicional para tomada de decisão.
○ Pontos que exigem validação com stakeholders.

Restrições e diretrizes:
● Indicar claramente as limitações das sugestões apresentadas.
● Manter a análise em nível exploratório e qualitativo.
