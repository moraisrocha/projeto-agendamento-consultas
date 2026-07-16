# Relatório de Status do Projeto: Aplicativo de Agendamento de Consultas Médicas
<br>**Para:** Diretoria Executiva
<br>**De:** Gerência de Projetos
<br>**Status Atual:** Em Fase Intermediária (Atenção / Amarelo)
## 1. Contexto Geral e Progresso Atual
O desenvolvimento do nosso novo aplicativo móvel de agendamento de consultas médicas encontra-se em sua **fase intermediária**. O núcleo de cadastro de usuários e os módulos iniciais de gestão de agendas médicas foram concluídos com sucesso.
No entanto, entramos em um período de alta complexidade técnica e de evolução de requisitos. Embora a equipe de engenharia (composta por 4 desenvolvedores e 1 tester) esteja altamente engajada, o ritmo de entregas das últimas semanas foi severamente impactado por desafios de integração externa e ajustes de escopo solicitados pelas áreas de negócios.
## 2. Desafios Técnicos e Impactos no Negócio
Buscando total transparência com esta diretoria, detalhamos abaixo os três principais problemas que enfrentamos hoje e como eles afetam diretamente os nossos objetivos de negócio:
 * **Instabilidade Crítica na API de Prontuário Externo**
   * *O Problema:* O sistema parceiro de prontuário passou por atualizações unilaterais recentes e não possui documentação clara. Isso gerou quebras frequentes de conexão no nosso ambiente de desenvolvimento.
   * *Impacto no Negócio:* **Risco de paralisação do aplicativo.** Como a integração é uma funcionalidade vital, a instabilidade impede o lançamento do fluxo de agendamento completo e afeta a experiência básica de ponta a ponta que prometemos aos nossos pacientes.
 * **Gargalo Operacional na Garantia de Qualidade (QA)**
   * *O Problema:* Contamos com 1 tester para validar o código gerado por 4 desenvolvedores. Com o aumento da complexidade e regras de validação adicionadas recentemente, formou-se um gargalo físico na homologação.
   * *Impacto no Negócio:* **Atraso no cronograma e risco à reputação.** Forçar entregas sem a devida vazão de testes pode fazer com que o aplicativo chegue ao mercado com falhas operacionais básicas em dispositivos.
 * **Aumento de Escopo no Fluxo de Agendamento**
   * *O Problema:* Novas validações e regras de negócio complexas foram solicitadas pelos stakeholders para o fluxo de agendamento que já estava parcialmente codificado.
   * *Impacto no Negócio:* **Aumento de custo por retrabalho e fadiga da equipe.** Alterar regras em funcionalidades já construídas consome horas extras da equipe que deveriam estar focadas na finalização das demais telas.
## 3. Plano de Resposta: Riscos Monitorados e Ações em Andamento
Em vez de apenas registrar as dificuldades, nossa equipe de desenvolvimento e gestão estruturou um plano de contingência focado em ações de **Prevenção (Evitar)** e **Minimização (Mitigar)**.
### Plano de Ação Estruturado
| Código de Risco | Risco Identificado | Ação de Resposta em Andamento | Tipo de Estratégia |
|---|---|---|---|
| **RSC-01** | Falha ou interrupção na integração de prontuários | **Construção de uma Camada de Abstração (Wrapper/Gateway):** Isolamos as chamadas da API externa no código. Se o parceiro alterar a API novamente, ajustamos apenas essa camada sem quebrar o aplicativo. <br> **Desacoplamento Temporário (Fallback):** Caso a API se mostre inviável nas próximas semanas, o app salvará os agendamentos de forma local/independente para não travar o lançamento. | Mitigar / Evitar |
| **RSC-02** | Gargalo de QA e atraso de homologação | **Testes Unitários e Cruzados:** Desenvolvedores passaram a realizar testes unitários automatizados rigorosos antes de enviar o código. Implementamos o "teste cruzado", onde um desenvolvedor valida a funcionalidade do outro antes de passar para o tester único. | Mitigar |
| **RSC-03** | Retrabalho por evolução ativa de requisitos | **Processo de Controle de Mudança (CCB):** Instituímos que qualquer nova regra de negócio passará por análise de impacto em horas antes de ser aprovada.<br> **Congelamento de Escopo (Fase 2):** Solicitamos a postergação de validações não essenciais para uma atualização pós-lançamento. | Mitigar / Evitar |
| **RSC-04** | Fadiga do time e prazos subestimados | **Ajuste de Cronograma e Redução de Escopo:** Estamos reestimando as tarefas com base na velocidade real do time nas últimas 3 semanas, reduzindo o escopo do lançamento inicial (ex: postergando notificações acessórias) para manter o time saudável. | Mitigar / Evitar |
| **RSC-05** | Exposição indevida de dados de saúde (LGPD) | **Minimização de Dados (Evitar Armazenamento):** O aplicativo não salvará dados clínicos permanentemente no celular do usuário. Os dados serão apenas transitados e mascarados.<br> **Criptografia e Peer Review:** Adotamos criptografia de ponta a ponta e revisões de código focadas estritamente em segurança da informação. | Evitar / Mitigar |
## 4. Próximos Passos e Decisões Recomendadas
Para garantir o sucesso do projeto com o menor impacto financeiro e de prazo possível, estamos conduzindo os seguintes passos imediatos:
 1. **Reunião de Alinhamento Técnico com o Parceiro Externo:** Agendamos um comitê de crise com a equipe técnica do sistema de prontuário para obter o mapeamento atualizado dos endpoints da API.
 2. **Validação do Escopo do MVP (Produto Mínimo Viável):** Solicitamos o apoio desta diretoria para validar junto aos stakeholders de negócios o congelamento das regras de agendamento atuais, adiando novos pedidos para a versão 1.1 do aplicativo.
 3. **Apresentação do Cronograma Repactuado:** Na próxima semana, apresentaremos uma simulação de nova data de lançamento considerando dois cenários: um focado em escopo integral (com prazo estendido) e outro focado em escopo reduzido (mantendo a data original).
