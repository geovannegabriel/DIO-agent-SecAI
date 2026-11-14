# DIO Agent — Especialista em Análise de Vulnerabilidades

Projeto desenvolvido como parte de um desafio da [DIO](https://www.dio.me), com o objetivo de evoluir o DIO Agent por meio da criação de uma especialização voltada à segurança da informação.

A proposta é transformar o agente em um mentor de **Application Security (AppSec)**, capaz de auxiliar na identificação, análise e correção de vulnerabilidades, utilizando instruções, conhecimentos e procedimentos definidos em arquivos Markdown.

## Objetivo

Especializar o DIO Agent para conduzir análises de segurança de maneira estruturada, evitando respostas precipitadas e incentivando a compreensão dos riscos envolvidos.

A especialização busca fazer com que o agente:

- Entenda o contexto antes de recomendar ações.
- Identifique vulnerabilidades e suas possíveis causas.
- Explique os riscos técnicos envolvidos.
- Avalie impacto e probabilidade de exploração.
- Classifique a severidade das vulnerabilidades.
- Recomende medidas de correção.
- Oriente a validação das correções implementadas.

## Especialização desenvolvida

A especialização escolhida foi **Análise de Vulnerabilidades**, com foco inicial em segurança de aplicações.

O objetivo é aproximar o comportamento do agente ao processo de análise utilizado por profissionais de segurança, considerando não apenas a identificação de uma falha, mas também seu contexto, impacto e tratamento.

### Estrutura do projeto

```text
dio-agent/
│
├── AGENTS.md
│
├── agent/
│   ├── persona.md
│   └── knowledge/
│       └── security-basics.md
│
└── skills/
    └── vulnerability-analysis/
        ├── SKILL.md
        └── README.md
```

### Arquivos criados e modificados

| Arquivo | Finalidade |
|---|---|
| `skills/vulnerability-analysis/SKILL.md` | Define o procedimento que o agente deve seguir durante uma análise de vulnerabilidade. |
| `skills/vulnerability-analysis/README.md` | Documenta a finalidade, o funcionamento e a utilização da nova skill. |
| `agent/knowledge/security-basics.md` | Reúne conceitos fundamentais de segurança da informação e boas práticas. |
| `agent/persona.md` | Acrescenta orientações para o comportamento do agente como mentor de segurança. |
| `AGENTS.md` | Registra a nova skill e define em quais situações ela deve ser utilizada. |

## Processo de análise de vulnerabilidades

A skill foi planejada para orientar o agente por um processo estruturado:

1. **Contextualização:** compreender a aplicação, infraestrutura, ambiente e autorização para os testes.
2. **Identificação:** analisar possíveis vulnerabilidades e evidências técnicas.
3. **Avaliação de risco:** considerar impacto, probabilidade e severidade.
4. **Referências técnicas:** relacionar a vulnerabilidade a classificações e referências relevantes, como OWASP e MITRE ATT&CK, quando aplicável.
5. **Recomendação:** apresentar medidas de correção e prevenção.
6. **Validação:** verificar se a correção mitigou efetivamente a vulnerabilidade.

O agente também deve solicitar informações adicionais quando o contexto for insuficiente, evitando recomendar comandos ou testes sem compreender o ambiente e o escopo autorizado.

## Conhecimentos incorporados

O arquivo `security-basics.md` reúne conceitos utilizados como referência durante as análises:

- Vulnerabilidade, ameaça e risco.
- Confidencialidade, integridade e disponibilidade (tríade CIA).
- Avaliação de impacto e probabilidade.
- Classificação de severidade.
- Princípio do menor privilégio.
- Segurança por padrão.
- Boas práticas de desenvolvimento seguro.

## Cenários de validação

Para avaliar a especialização, foram definidos cenários de laboratório:

### 1. SQL Injection

Análise de uma aplicação Python que utiliza SQLite e constrói consultas SQL por meio da concatenação direta de entradas fornecidas pelo usuário.

O objetivo é identificar a vulnerabilidade, compreender como ela ocorre e orientar a utilização de consultas parametrizadas.

### 2. Validação após correção

Análise da mesma aplicação após a implementação de consultas parametrizadas, verificando se a vulnerabilidade foi mitigada.

### 3. Segurança de infraestrutura

Avaliação de um cenário hipotético envolvendo um servidor Ubuntu exposto à internet.

O objetivo é verificar se o agente solicita informações sobre o ambiente, exposição, finalidade e autorização antes de recomendar procedimentos de análise.

Todos os testes práticos devem ser realizados exclusivamente em aplicações e ambientes próprios ou com autorização explícita.

## Ambiente de desenvolvimento

O projeto utiliza o repositório original do [DIO Agent](https://github.com/digitalinnovationone/dio-agent).

Como ambiente de desenvolvimento e execução, foi utilizado o **Google Antigravity**, mantendo os arquivos e instruções do projeto como base para a especialização.

Não foi necessário treinar um modelo de inteligência artificial. A evolução do comportamento ocorre por meio das instruções, da persona, da base de conhecimento e da skill adicionada.

### Como executar

1. Clone o repositório:

```bash
git clone https://github.com/SEU_USUARIO/dio-agent.git
```

2. Abra a pasta do projeto no Google Antigravity.

3. Utilize um harness compatível com as instruções do projeto e abra o agente na pasta raiz, onde está localizado o `AGENTS.md`.

4. Inicie uma conversa e solicite uma análise de vulnerabilidade.

Exemplo de solicitação:

```text
Atue como especialista em AppSec.

Analise a aplicação Python apresentada,
identifique possíveis vulnerabilidades,
explique os riscos envolvidos e recomende
uma correção segura.

Antes de sugerir qualquer teste,
verifique o contexto e o escopo autorizado.
```

## Aprendizados

O desenvolvimento deste projeto permitiu explorar a especialização de agentes de IA por meio de arquivos de instrução, compreender a organização de skills e aplicar conceitos de segurança da informação em um fluxo de análise orientado.

Um dos principais aprendizados foi perceber que a utilidade de um agente não depende apenas do modelo utilizado, mas também da qualidade das instruções, dos conhecimentos disponíveis e do processo definido para orientar suas respostas.

## Referências

- [DIO Agent — Repositório original](https://github.com/digitalinnovationone/dio-agent)
- [OWASP — Open Worldwide Application Security Project](https://owasp.org/)
- [MITRE ATT&CK](https://attack.mitre.org/)
- [OWASP SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection)
- [Python — SQLite3](https://docs.python.org/3/library/sqlite3.html)

---

**Projeto desenvolvido para fins educacionais, com foco em aprendizado, análise defensiva e práticas de segurança em ambientes autorizados.**
