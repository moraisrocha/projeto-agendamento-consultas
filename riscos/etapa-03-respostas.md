### RSC-01: Incompatibilidade ou falha crítica na integração com o prontuário externo
 * **Risco:** Incompatibilidade ou falha crítica na integração com o prontuário externo.
 * **Descrição:** Instabilidade e quebra de comunicação devido à falta de documentação clara de API e alterações recentes e unilaterais no sistema terceiro.
 * **Estratégias de resposta possíveis:**
   * **i. Evitar:** Desacoplar temporária ou permanentemente o aplicativo do sistema de prontuário externo. O agendamento passaria a operar em modo *stand-alone* (armazenando os dados localmente ou em base própria) até que o parceiro garanta estabilidade. Isso elimina o risco de paralisia, mas altera o escopo crítico.
   * **ii. Mitigar:** Desenvolver uma camada de abstração (um *wrapper* ou *gateway* de integração) no código do aplicativo para isolar as chamadas da API externa. Se a API mudar, apenas essa camada precisará ser ajustada, reduzindo o impacto no restante do app. Adicionalmente, estabelecer reuniões técnicas semanais com a equipe do sistema externo.
   * **iii. Transferir:** Estabelecer uma cláusula contratual ou um acordo de nível de serviço (SLA) rígido com o fornecedor do sistema de prontuário, imputando a eles a responsabilidade financeira ou operacional por indisponibilidades e falhas de comunicação causadas por alterações sem aviso.
   * **iv. Aceitar:** Aceitar o risco caso o parceiro de integração seja um monopólio ou um órgão regulador intransigente. O projeto continuará consumindo a API instável diretamente e a equipe tratará os erros de conexão no aplicativo de forma passiva, exibindo mensagens de indisponibilidade temporária ao usuário final.
### RSC-02: Atraso na entrega por desequilíbrio na capacidade de testes (Gargalo de QA)
 * **Risco:** Sobrecarga do único profissional de testes diante do fluxo de trabalho de 4 desenvolvedores.
 * **Descrição:** Desequilíbrio de capacidade que gera acúmulo de tarefas na fase de homologação e riscos à qualidade das entregas.
 * **Estratégias de resposta possíveis:**
   * **i. Evitar:** Alterar o fluxo de trabalho para que novas funcionalidades só sejam iniciadas pelos desenvolvedores se a fila de testes estiver vazia (adotando limites de Trabalho em Progresso - WIP). Isso força o time a focar em finalizar o que já foi feito, evitando o acúmulo de gargalos.
   * **ii. Mitigar:** Capacitar os 4 desenvolvedores para realizarem testes unitários rigorosos e testes de integração automatizados antes de enviar qualquer tarefa ao QA. Outra ação é o tester focar em criar roteiros e cenários para que os próprios desenvolvedores façam testes cruzados (um dev testa o código do outro).
   * **iii. Transferir:** Contratar uma consultoria externa de QA ou alocar um profissional terceirizado (terceirização pontual ou *staff augmentation*) para absorver a sobrecarga de testes de regressão e validações manuais na fase intermediária/final.
   * **iv. Aceitar:** Prosseguir com o arranjo atual (4 devs para 1 QA). Se o cronograma estourar ou bugs passarem para produção, a equipe lidará com as correções de forma reativa nos ciclos seguintes, assumindo que a velocidade de entrega é prioritária sobre a perfeição do software.
### RSC-03: Desalinhamento de escopo e retrabalho por evolução ativa de requisitos
 * **Risco:** Alterações frequentes de requisitos e regras de negócio no fluxo de agendamento por parte dos stakeholders.
 * **Descrição:** Mudanças tardias em regras que já estavam parcialmente implementadas, gerando retrabalho.
 * **Estratégias de resposta possíveis:**
   * **i. Evitar:** Congelar o escopo do fluxo de agendamento imediatamente. Nenhuma alteração solicitada pelos stakeholders será implementada nesta versão do aplicativo; todas as novas ideias de validação serão direcionadas para uma "Fase 2" (fase pós-lançamento).
   * **ii. Mitigar:** Implementar um processo formal de Gestão de Mudanças (ex: criação de um formulário simples de solicitação e comitê de aprovação). Cada mudança solicitada exigirá uma análise prévia de impacto em prazo e esforço, apresentada explicitamente aos stakeholders antes de ser aprovada.
   * **iii. Transferir:** Envolver uma liderança de negócios parceira (como o patrocinador do projeto) para assumir a copropriedade das especificações de requisitos, dividindo com os stakeholders demandantes a responsabilidade pelas consequências de prazos decorrentes das alterações solicitadas.
   * **iv. Aceitar:** Absorver as alterações de escopo à medida que surgirem, sob a premissa de que a satisfação do cliente final com o fluxo refinado é mais importante do que seguir o cronograma rígido. O cronograma será estendido de forma reativa.
### RSC-04: Fadiga da equipe e atraso acumulado por subestimação de prazos
 * **Risco:** Esgotamento da equipe e perda de previsibilidade devido ao aumento relatado da carga de trabalho.
 * **Descrição:** Dificuldade recorrente em cumprir estimativas sob pressão por novas regras e instabilidades.
 * **Estratégias de resposta possíveis:**
   * **i. Evitar:** Reduzir o escopo da entrega atual (cortar funcionalidades secundárias do aplicativo, como notificações customizadas ou relatórios) para adequar o volume de trabalho à capacidade real de entrega da equipe dentro do prazo restante.
   * **ii. Mitigar:** Realizar uma sessão de reestimativa de esforço com a equipe utilizando dados reais de velocidade das últimas semanas. Ajustar o cronograma publicamente para refletir prazos realistas e estabelecer limites rígidos de horas extras para evitar o esgotamento físico e mental.
   * **iii. Transferir:** Compartilhar o risco com a diretoria do projeto, buscando orçamento adicional para contratar desenvolvedores temporários (*freelancers* ou consultores terceirizados) para apoiar na codificação de módulos específicos.
   * **iv. Aceitar:** Manter o cronograma e o escopo inalterados, documentando o atraso iminente. A gestão monitora ativamente os indicadores de estresse da equipe e aceita que os prazos serão naturalmente estendidos, sem punições ou pressão adicional sobre o time técnico.
### RSC-05: Exposição indevida ou disponibilização equivocada de dados sensíveis e pessoais de saúde (Prontuário/LGPD)
 * **Risco:** Exposição inadequada ou vazamento de dados pessoais e de prontuários de pacientes.
 * **Descrição:** Vulnerabilidades de segurança decorrentes da pressa no desenvolvimento e da falta de documentação clara na integração do prontuário.
 * **Estratégias de resposta possíveis:**
   * **i. Evitar:** Não trafegar nem armazenar dados de prontuário médico dentro do aplicativo móvel. O app funcionaria estritamente para agendar data/hora e o prontuário seria acessado pelo médico exclusivamente no sistema externo original dele, eliminando a superfície de ataque no app.
   * **ii. Mitigar:** Adotar criptografia de ponta a ponta para os dados em trânsito, aplicar mascaramento de dados nas telas do app e realizar revisões de código focadas em segurança (*security peer review*). Além disso, o tester pode ser orientado a realizar testes básicos de vulnerabilidade (ex: injeção de SQL ou quebra de controle de acesso).
   * **iii. Transferir:** Contratar um seguro de responsabilidade civil para incidentes cibernéticos ou delegar toda a autenticação e armazenamento de dados de saúde para uma plataforma de nuvem em conformidade com padrões rígidos de saúde (ex: HIPAA/LGPD Compliant), transferindo a responsabilidade da infraestrutura de segurança para um grande provedor.
   * **iv. Aceitar:** Aceitar o nível atual de segurança oferecido pelas bibliotecas padrão utilizadas pelos desenvolvedores. Esta aceitação só deve ser considerada se uma avaliação legal interna concluir que as medidas básicas implementadas cumprem os requisitos mínimos exigidos pela legislação vigente e o apetite ao risco da organização for compatível.

