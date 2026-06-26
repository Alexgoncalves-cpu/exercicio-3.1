# A — Meta-Prompt v2: Pesquisa Estruturada para Service Blueprint AS-IS
## Processo: Requisição de Passaporte na Polícia Federal (Brasil)
### Versão 2.0 — Revisada após auditoria externa (24 falhas endereçadas)

---

## Registro de auditoria (v1 → v2)

Esta seção documenta como cada falha da auditoria externa foi tratada. Nenhuma foi ignorada.

| # | Falha | Decisão | Resumo da ação |
|---|-------|---------|----------------|
| 1 | Classificação incorreta das camadas do blueprint | **(a) Corrigida** | Evidências físicas realocadas como camada transversal paralela, não como linha de interação interna |
| 2 | Confusão etapa vs artefato — presupõe universalidade | **(a) Corrigida** | Instrução reformulada: identificar *quais* etapas geram evidência, não pressupor que todas geram |
| 3 | Lei 7.116/1983 citada como obrigatória para passaporte | **(a) Corrigida** | Removida da lista obrigatória; reclassificada como contexto periférico opcional |
| 4 | Ausência do Decreto 5.978/2006 e portarias da PF | **(a) Corrigida** | Adicionados explicitamente como normativos prioritários obrigatórios |
| 5 | Bastidor superficial — omite consultas a bases externas | **(a) Corrigida** | Incluídas: RF (CPF), Justiça Eleitoral, Serviço Militar, mandados judiciais, antifraude |
| 6 | Processamento na PF mal descrito | **(a) Corrigida** | Detalhado: conferência ICAO, validação biométrica, assinatura digital, deferimento/indeferimento |
| 7 | Logística subdimensionada | **(a) Corrigida** | Incluídos: contrato logístico, cadeia de custódia, controles de extravio/roubo |
| 8 | Integração sistêmica ausente | **(a) Corrigida** | Adicionados: SINPA ↔ Casa da Moeda, SINCRE, gateway BCB/PIX |
| 9 | Tesouro Nacional tratado superficialmente | **(a) Corrigida** | Detalhado: fluxo SIAFI, compensação da GRU, validação automática vs manual |
| 10 | Evidências essenciais ausentes | **(a) Corrigida** | Incluídos: registro de biometria, status, deferimento/indeferimento, acompanhamento |
| 11 | Sem distinção evidência cidadão vs interna | **(a) Corrigida** | Tabela desdobrada em duas colunas: visibilidade ao cidadão / interna |
| 12 | Evidência negativa não considerada | **(a) Corrigida** | Incluídos: indeferimento, cancelamento, GRU expirada |
| 13 | LGPD sem vínculo operacional | **(a) Corrigida** | Especificados: base legal (obrigação legal), finalidade e prazo de retenção biométrica |
| 14 | Normas ICAO e Lei de Migração ausentes | **(a) Corrigida** | Adicionados: padrões ICAO Doc 9303, Lei 13.445/2017, portarias de comparecimento |
| 15 | GRU mal enquadrada normativamente | **(a) Corrigida** | Incluídos: STN e normativos SIAFI como reguladores primários da GRU |
| 16 | Categorias de fail point incompletas | **(a) Corrigida** | Adicionadas: falhas jurídicas, interoperabilidade de bases, governança descentralizada |
| 17 | Falhas específicas omitidas | **(a) Corrigida** | Incluídos: CPF irregular, expiração GRU, inconsistência biométrica, divergência cadastral |
| 18 | Frequência sem base empírica | **(a) Corrigida** | Coluna redenominada "Evidência de frequência"; exige fonte ou é marcada como inferência |
| 19 | Reclame Aqui como evidência | **(b) Defendida com qualificação** | Mantida como sinal qualitativo com caveat explícito de limitação estatística |
| 20 | Triangulação inexequível para bastidores | **(a) Corrigida** | Diferenciada: fontes públicas (triangulação obrigatória) vs processos internos (fonte única + marcação) |
| 21 | Rastreabilidade total irrealista | **(a) Corrigida** | Adicionada cláusula de exceção para informações classificadas/indisponíveis |
| 22 | Não garante visão AS-IS real | **(a) Corrigida** + **(c) Em aberto** | Adicionadas fontes etnográficas; brecha processo real vs prescrito marcada como limitação estrutural |
| 23 | Dependência de mapa de atores externo | **(b) Defendida** | Dependência é intencional e declarada; adicionados critérios de validação do mapa |
| 24 | Fluxo incompleto para casos reais | **(a) Corrigida** | Adicionados fluxos variantes: indeferimento, reemissão, urgência, passaporte anterior válido |

---

## Contexto e objetivo

Você é um analista de serviços públicos especializado em Service Design e mapeamento de processos. Sua tarefa é conduzir uma pesquisa estruturada que sirva de base empírica para a construção de um **Service Blueprint AS-IS** do processo de emissão de passaporte pela Polícia Federal do Brasil.

O blueprint descreve o serviço **como ele funciona hoje** (não como deveria funcionar). Há uma brecha reconhecida — e não eliminável nesta fase — entre o processo **prescrito** (descrito em normas e manuais) e o processo **real** (praticado nas unidades): veja a nota metodológica ao final deste documento.

---

## Camadas do Service Blueprint e eixos de pesquisa

A estrutura adota o modelo de Shostack (1982) e Bitner, Ostrom & Morgan (2008). As camadas são:

| Camada do Blueprint | Posição no diagrama | Eixo de pesquisa correspondente |
|---------------------|--------------------|---------------------------------|
| **Evidências físicas** | Faixa transversal superior (permeia todas as colunas) | **(c)** Evidências físicas |
| **Ações do cidadão** | Acima da linha de interação | **(a)** Jornada do cidadão |
| **Ações dos atores onstage** | Entre linha de interação e linha de visibilidade | **(b)** Bastidor — frente visível |
| **Ações dos atores backstage** | Abaixo da linha de visibilidade | **(b)** Bastidor — retaguarda oculta |
| **Processos de suporte** | Abaixo da linha de interação interna | **(b)** Bastidor — sistemas de suporte |
| **Base normativa** | Rodapé / anotação do blueprint | **(d)** Normativos |
| **Pontos de falha** | Anotações sobrepostas ao fluxo | **(e)** Fail points |

> ⚠️ **Nota metodológica — Falha 1 corrigida:** Evidências físicas não são uma "linha de interação interna". São uma camada paralela que corre ao longo de toda a experiência e aparecem em cada coluna do blueprint (uma por etapa), não em uma linha separada. A instrução anterior estava incorreta.

---

## Insumos disponíveis

- **Fluxo ponta a ponta (end-to-end)** do processo: fornecido pelo usuário (ver abaixo)
- **Mapa de Atores (RACI)**: arquivo `C_mapa_atores.md` — 13 atores com papéis R/A/C/I

> ⚠️ **Nota — Falha 23 defendida:** A dependência do `C_mapa_atores.md` é intencional e declarada. O pesquisador deve **validar** esse mapa antes de usá-lo, aplicando os critérios: (i) todos os atores mencionados no fluxo estão no mapa? (ii) os papéis RACI são consistentes com fontes normativas? (iii) há atores no fluxo real que não constam no mapa? Achados de validação devem ser registrados no arquivo de saída correspondente.

### Fluxo de referência — Casos e variantes

**Caso principal (cidadão adulto, primeira emissão, processo regular):**
1. Solicitação digital — SINPA (gov.br)
2. Pagamento da GRU (PIX / cartão / boleto)
3. Agendamento — Agenda Web (PF)
4. Atendimento presencial (PF) — conferência documental + coleta biométrica
5. Processamento e produção — Casa da Moeda do Brasil
6. Retirada presencial na unidade PF (prazo máximo: 90 dias)

**Variantes obrigatórias a mapear (Falha 24 corrigida):**

| Variante | Diferença em relação ao caso principal |
|----------|---------------------------------------|
| Indeferimento | Encerra o fluxo após a etapa 4; gera obrigações de notificação e recurso |
| Reemissão por perda/roubo | Exige BO; pode ter taxa diferenciada |
| Urgência / passaporte de emergência | Prazo comprimido; critérios específicos; pode dispensar agendamento |
| Renovação (passaporte anterior válido) | Simplificações documentais possíveis |
| Menor de idade | Exige autorização de ambos os responsáveis ou judicial |
| Restrição judicial | Fluxo encerrado; notificação ao requerente |

---

## Instruções gerais de pesquisa

### Fontes e triangulação (Falhas 19, 20, 21 corrigidas)

Aplique regras de fonte diferenciadas por tipo de informação:

**Para etapas públicas (jornada do cidadão, normativos, evidências visíveis):**
- Triangulação obrigatória: mínimo de 2 fontes independentes
- Fontes primárias: gov.br, portal PF, legislação federal, DOU
- Fontes secundárias: imprensa especializada, estudos acadêmicos
- Fontes qualitativas (sinal, não evidência estatística): relatos de usuários em fóruns e plataformas como Reclame Aqui — **usar exclusivamente para identificar hipóteses de fail points; nunca para afirmar frequência**

> ⚠️ **Falha 19 — qualificação:** Reclame Aqui e fóruns são fontes de sinal qualitativo, não de representatividade estatística. Citá-los exige marcação explícita: `[fonte qualitativa — sem representatividade estatística]`.

**Para processos internos e de bastidor:**
- Triangulação desejável, mas reconhecidamente difícil: acesse LAI, relatórios TCU/CGU, contratos no Portal da Transparência
- Se apenas uma fonte estiver disponível: registrar o achado com marcação `[fonte única — requer verificação adicional]`
- Se nenhuma fonte pública existir: registrar como `[não encontrado — processo interno opaco; requer acesso privilegiado ou LAI]`

> ⚠️ **Falha 21 — exceção:** Para informações classificadas, contratos sensíveis ou operações internas não publicadas (ex.: sistemas internos PF, operação da Casa da Moeda), a rastreabilidade total é **irrealista**. Registre a ausência; não infira.

---

## Eixo (a) — Jornada do Cidadão (linha de interação)

**Objetivo:** mapear cada ponto de contato do cidadão com o serviço, na sequência cronológica real, da necessidade até a posse do documento — e para cada variante relevante.

**Perguntas a responder:**
- Quais são os passos exatos que o cidadão executa, em qual ordem e por qual canal (digital / presencial / telefone)?
- Qual é o tempo médio/esperado em cada etapa (com fonte)?
- Quais decisões o cidadão precisa tomar (ex.: escolha de unidade, tipo de passaporte, urgência)?
- O que acontece quando a solicitação é **indeferida**? O cidadão é notificado? Por qual canal? Há recurso?
- Como o fluxo difere para: menores de idade, urgência, renovação, restrição judicial?

**Fontes prioritárias:** portal gov.br/passaporte, FAQ oficial da PF, tutoriais em vídeo oficiais, notas de imprensa de órgãos governamentais.

---

## Eixo (b) — Processos de Bastidor (backstage)

**Objetivo:** identificar todas as atividades realizadas pelos atores do sistema que o cidadão **não vê**, divididas em duas subcamadas: frente visível (onstage) e retaguarda oculta (backstage + suporte sistêmico).

### b.1 — Frente visível (onstage) — Atendente PF

**Perguntas a responder:**
- O que o atendente faz durante o atendimento presencial, passo a passo?
- Qual é o roteiro formal de conferência documental?
- Como é registrado o deferimento ou indeferimento?
- Como é capturada e validada a biometria segundo o padrão **ICAO Doc 9303**?
- Como é validada a assinatura digital do requerimento?

### b.2 — Retaguarda oculta (backstage) — Sistemas e atores não visíveis

**Consultas a bases externas (Falha 5 corrigida):**

Pesquise e descreva o que ocorre em cada consulta abaixo, quem a faz, quando e com que critério de bloqueio:

| Base consultada | Dado verificado | Impacto de irregularidade |
|----------------|-----------------|--------------------------|
| Receita Federal (CPF) | Regularidade do CPF | Bloqueio da solicitação |
| Tribunal Superior Eleitoral | Regularidade eleitoral | Bloqueio (para emissão) |
| Serviço Militar | Quitação militar (homens) | Bloqueio ou exigência adicional |
| Poder Judiciário | Mandados de prisão / restrição de saída do país | Bloqueio; comunicação ao juízo |
| Sistemas antifraude | Identidade, biometria, histórico | Sinalização para análise humana |
| SINCRE ou equivalente | Registros de estrangeiros / inconsistências | Verificação de identidade |

**Integração sistêmica (Falha 8 corrigida):**
- Como o SINPA envia a demanda para a Casa da Moeda? (protocolo, arquivo, sistema)
- Como o SINPA se integra ao sistema de agendamento e à biometria?
- Qual gateway processa o pagamento PIX/cartão? (integração BCB?)
- Como o status é atualizado em cada etapa para o cidadão?

**Fluxo de pagamento e conciliação — Tesouro Nacional / SIAFI (Falha 9 corrigida):**
- Como a GRU é gerada e o código de barras vinculado à solicitação?
- O que acontece no SIAFI após a compensação do pagamento?
- A validação é automática ou há verificação manual?
- Qual é o prazo de compensação e o que ocorre se expirar antes da validação?

**Produção e logística (Falha 7 corrigida):**
- Qual é o contrato logístico entre PF e transportadora? (verifique Portal da Transparência)
- Como funciona a cadeia de custódia de documento de segurança (rastreamento, lacre, assinatura de entrega)?
- Quais controles existem contra extravio, roubo ou troca de documentos?
- Como a unidade PF confirma o recebimento do lote?

**Fontes prioritárias:** relatórios TCU e CGU sobre o processo de passaporte, respostas a LAI publicadas, contratos publicados no Portal da Transparência, portarias internas da PF publicadas no DOU.

---

## Eixo (c) — Evidências Físicas (camada transversal do blueprint)

**Objetivo:** identificar os artefatos — físicos ou digitais — presentes em cada etapa do processo.

> ⚠️ **Falha 2 corrigida:** Nem toda etapa gera evidência para o cidadão. A instrução é: **identifique quais etapas geram evidências e quais não geram**. Registre a ausência de evidência quando aplicável — ela é informação relevante para o blueprint.

**Formato de saída obrigatório:** tabela com as colunas abaixo.

| Etapa | Evidência | Tipo (físico / digital) | Visibilidade | Emitido por | Finalidade |
|-------|-----------|------------------------|--------------|-------------|------------|
| | | | Cidadão / Interna | | |

> ⚠️ **Falha 11 corrigida:** A coluna "Visibilidade" distingue obrigatoriamente: (i) evidências acessíveis ao cidadão e (ii) evidências exclusivamente internas ao sistema ou à PF.

**Evidências obrigatórias a mapear (incluindo as da Falha 10):**
- Protocolo de solicitação (PDF / número de protocolo) — com situação atualizada em tempo real?
- Guia de Recolhimento da União (GRU) — boleto / QR code PIX
- Comprovante de agendamento
- Checklist oficial de documentos exigidos
- Recibo ou número de atendimento no balcão
- Registro biométrico capturado (foto ICAO + digitais) — evidência interna
- Registro de deferimento ou indeferimento — evidência interna + notificação ao cidadão?
- SMS / e-mail de notificação de status (em quais etapas?)
- Código de rastreamento logístico
- O passaporte (documento final)

**Evidências negativas (Falha 12 corrigida):**
- Notificação de indeferimento (forma, prazo, conteúdo)
- Notificação de cancelamento por não retirada
- Comunicação de GRU expirada / solicitação cancelada

---

## Eixo (d) — Normativos Aplicáveis

**Objetivo:** listar a base legal e regulatória que governa cada etapa do processo.

**Formato de saída:** tabela com colunas `Normativo | Tipo | Ementa resumida | Etapa(s) regulada(s) | Observação | URL ou referência`.

### Normativos obrigatórios (Falhas 3, 4, 14, 15 corrigidas)

**Base primária do passaporte:**
- **Decreto nº 5.978/2006** — Regulamento dos Passaportes Brasileiros *(principal normativo; ausente na v1)*
- Portarias vigentes da Polícia Federal sobre emissão de passaporte *(pesquisar no DOU — últimas publicações)*
- Normas da PF sobre comparecimento presencial obrigatório e prazos

**Documentação e identidade:**
- Lei nº 7.116/1983 *(documentos de identidade — RG)* — incluir **apenas como contexto periférico**, com nota: *"não regula passaporte diretamente"* *(Falha 3 corrigida)*
- Lei nº 13.445/2017 — Lei de Migração *(regula uso e validade do passaporte em contexto migratório)*

**Padrões internacionais (Falha 14 corrigida):**
- **ICAO Doc 9303** — Padrões para documentos de viagem legíveis por máquina *(obrigatório para emissão de passaporte compatível com leitura internacional)*

**Pagamento e arrecadação (Falha 15 corrigida):**
- Normativos da **Secretaria do Tesouro Nacional (STN)** sobre GRU
- Instruções sobre o **SIAFI** aplicáveis à arrecadação de taxas
- Portaria Interministerial que define o valor da taxa de passaporte (pesquisar versão vigente)
- *(Nota: a GRU não é regulada apenas por "IN da Receita" — o enquadramento correto é STN/SIAFI)* *(Falha 15 corrigida)*

**Dados pessoais e biometria (Falha 13 corrigida):**
- **Lei nº 13.709/2018 (LGPD)** — incluir com os seguintes detalhamentos obrigatórios:
  - Base legal aplicável: obrigação legal (art. 7º, II) e exercício regular de direito (art. 7º, VI)
  - Finalidade específica: identificação do requerente e segurança do documento
  - Prazo de retenção dos dados biométricos: pesquisar política da PF e/ou regulação específica

**Produção e segurança:**
- Normas da Casa da Moeda sobre produção de documentos de segurança *(pesquisar publicações no DOU)*

**Controle e transparência:**
- Lei nº 12.527/2011 (LAI) — acesso à informação sobre o processo
- Normas TCU e CGU aplicáveis à auditoria do serviço

**Acessibilidade:**
- Lei nº 13.146/2015 (Lei Brasileira de Inclusão) — atendimento presencial

---

## Eixo (e) — Fail Points Conhecidos

**Objetivo:** identificar sistematicamente onde o processo falha — por tipo de falha, impacto para o cidadão e evidência de frequência.

> ⚠️ **Falha 18 corrigida:** A coluna de frequência foi renomeada para **"Evidência de frequência"** e exige: (i) fonte empírica citada (relatório, dado estatístico, pesquisa), ou (ii) marcação explícita `[inferência — sem dado empírico]`. Classificações sem fonte são proibidas.

**Formato de saída obrigatório:**

| Fail Point | Etapa afetada | Categoria | Impacto para o cidadão | Evidência de frequência | Fonte |
|------------|--------------|-----------|------------------------|------------------------|-------|

### Categorias de falha (Falha 16 corrigida — categorias expandidas)

**Falhas técnicas:**
- Indisponibilidade do SINPA, Agenda Web ou GRU
- Falha de integração entre sistemas (ex.: pagamento compensado mas não reconhecido pelo agendamento)

**Falhas operacionais:**
- Documentação incompleta ou inválida detectada no presencial
- Inconsistência biométrica (Falha 17 corrigida)
- Prazo de produção estourado

**Falhas de interoperabilidade de bases (Falha 16 corrigida):**
- CPF irregular bloqueando emissão (Falha 17 corrigida)
- Divergência de dados cadastrais entre bases (ex.: nome diferente na Receita e no BO)
- Inconsistência de regularidade eleitoral

**Falhas jurídicas (Falha 16 corrigida):**
- Restrição judicial impeditiva (mandado de prisão, proibição de saída do país)
- Menores sem autorização judicial ou dos responsáveis

**Falhas financeiras:**
- GRU expirada antes da validação (Falha 17 corrigida)
- Pagamento não reconhecido por falha de compensação bancária

**Falhas logísticas:**
- Atraso de entrega na unidade PF
- Passaporte extraviado ou trocado no transporte

**Falhas de comunicação:**
- Cidadão não notificado sobre status, indeferimento ou disponibilidade para retirada
- Informações divergentes entre canais (site vs atendente vs FAQ)

**Falhas de capacidade:**
- Falta de vagas para agendamento (demanda reprimida — Falha 17 corrigida)
- Filas no atendimento presencial além do tempo estimado

**Falhas de governança (Falha 16 corrigida):**
- Divergência de interpretação de requisitos documentais entre unidades da PF
- Inconsistência de critérios de deferimento/indeferimento entre servidores

**Fontes prioritárias:** relatórios TCU e CGU sobre emissão de passaporte (pesquisar por ano), ouvidoria da PF (relatórios anuais publicados), notícias de imprensa com dados concretos, trabalhos acadêmicos sobre digitalização de serviços públicos.

---

## Formato de saída e convenção de arquivos

| Arquivo | Conteúdo |
|---------|----------|
| `B_jornada_cidadao.md` | Resultado do Eixo (a) — inclui variantes |
| `C_mapa_atores.md` | Já existente — validar conforme critérios acima |
| `D_evidencias_fisicas.md` | Resultado do Eixo (c) |
| `E_normativos.md` | Resultado do Eixo (d) |
| `F_fail_points.md` | Resultado do Eixo (e) |
| `G_service_blueprint.md` | Síntese integrando todos os eixos no blueprint AS-IS |

---

## Critérios de qualidade da pesquisa (revisados)

| Critério | Descrição | Exceção admitida |
|----------|-----------|-----------------|
| Rastreabilidade | Todo achado tem fonte citada | Processos internos opacos: registrar como "não encontrado" |
| Separação de camadas | Cada achado está no eixo correto | — |
| Cobertura | Todas as etapas do fluxo + variantes estão representadas | — |
| Consistência com o mapa de atores | Achados coerentes com `C_mapa_atores.md` após validação | Divergências devem ser explicitadas |
| Atualidade | Priorizar fontes 2022–2025 | Normativos de data anterior se vigentes |
| Visão AS-IS | Descreve o processo como existe hoje | — |
| Distinção prescrito vs real | Indicar quando fonte descreve norma (prescrito) vs prática observada (real) | — |

---

## Restrições (revisadas)

- **Não inventar:** se uma informação não for encontrada, registre como `[não encontrado — requer verificação]`
- **Não prescrever:** este é um blueprint AS-IS; sugestões de melhoria pertencem a uma fase posterior
- **Não duplicar:** se um achado pertence a dois eixos, registre no mais específico e faça referência cruzada
- **Não inferir frequência:** sem dado empírico, marque `[inferência — sem dado empírico]`
- **Não generalizar fontes qualitativas:** relatos de usuários indicam hipóteses, não fatos estabelecidos

---

## Nota metodológica — Limitação estrutural em aberto

> **(Falha 22 — parcialmente corrigida, parcialmente em aberto)**

A pesquisa baseada em fontes públicas captura predominantemente o **processo prescrito** (como a PF diz que o serviço funciona) — não necessariamente o **processo real** (como ele de fato acontece nas unidades).

Para aproximar a pesquisa do processo real, recomenda-se:
- Priorizar **relatórios de auditoria TCU/CGU**, que frequentemente documentam divergências entre prescrito e real
- Considerar **análises de reclamações formais** da ouvidoria da PF como proxy do processo real
- Se possível, incorporar **relatos de servidores** via LAI ou publicações acadêmicas com pesquisa de campo

**Limitação reconhecida e não eliminável nesta fase:** sem acesso direto a sistemas internos da PF, à operação da Casa da Moeda ou à observação de campo (shadowing), o blueprint resultante terá maior fidelidade nas etapas visíveis ao cidadão e menor fidelidade nas etapas de bastidor. Essa limitação deve ser declarada explicitamente no arquivo `G_service_blueprint.md`.

---

*Meta-prompt v2 — elaborado após auditoria externa de 24 pontos. Versão 2.0.*
