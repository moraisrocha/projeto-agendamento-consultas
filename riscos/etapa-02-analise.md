### RSC-01: Incompatibilidade ou falha crítica na integração com o prontuário externo
 * **Risco:** Incompatibilidade ou falha crítica na integração com o prontuário externo.
 * **Descrição:** Instabilidade e quebras de comunicação com o sistema externo de prontuário causadas por alterações recentes do fornecedor e falta de documentação clara de API.
 * **Possíveis impactos no projeto:**
   * *Prazo:* Atraso severo na entrega final, dado que a integração é descrita como crítica para o projeto.
   * *Esforço:* Desvio massivo de esforço dos desenvolvedores para engenharia reversa e correções emergenciais.
   * *Qualidade:* Instabilidade geral no fluxo de dados de saúde e agendamentos.
 * **Fatores que influenciam a ocorrência:**
   * *Aumentam a probabilidade:* O fornecedor externo continuar realizando atualizações sem aviso; indisponibilidade de um canal de suporte técnico direto com o parceiro.
   * *Reduzem a probabilidade:* Obtenção imediata de documentação atualizada ou estabelecimento de um ambiente de homologação (sandbox) estável pelo parceiro.
 * **Probabilidade (qualitativa):** Alta
 * **Impacto (qualitativo):** Alto
 * **Justificativa da classificação:** A instabilidade e a falta de documentação já são uma realidade no projeto ("desafios que surgiram"). Sendo uma dependência externa e crítica para o funcionamento do app, qualquer falha impede a homologação e a entrega do sistema de agendamento.

### RSC-02: Atraso na entrega por desequilíbrio na capacidade de testes (Gargalo de QA)
 * **Risco:** Gargalo de qualidade devido à baixa capacidade de vazão para testes em relação ao ritmo de desenvolvimento.
 * **Descrição:** Sobrecarga do único tester da equipe (proporção desbalanceada de 4 desenvolvedores para 1 tester) para validar as regras novas e o fluxo existente.
 * **Possíveis impactos no projeto:**
   * *Prazo:* Acúmulo de entregas na fase de testes, impedindo a liberação de pacotes de software nas datas previstas.
   * *Qualidade:* Liberação de código com bugs para produção devido à pressa ou à incapacidade física de o único tester cobrir todos os cenários de teste (incluindo testes de regressão).
 * **Fatores que influenciam a ocorrência:**
   * *Aumentam a probabilidade:* O aumento na complexidade das regras de negócio demandar testes manuais exaustivos; ausência de automação de testes.
   * *Reduzem a probabilidade:* Desenvolvedores realizarem testes unitários e integrados robustos antes de enviar o código para o QA.
 * **Probabilidade (qualitativa):** Alta
 * **Impacto (qualitativo):** Médio
 * **Justificativa da classificação:** Com o aumento relatado da carga de trabalho e novas regras de negócio, a probabilidade de o único tester ficar sobrecarregado é altíssima. O impacto é médio porque, embora cause atrasos nas entregas de sprints e possa deixar passar bugs menores, não impede tecnicamente a arquitetura geral do sistema (diferente da falha de integração crítica).

### RSC-03: Desalinhamento de escopo e retrabalho por evolução ativa de requisitos
 * **Risco:** Alterações frequentes de requisitos e regras de negócio no fluxo de agendamento solicitadas pelos stakeholders.
 * **Descrição:** Mudanças em regras de validação no fluxo de agendamento que já se encontra parcialmente implementado na fase intermediária do projeto.
 * **Possíveis impactos no projeto:**
   * *Esforço:* Desperdício de horas de desenvolvimento em código que precisará ser reescrito ou descartado (retrabalho).
   * *Qualidade:* Introdução de bugs de regressão em partes do fluxo de agendamento que já estavam funcionando de forma estável.
 * **Fatores que influenciam a ocorrência:**
   * *Aumentam a probabilidade:* Falta de um processo formal de aprovação de mudanças (Change Control Board) ou de congelamento de escopo para a fase intermediária.
   * *Reduzem a probabilidade:* Alinhamento prévio rígido com stakeholders por meio de prototipação ou validação visual antes da codificação.
 * **Probabilidade (qualitativa):** Média
 * **Impacto (qualitativo):** Médio
 * **Justificativa da classificação:** A probabilidade é média porque os stakeholders já estão solicitando alterações de forma ativa. O impacto é classificado como médio porque, embora afete o fluxo principal (agendamento), as alterações estão focadas em validações e regras de negócio que, sob uma gestão de escopo adequada, podem ser priorizadas para fases posteriores sem inviabilizar o aplicativo inteiro.

### RSC-04: Fadiga da equipe e atraso acumulado por subestimação de prazos
 * **Risco:** Sobrecarga física/mental do time e atrasos acumulados devido a estimativas de esforço irreais ou desatualizadas.
 * **Descrição:** Dificuldade recorrente relatada pela equipe em cumprir os prazos inicialmente estimados frente ao aumento da carga de trabalho atual.
 * **Possíveis impactos no projeto:**
   * *Prazo:* Atraso contínuo e cumulativo ao longo de todo o cronograma restante do projeto.
   * *Coordenação:* Queda na previsibilidade de entregas, gerando frustração em stakeholders e desgaste no clima organizacional.
 * **Fatores que influenciam a ocorrência:**
   * *Aumentam a probabilidade:* Manutenção do cronograma original sem ajustes após a adição de novas regras de negócio solicitadas por stakeholders.
   * *Reduzem a probabilidade:* Repactuação imediata de prazos ou redução do escopo planejado para a entrega atual (MVP - Produto Mínimo Viável).
 * **Probabilidade (qualitativa):** Alta
 * **Impacto (qualitativo):** Médio
 * **Justificativa da classificação:** A equipe já declarou formalmente a dificuldade em cumprir os prazos estimados e o aumento na carga de trabalho, tornando a ocorrência do atraso de alta probabilidade. O impacto é médio porque atrasos de cronograma são gerenciáveis por meio de repactuação e alinhamento de expectativas com os stakeholders.

### RSC-05: Exposição indevida ou disponibilização equivocada de dados sensíveis de saúde (Prontuário/LGPD)
 * **Risco:** Exposição inadequada, acesso indevido ou vazamento de dados pessoais e de prontuários médicos dos pacientes.
 * **Descrição:** Falhas de segurança no tráfego, armazenamento ou exibição de informações médicas e dados pessoais, impulsionadas pela falta de documentação clara na API de prontuário externa e pela pressa no desenvolvimento.
 * **Possíveis impactos no projeto:**
   * *Qualidade:* Quebra grave de confiabilidade, segurança e integridade do sistema móvel.
   * *Esforço:* Necessidade de refatorações de segurança de emergência, alteração na arquitetura de autenticação e auditorias profundas de código.
   * *Impacto Regulatório/Legal:* Risco de sanções legais severas por não conformidade com leis de proteção de dados de saúde (como a LGPD no Brasil), além de potencial cancelamento do projeto.
 * **Fatores que influenciam a ocorrência:**
   * *Aumentam a probabilidade:* A instabilidade e a falta de documentação do sistema de prontuário externo forçarem os desenvolvedores a implementar soluções de contorno rápidas e menos seguras para cumprir prazos agressivos; ausência de testes específicos de segurança pelo único tester da equipe.
   * *Reduzem a probabilidade:* A equipe ter um meio de comunicação integrado (facilitando o alinhamento de segurança e revisões de código em tempo real); adoção de criptografia e mascaramento de dados de saúde.
 * **Probabilidade (qualitativa):** Média
 * **Impacto (qualitativo):** Alto
 * **Justificativa da classificação:** O impacto é classificado como alto por lidar diretamente com prontuários médicos (dados altamente sensíveis sob aspectos legais e éticos). A probabilidade é média devido ao cenário de instabilidade da integração externa e à sobrecarga do time, fatores propícios para falhas acidentais de segurança. No entanto, a comunicação integrada do time ajuda a mitigar a probabilidade ao facilitar o pareamento e o alinhamento técnico diário.

## Matriz Qualitativa de Riscos

| Probabilidade\Impacto | Baixo | Médio | Alto |
|---|---|---|---|
| **Alta** |  | **RSC-02** (Gargalo de QA) <br> **RSC-04** (Fadiga/Atrasos) | **RSC-01** (Integração Crítica) |
| **Média** |  | **RSC-03** (Mudança de Requisitos) | **RSC-05** (Exposição de Dados Sensíveis) |
| **Baixa** |  |  |  |
