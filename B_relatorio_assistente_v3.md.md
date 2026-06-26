# A — Meta-Prompt v3: Pesquisa Estruturada para Service Blueprint AS-IS
## Processo: Requisição de Passaporte na Polícia Federal (Brasil)
### Versão 3.0 — Revisada após segunda auditoria externa (audit_v2)

---

## Registro de decisões: audit_v2 → v3

Esta tabela documenta as decisões tomadas para cada ponto levantado pela segunda auditoria. A decisão é de responsabilidade do autor; a verificação de execução cabe ao auditor. Não há afirmação de completude — auditoria independente permanece necessária.

### Falhas parcialmente resolvidas da v1 (gap residual após v2)

| # | Falha | Decisão v3 | Resumo |
|---|-------|-----------|--------|
| 5 | Bastidor — consultas externas sem profundidade operacional | **(a) Corrigida** | Adicionados: base normativa de cada consulta, critérios legais de bloqueio, periodicidade esperada, protocolo de fallback em falha de integração |
| 6 | Processamento biométrico na PF sem distinção de fases | **(a) Corrigida** | Distinguidas explicitamente: captura, validação técnica (qualidade), validação identitária e auditoria; adicionado procedimento de rejeição biométrica |
| 7 | Logística — pontos de transferência de custódia ausentes | **(a) Corrigida** | Incluídos: pontos de transferência, responsabilidade jurídica por etapa, protocolo de extravio |
| 8 | Integração sistêmica — apenas perguntas, sem estrutura mínima | **(a) Corrigida** | Adicionadas: tipologias de integração esperadas (API/batch/fila), evidências técnicas mínimas verificáveis, hipóteses marcadas como inferência |
| 9 | Tesouro/SIAFI — banco arrecadador e tempo de liquidação ausentes | **(a) Corrigida** | Incluídos: papel do banco arrecadador, tempo de liquidação por meio de pagamento, impacto de falha de compensação |
| 13 | LGPD sem controlador/operador, sem compartilhamento, sem segurança | **(a) Corrigida** | Adicionados: identificação do controlador e operador (art. 5º LGPD), hipóteses de compartilhamento, requisitos de segurança da informação |
| 14 | Normativos — atos específicos da PF ainda genéricos | **(a) Corrigida** | Adicionadas instruções de busca específica no DOU com termos e período; não presume quais portarias existem |
| 22 | Processo real vs prescrito — risco metodológico não tratado | **(a) Corrigida** + **(c) Em aberto** | Adicionada regra de convergência com três categorias de achado; brecha estrutural mantida como limitação declarada |

### Novas falhas introduzidas na v2

| # | Falha | Decisão v3 | Resumo |
|---|-------|-----------|--------|
| 25 | Registro de auditoria autorreferente — "nenhuma ignorada" não verificável | **(a) Corrigida** | Tabela mantida como registro de decisões, não como atestado de completude; validação independente declarada necessária |
| 26 | Sem critérios de aceitação / suficiência por eixo | **(a) Corrigida** | Adicionada seção "Critérios de suficiência e aceitação" com nível mínimo de evidência por eixo |
| 27 | Sem governança metodológica (quem valida, como resolver conflitos) | **(a) Corrigida** | Nova seção "Governança metodológica" com validador, resolução de conflitos e divergência normativa vs prática |
| 28 | Sem hierarquia de fontes (precedência não definida) | **(a) Corrigida** | Nova tabela de hierarquia de fontes com ordem de precedência e regra de desempate |
| 29 | Sobrecarga cognitiva — sem priorização de requisitos | **(a) Corrigida** | Cada requisito classificado como **[E]** Essencial ou **[C]** Complementar; executor pode entregar E antes de C |
| 30 | Ambiguidade no conceito de AS-IS — mistura qualitativa e normativa sem regra | **(a) Corrigida** | Adicionada seção "Regras de convergência de fontes para visão AS-IS" com três categorias de achado |
| 31 | Requisitos técnicos não verificáveis induzem inferências | **(a) Corrigida** | Perguntas técnicas sobre integração agora marcadas como hipóteses `[hipótese técnica]`; resultado esperado é investigar, não confirmar |

### Pontos ainda abertos após v2

| # | Ponto | Decisão v3 | Resumo |
|---|-------|-----------|--------|
| Aberto 1 | Bastidor estruturalmente dependente de fontes inacessíveis | **(a) Parcial** + **(c) Em aberto** | Adicionada estratégia alternativa: inferência controlada por triangulação de fontes secundárias; limitação declarada explicitamente |
| Aberto 2 | Ausência de modelo de controle interno (visão auditoria) | **(a) Corrigida** | Novo Eixo (f) adicionado: Controles Internos e Segregação de Funções |
| Aberto 3 | Exceções sistêmicas incompletas (contingência, fallback manual) | **(a) Corrigida** | Variantes de exceção sistêmica adicionadas no fluxo e no Eixo (b) |
| Aberto 4 | Granularidade mínima do blueprint não definida | **(a) Corrigida** | Nova seção "Granularidade mínima esperada por etapa" adicionada |
| Aberto 5 | Sem mecanismo de validação empírica | **(c) Em aberto** | Validação empírica exige acesso de campo (shadowing, entrevistas com servidores) — fora do escopo desta pesquisa documental; declarado como etapa futura necessária |

---

## 1. Governança metodológica (novo — Falha 27)

Esta seção define como o processo de pesquisa é governado internamente.

### 1.1 Responsabilidades

| Papel | Função |
|-------|--------|
| **Executor da pesquisa** | Coleta achados, classifica por eixo, cita fontes, aplica marcações de confiança |
| **Revisor do blueprint** | Verifica coerência entre eixos, identifica contradições, valida alinhamento com mapa de atores |
| **Validador externo** | Auditor independente do processo final — não pode ser o próprio executor |

> Nota: Em execução solo (sem equipe), os papéis de executor e revisor são acumulados — isso **não elimina** a necessidade de revisar cada eixo antes de sintetizar o blueprint. O validador externo permanece como etapa necessária, mesmo que posterior.

### 1.2 Resolução de conflitos entre fontes

Quando duas fontes confiáveis divergem sobre o mesmo fato:

1. Aplicar a **hierarquia de fontes** (seção 2) — a de maior nível prevalece
2. Se do mesmo nível: registrar ambas com marcação `[divergência de fontes — ver nota]` e descrever a divergência
3. Nunca eliminar silenciosamente a fonte minoritária

### 1.3 Divergência normativa vs prática observada

Quando uma fonte normativa contradiz uma fonte de prática observada (ex.: norma diz prazo de 6 dias; auditoria TCU registra média de 15 dias):

- **Registrar as duas versões separadamente** com suas fontes
- Usar a marcação: `[prescrito: X | observado: Y | fonte observado: Z]`
- Não escolher uma versão como "verdadeira" — o blueprint AS-IS deve conter as duas

---

## 2. Hierarquia de fontes (novo — Falha 28)

Ordem de precedência decrescente. Fonte de nível superior prevalece em caso de conflito com fonte de nível inferior.

| Nível | Tipo de fonte | Exemplos | Marcação |
|-------|--------------|----------|----------|
| 1 | Norma federal vigente | Lei, Decreto, Portaria publicada no DOU | `[N1-normativo]` |
| 2 | Relatório de órgão de controle | TCU, CGU, auditoria operacional | `[N2-controle]` |
| 3 | Documento oficial interno publicado | Contrato no Portal da Transparência, resposta LAI | `[N3-oficial]` |
| 4 | Fonte jornalística qualificada com dado concreto | Agência Brasil, Portal G1 com citação de autoridade | `[N4-imprensa]` |
| 5 | Pesquisa acadêmica com método declarado | Artigo, dissertação, TCC com pesquisa de campo | `[N5-academia]` |
| 6 | Relato qualitativo não controlado | Reclame Aqui, fóruns, relatos anônimos | `[N6-qualitativo]` |

> **Regra de desempate:** quando duas fontes do mesmo nível divergem, prevalece a mais recente. Se mesma data, registrar como divergência (seção 1.2).

> **Fontes N6** nunca sustentam afirmações factuais — servem apenas para levantar hipóteses de fail points a investigar em fontes de nível superior.

---

## 3. Critérios de suficiência e aceitação por eixo (novo — Falha 26)

Define quando a pesquisa de cada eixo pode ser encerrada.

| Eixo | Critério mínimo de suficiência | Nível mínimo de evidência |
|------|-------------------------------|--------------------------|
| (a) Jornada | Todas as etapas do caso principal + pelo menos 3 variantes documentadas com fonte N1–N4 | N1 ou N2 para cada etapa principal |
| (b) Bastidor | Cada ator do mapa RACI tem ao menos 1 atividade de bastidor descrita com fonte N1–N3 | N1–N3 para consultas a bases; N3–N5 para demais |
| (c) Evidências | Cada etapa da jornada tem coluna de evidência preenchida (inclusive com "ausente" quando não há) | N1–N4; N6 apenas para hipóteses |
| (d) Normativos | Todos os normativos da lista obrigatória pesquisados, com status (vigente / revogado / não encontrado) | N1 para cada normativo |
| (e) Fail points | Mínimo de 3 falhas por categoria, com pelo menos 1 com evidência N2 ou N3 | N2–N3 para ao menos 50% dos itens |
| (f) Controles | Cada etapa principal tem ao menos 1 controle identificado ou marcado como "controle não encontrado" | N1–N3 |

> Requisitos marcados **[E]** são essenciais — pesquisa incompleta sem eles. Requisitos marcados **[C]** são complementares — entregam mais qualidade mas não bloqueiam a síntese do blueprint.

---

## 4. Contexto e objetivo

Você é um analista de serviços públicos especializado em Service Design e mapeamento de processos. Sua tarefa é conduzir uma pesquisa estruturada que sirva de base empírica para a construção de um **Service Blueprint AS-IS** do processo de emissão de passaporte pela Polícia Federal do Brasil.

**O blueprint descreve o serviço como ele funciona hoje.** Há uma brecha reconhecida — e não eliminável nesta fase — entre o processo prescrito (normas) e o processo real (prática): veja a seção de limitações ao final.

**Atenção:** esta é uma pesquisa documental. Ela captura o processo **prescrito** com alta fidelidade e o processo **real** com fidelidade limitada às fontes disponíveis (relatórios de controle, LAI, pesquisa acadêmica). Validação empírica (shadowing, entrevistas com servidores) permanece como etapa futura necessária — ver Aberto 5.

---

## 5. Camadas do Service Blueprint e eixos de pesquisa

Modelo: Shostack (1982) e Bitner, Ostrom & Morgan (2008).

| Camada do Blueprint | Posição no diagrama | Eixo de pesquisa |
|---------------------|--------------------|-----------------------|
| Evidências físicas | Faixa transversal superior (permeia todas as colunas) | **(c)** |
| Ações do cidadão | Acima da linha de interação | **(a)** |
| Ações onstage (visíveis ao cidadão) | Entre linha de interação e linha de visibilidade | **(b)** — frente visível |
| Ações backstage (ocultas ao cidadão) | Abaixo da linha de visibilidade | **(b)** — retaguarda |
| Processos de suporte sistêmico | Abaixo da linha de interação interna | **(b)** — sistemas |
| Controles internos e segregação de funções | Anotações sobrepostas | **(f)** — novo eixo |
| Normativos | Rodapé / anotação | **(d)** |
| Fail points | Sobrepostos ao fluxo | **(e)** |

---

## 6. Regras de convergência de fontes para visão AS-IS (novo — Falha 30)

Todo achado deve ser classificado em uma das três categorias:

| Categoria | Definição | Marcação no arquivo |
|-----------|-----------|---------------------|
| **Prescrito** | Descrito em normativo ou documento oficial — como o processo "deve" funcionar | `[prescrito — N1]` |
| **Observado** | Descrito em relatório de controle, pesquisa de campo ou fonte N2–N5 — como o processo "funciona" | `[observado — N2]` |
| **Hipótese** | Inferido a partir de fonte N6 ou por analogia — não confirmado em fonte primária | `[hipótese — N6 — não confirmado]` |

O blueprint final deve indicar, para cada elemento, em qual categoria ele se enquadra. Não misturar prescrição com observação sem marcação explícita.

---

## 7. Insumos disponíveis

- **Fluxo ponta a ponta:** fornecido pelo usuário (abaixo)
- **Mapa de Atores (RACI):** `C_mapa_atores.md` — 13 atores

> **Uso do mapa de atores:** antes de usar, validar: (i) todos os atores do fluxo estão no mapa? (ii) papéis RACI são consistentes com normativos N1? (iii) há atores identificados na pesquisa que não constam no mapa? Registrar divergências em `C_mapa_atores.md` ou em nota de rodapé do blueprint.

### 7.1 Fluxo — Caso principal

| Etapa | Ator principal | Canal |
|-------|---------------|-------|
| 1. Solicitação digital — SINPA | Cidadão / Sistema PF | Digital |
| 2. Pagamento da GRU | Cidadão / Sistema financeiro | Digital |
| 3. Agendamento — Agenda Web | Cidadão / Sistema PF | Digital |
| 4. Atendimento presencial | Cidadão / Atendente PF | Presencial |
| 5. Processamento e produção | Casa da Moeda / Logística | Interno |
| 6. Retirada | Cidadão / Atendente PF | Presencial |

### 7.2 Variantes obrigatórias **[E]**

| Variante | Divergência do caso principal | Etapas afetadas |
|----------|------------------------------|----------------|
| Indeferimento | Encerra em etapa 4; gera notificação e prazo de recurso | 4 → saída |
| Reemissão (perda/roubo) | Exige BO; taxa diferenciada possível | 1–2 |
| Urgência / emergência | Prazo comprimido; possível dispensa de agendamento | 2–4 |
| Renovação (passaporte anterior válido) | Simplificações documentais | 1, 4 |
| Menor de idade | Autorização de responsáveis ou judicial | 1, 4 |
| Restrição judicial | Fluxo encerrado em qualquer etapa; comunicação ao juízo | Qualquer |

### 7.3 Exceções sistêmicas **[E]** (novo — Aberto 3)

| Exceção | Etapa afetada | Expectativa de fallback |
|---------|--------------|------------------------|
| Indisponibilidade do SINPA | 1 | Existe procedimento manual? Qual normativo o define? |
| Falha de compensação de pagamento | 2 | Como o cidadão é instruído? Quem aciona a reconciliação? |
| Agenda Web indisponível | 3 | Há agendamento por telefone? Por presencial direto? |
| Falha biométrica (baixa qualidade) | 4 | Quantas tentativas? Quem decide a rejeição? |
| Atraso na produção da Casa da Moeda | 5 | Há prazo máximo contratual? Como o cidadão é notificado? |
| Passaporte extraviado na logística | 5–6 | Qual o protocolo? Quem é responsável juridicamente? |

---

## 8. Eixo (a) — Jornada do Cidadão **[E]**

**Objetivo:** mapear cada ponto de contato do cidadão com o serviço, na sequência cronológica real.

**Perguntas essenciais [E]:**
- Quais passos o cidadão executa, em qual ordem e por qual canal?
- Qual é o tempo médio/esperado em cada etapa (com fonte N1–N4)?
- Em caso de indeferimento: como e quando o cidadão é notificado? Há prazo de recurso? (Normativo?)
- Como cada variante da seção 7.2 altera a jornada?

**Perguntas complementares [C]:**
- Quais decisões o cidadão precisa tomar (ex.: escolha de unidade, tipo de passaporte)?
- Há diferença de jornada entre capitais e cidades do interior?

**Fontes prioritárias:** portal gov.br/passaporte `[N1]`, FAQ oficial da PF `[N1–N2]`, tutoriais em vídeo oficiais `[N3]`.

---

## 9. Eixo (b) — Processos de Bastidor

**Objetivo:** identificar todas as atividades fora da vista do cidadão, em três subcamadas.

### 9.1 Frente visível — Atendente PF **[E]**

- Roteiro formal de conferência documental (existe checklist normativo?)
- Registro do deferimento ou indeferimento: em qual sistema? Qual o documento gerado?

**Processamento biométrico — fases distintas (Falha 6 corrigida) [E]:**

| Fase | Descrição esperada | Padrão aplicável |
|------|--------------------|-----------------|
| Captura | Coleta de foto e digitais | ICAO Doc 9303, Parte 9 |
| Validação técnica | Verificação de qualidade da imagem (resolução, iluminação) | Critérios ICAO |
| Validação identitária | Comparação com biometria anterior ou base de dados | Sistema interno PF |
| Auditoria | Revisão em casos de inconsistência | Procedimento interno |

> **Rejeição biométrica [E]:** quando a captura não atinge qualidade mínima, qual é o procedimento? Quantas tentativas são permitidas? Quem decide? Há normativo interno ou portaria específica?

### 9.2 Retaguarda — Consultas a bases externas (Falha 5 corrigida) **[E]**

Para cada consulta abaixo, pesquisar: (i) base normativa que autoriza a consulta, (ii) critério exato de bloqueio, (iii) periodicidade (em tempo real ou em lote?), (iv) protocolo de fallback se a base estiver indisponível.

| Base | Dado verificado | Base normativa esperada | Critério de bloqueio | Periodicidade | Fallback |
|------|----------------|------------------------|---------------------|--------------|---------|
| Receita Federal (CPF) | Regularidade do CPF | Instrução normativa RFB — pesquisar | CPF cancelado/suspenso | [verificar] | [verificar] |
| TSE | Regularidade eleitoral | Código Eleitoral / resolução TSE — pesquisar | Multas não quitadas | [verificar] | [verificar] |
| Serviço Militar | Quitação (homens até 45 anos) | Lei 4.375/1964 e atualizações — pesquisar | Sem certificado de dispensa | [verificar] | [verificar] |
| Poder Judiciário | Mandado de prisão / proibição saída | Código de Processo Penal / decisão judicial | Qualquer mandado ativo | Tempo real? | [verificar] |
| Base antifraude PF | Histórico de fraudes / inconsistências | Normativo interno — pesquisar via LAI | [verificar] | [verificar] | [verificar] |

> Colunas marcadas `[verificar]` são hipóteses `[hipótese técnica]` — o executor deve investigar, não presumir.

### 9.3 Integração sistêmica (Falha 8 corrigida) **[E/C]**

> ⚠️ As perguntas abaixo são **hipóteses de investigação** `[hipótese técnica]`. O executor não deve afirmar tipos de integração sem fonte — apenas investigar e registrar o que encontrar (ou registrar "não encontrado").

**[E] Investigar com evidência documental:**
- Existe integração entre SINPA e sistema de agendamento? (evidência: manual técnico, LAI, TCU)
- O pagamento compensado na GRU aciona automaticamente o agendamento? (evidência: normativo ou relatório de auditoria)
- Como a PF transmite o pedido para a Casa da Moeda? (evidência: contrato no Portal da Transparência)

**[C] Investigar se fonte disponível:**
- Tipos de integração: API REST, batch, fila de mensagens? `[hipótese técnica — confirmar via LAI ou TCU]`
- Gateway de pagamento PIX: integração com BCB? `[hipótese técnica — confirmar via normativo BCB ou contrato]`
- Integração com SINCRE ou sistema equivalente? `[hipótese técnica]`

### 9.4 Fluxo financeiro e conciliação — Tesouro Nacional / SIAFI (Falha 9 corrigida) **[E]**

**[E]** Pesquisar e descrever:
- Como a GRU é gerada: qual normativo define o código de receita do passaporte?
- Qual é o banco arrecadador? (verificar contrato ou portaria STN)
- Após compensação: qual o tempo de liquidação por meio de pagamento (PIX vs boleto vs cartão)?
- O reconhecimento do pagamento pelo sistema da PF é automático ou requer validação manual? (evidência: relatório TCU ou LAI)
- O que ocorre se a GRU compensar após o prazo de validade da solicitação?

**Fontes prioritárias:** normativos STN sobre GRU `[N1]`, contrato com banco arrecadador no Portal da Transparência `[N3]`, relatório TCU sobre arrecadação `[N2]`.

### 9.5 Produção e logística (Falha 7 corrigida) **[E]**

**Cadeia de custódia — pontos de transferência [E]:**

| Ponto | Transferência | Responsável cedente | Responsável receptor | Documento de transferência? |
|-------|-------------|--------------------|--------------------|---------------------------|
| 1 | Casa da Moeda → transportadora | Casa da Moeda | Transportadora | [verificar] |
| 2 | Transportadora → unidade PF | Transportadora | Chefe da unidade PF | [verificar] |
| 3 | Unidade PF → cidadão | Atendente PF | Cidadão | [verificar] |

**[E]** Pesquisar:
- Em caso de extravio: quem notifica o cidadão? Qual prazo? Qual normativo define responsabilidade?
- Existe seguro ou ressarcimento previsto para documento extraviado?
- O contrato logístico está publicado no Portal da Transparência? (pesquisar por CNPJ da transportadora ou objeto do contrato)

---

## 10. Eixo (c) — Evidências Físicas (camada transversal)

**Objetivo:** identificar artefatos por etapa. Etapas sem evidência para o cidadão devem ser registradas explicitamente como "sem evidência direta".

**Formato de saída:**

| Etapa | Evidência | Tipo | Visibilidade | Emitido por | Finalidade | Categoria (prescrito/observado/hipótese) |
|-------|-----------|------|--------------|-------------|------------|------------------------------------------|

**Evidências obrigatórias [E]:** protocolo de solicitação, GRU, comprovante de agendamento, checklist de documentos, registro de deferimento/indeferimento (interna + notificação ao cidadão), registro biométrico capturado (interna), notificações de status (SMS/e-mail — em quais etapas?), o passaporte.

**Evidências negativas [E]:** notificação de indeferimento (forma, prazo, conteúdo), GRU expirada, cancelamento por não retirada em 90 dias.

**Evidências complementares [C]:** código de rastreamento logístico, recibo de entrega no balcão, termo de retirada assinado pelo cidadão.

---

## 11. Eixo (d) — Normativos Aplicáveis **[E]**

**Formato de saída:**

| Normativo | Tipo | Ementa resumida | Etapa(s) regulada(s) | Status (vigente/revogado/não encontrado) | Fonte |
|-----------|------|----------------|---------------------|----------------------------------------|-------|

### Normativos obrigatórios [E]

**Passaporte — base primária:**
- **Decreto nº 5.978/2006** — Regulamento dos Passaportes Brasileiros *(verificar se vigente ou substituído)*
- **Portarias da PF sobre emissão:** buscar no DOU com termos `"passaporte" "Polícia Federal" "portaria"` — período 2015–2025; listar todas as encontradas
- **Atos normativos PF sobre prazos e comparecimento:** buscar com termos `"passaporte" "atendimento" "prazo" "portaria" site:in.gov.br`

**Documentação e identidade:**
- Lei nº 13.445/2017 — Lei de Migração *(uso e validade do passaporte em contexto migratório)*
- Lei nº 7.116/1983 — incluir apenas como **contexto periférico**, com nota: *"regula RG, não passaporte — relevante apenas para consistência de dados de identidade"*

**Padrões internacionais [E]:**
- **ICAO Doc 9303** — Partes 1, 3 e 9 *(documentos legíveis por máquina, biometria)*
- Verificar: a PF publica portaria de adesão ao padrão ICAO? (buscar no DOU)

**Pagamento e arrecadação [E]:**
- Normativo STN sobre Guia de Recolhimento da União (GRU) *(buscar: "GRU" "STN" "normativo" — identificar o instrumento vigente)*
- Portaria interministerial que define o valor da taxa de passaporte *(buscar por ano — verificar última atualização)*
- *(GRU é regulada pela STN/SIAFI, não apenas por IN da Receita)*

**Dados pessoais e biometria [E] (Falha 13 corrigida):**
- **Lei nº 13.709/2018 (LGPD)** — pesquisar e registrar obrigatoriamente:
  - Controlador: quem é? (PF? MJSP?) — art. 5º, VI
  - Operador: quem trata os dados em nome do controlador? (Casa da Moeda? Empresa de TI?) — art. 5º, VII
  - Base legal: obrigação legal (art. 7º, II) e/ou exercício regular de direito (art. 7º, VI)
  - Hipóteses de compartilhamento: com quais órgãos os dados biométricos são compartilhados? Base legal de cada compartilhamento?
  - Prazo de retenção: existe política publicada ou normativo que defina o prazo de guarda dos dados biométricos?
  - Segurança da informação: existe normativo ou contrato que defina requisitos de segurança para o tratamento dos dados?

**Controle e transparência:**
- Lei nº 12.527/2011 (LAI)
- Normas TCU e CGU sobre auditoria do serviço (buscar acórdãos TCU com "passaporte" e "Polícia Federal")

**Acessibilidade:**
- Lei nº 13.146/2015 (Lei Brasileira de Inclusão)

---

## 12. Eixo (e) — Fail Points Conhecidos **[E]**

**Formato de saída:**

| Fail Point | Etapa | Categoria | Impacto ao cidadão | Evidência de frequência (fonte ou `[inferência]`) | Fonte | Categoria achado |
|------------|-------|-----------|-------------------|--------------------------------------------------|-------|-----------------|

### Categorias obrigatórias [E]

**Técnicas:** indisponibilidade de sistemas; falha de integração entre sistemas.

**Operacionais:** documentação incompleta; inconsistência biométrica; prazo de produção estourado.

**Interoperabilidade de bases:** CPF irregular; divergência de dados cadastrais; irregularidade eleitoral.

**Jurídicas:** restrição judicial ativa; menor sem autorização.

**Financeiras:** GRU expirada; pagamento não reconhecido por falha de compensação.

**Logísticas:** atraso de entrega; extravio de documento.

**Comunicação:** cidadão não notificado sobre status ou indeferimento; informações divergentes entre canais.

**Capacidade:** falta de vagas para agendamento; demanda reprimida.

**Governança:** divergência de interpretação de requisitos entre unidades da PF.

**Fontes prioritárias:** acórdãos TCU com "passaporte" `[N2]`, relatórios CGU `[N2]`, ouvidoria PF (relatórios anuais publicados) `[N3]`, notícias com dados concretos `[N4]`.

> Fontes N6 (Reclame Aqui, fóruns) geram apenas hipóteses para investigar em N1–N4. Jamais sustentar frequência com N6.

---

## 13. Eixo (f) — Controles Internos e Segregação de Funções (novo — Aberto 2) **[E]**

**Objetivo:** mapear os controles internos formais e informais existentes em cada etapa do processo, na perspectiva de auditoria (COSO-like).

**Formato de saída:**

| Etapa | Controle identificado | Tipo de controle | Ator responsável | Base normativa | Evidência de efetividade | Fonte |
|-------|----------------------|-----------------|-----------------|---------------|------------------------|-------|

### Tipos de controle a identificar

| Tipo | Definição |
|------|-----------|
| **Preventivo** | Impede que o erro ou fraude ocorra (ex.: validação automática de CPF) |
| **Detectivo** | Identifica erro ou fraude após ocorrência (ex.: auditoria biométrica) |
| **Corretivo** | Corrige o efeito após detecção (ex.: reemissão de passaporte com defeito) |

### Segregação de funções **[E]**

Investigar e registrar:
- Quem solicita, quem aprova e quem executa são atores distintos em cada etapa? (princípio de segregação)
- Um único atendente da PF pode: (i) conferir documentos, (ii) coletar biometria E (iii) deferir o pedido? Se sim, há controle compensatório?
- A Casa da Moeda tem acesso aos dados de solicitação ou apenas recebe demanda de produção?

### Pontos de controle críticos **[E]**

- Pagamento: a compensação da GRU é verificada automaticamente ou há intervenção manual possível?
- Atendimento presencial: o indeferimento é registrado em sistema auditável ou apenas em papel?
- Logística: o recebimento na unidade PF é confirmado em sistema ou apenas fisicamente?

---

## 14. Granularidade mínima esperada por etapa (novo — Aberto 4)

Para cada etapa do caso principal, o blueprint final deve conter no mínimo:

| Elemento | Descrição | Obrigatório? |
|---------|-----------|-------------|
| Nome da etapa | Rótulo claro e único | **[E]** |
| Ator(es) responsável(is) | Pelo menos o ator principal | **[E]** |
| Canal | Digital / presencial / interno | **[E]** |
| Tempo estimado | Com fonte ou marcado como `[sem dado]` | **[E]** |
| Evidência física/digital | Artefato gerado ou "ausente" | **[E]** |
| Controle existente | Pelo menos 1 ou "não identificado" | **[E]** |
| Fail point principal | Pelo menos 1 ou "não identificado" | **[E]** |
| Categoria do achado | Prescrito / observado / hipótese | **[E]** |
| Normativo aplicável | Pelo menos 1 N1 ou "não encontrado" | **[E]** |
| Variantes de exceção | Quando aplicável à etapa | **[C]** |

---

## 15. Convenção de arquivos

| Arquivo | Conteúdo |
|---------|----------|
| `B_jornada_cidadao.md` | Eixo (a) — inclui variantes e exceções sistêmicas |
| `C_mapa_atores.md` | Existente — validar conforme seção 7 |
| `D_evidencias_fisicas.md` | Eixo (c) |
| `E_normativos.md` | Eixo (d) |
| `F_fail_points.md` | Eixo (e) |
| `G_controles_internos.md` | Eixo (f) — novo |
| `H_service_blueprint.md` | Síntese — todos os eixos integrados |

---

## 16. Restrições

- **Não inventar:** achado sem fonte → `[não encontrado — requer verificação]`
- **Não prescrever:** este é AS-IS; melhoria pertence a fase posterior
- **Não inferir frequência:** sem dado empírico → `[inferência — sem dado empírico]`
- **Não generalizar N6:** relatos de usuário são hipóteses, não fatos
- **Não confirmar hipóteses técnicas sem fonte:** `[hipótese técnica]` exige investigação, não afirmação
- **Não misturar prescrito e observado** sem marcação explícita

---

## 17. Limitações estruturais declaradas

### 17.1 Brecha processo prescrito vs real (Falha 22 — Aberto parcial)

Esta pesquisa captura o processo prescrito com alta fidelidade. O processo real é acessível apenas indiretamente, via:
- Relatórios TCU/CGU (melhor proxy disponível)
- Reclamações formais da ouvidoria
- Pesquisa acadêmica com trabalho de campo

Estratégia de inferência controlada para bastidores inacessíveis: quando a fonte direta não existir, o executor pode construir uma descrição de bastidor por triangulação de (i) normativo que define a obrigação, (ii) relatório de controle que audita o cumprimento, e (iii) contrato publicado que define o escopo do fornecedor — marcando o resultado como `[inferência controlada — triangulação N1+N2+N3]`. Isso é distinto de invenção: é dedução documentada.

### 17.2 Validação empírica ausente (Aberto 5 — em aberto)

Validação empírica — shadowing, entrevistas com servidores, observação de atendimento — está **fora do escopo** desta pesquisa documental. O blueprint resultante deve declarar essa limitação explicitamente no arquivo `H_service_blueprint.md`. Recomenda-se planejamento de etapa de validação de campo como fase subsequente obrigatória para uso do blueprint em diagnóstico de riscos ou redesenho do serviço.

---

*Meta-prompt v3 — segunda revisão após auditoria externa. Versão 3.0.*
