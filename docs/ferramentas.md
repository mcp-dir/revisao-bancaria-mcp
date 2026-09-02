# Ferramentas

Revisão de Contrato Bancário expõe 16 ferramentas (todas somente leitura).

### 1. `calculo_atualizar`
**Input**: `parcelas`, `indice` (opcional), `data_calculo` (opcional), `taxa_juros` (opcional), `periodicidade_juros` (opcional), `juros_tipo` (opcional), `multa` (opcional), `multa_incide_sobre_juros` (opcional), `honorarios` (opcional), `honorarios_tipo` (opcional), `pro_rata` (opcional)

Atualização monetária / liquidação de débito judicial: corrige parcelas por um índice oficial (IPCA, INPC, IGP-M, SELIC, TR…) e aplica juros, multa e honorários.

### 2. `calculo_indice`
**Input**: `indice`, `data_inicial`, `data_final` (opcional), `valor` (opcional), `pro_rata` (opcional), `incluir_valores` (opcional)

Consulta de índice oficial: fator de correção acumulado entre duas datas (mês inicial excluído, mês final incluído — convenção BACEN/IBGE).

### 3. `calculo_salario_minimo`
**Input**: `ano` (opcional)

Salário mínimo nacional vigente de um ano (dinâmico, IPEADATA).

### 4. `calculo_aluguel`
**Input**: `aluguel_inicial`, `inicio_contrato`, `inicio_atraso`, `fim_atraso`, `data_calculo` (opcional), `indice` (opcional), `periodicidade_meses` (opcional), `juros` (opcional), `multa` (opcional)

Aluguéis em atraso (Lei 8.245/91): reajusta o aluguel ao longo do contrato pelo índice, corrige cada mês atrasado até hoje, aplica juros de mora (1% a.m.) e multa moratória.

### 5. `calculo_pensao`
**Input**: `forma`, `referencia`, `inicio_atraso`, `fim_atraso`, `data_calculo` (opcional), `indice` (opcional), `juros` (opcional), `pagamentos` (opcional), `remuneracoes` (opcional)

Pensão alimentícia em atraso (art.

### 6. `calculo_trabalhista`
**Input**: `salario`, `admissao`, `demissao`, `motivo` (opcional), `aviso` (opcional), `saldo_fgts` (opcional), `dependentes` (opcional), `ferias_vencidas` (opcional), `projetar_aviso` (opcional)

Verbas rescisórias / liquidação trabalhista (CLT): saldo de salário, aviso prévio indenizado (Lei 12.506/2011), 13º proporcional, férias proporcionais + 1/3, férias vencidas, multa de 40%/20% do FGTS, com descontos de…

### 7. `calculo_fgts`
**Input**: `depositos`, `data_calculo` (opcional), `indice` (opcional), `incluir_juros_3aa` (opcional)

Correção do FGTS (tese TR → INPC/IPCA-E, STF): por depósito calcula a diferença entre corrigir pelo índice de inflação vs pela TR, com juros de 3% a.a.

### 8. `calculo_dosimetria`
**Input**: `pena_min_anos`, `pena_max_anos`, `circunstancias_desfavoraveis` (opcional), `atenuantes` (opcional), `agravantes` (opcional), `causas_aumento` (opcional), `causas_diminuicao` (opcional), `fracao_fase1` (opcional), `fracao_fase2` (opcional)

Dosimetria da pena (art. 68 CP, sistema trifásico): pena-base pelas circunstâncias judiciais (art. 59), pena intermediária por atenuantes/agravantes (Súmula 231 STJ), pena definitiva por causas de aumento/diminuição (…

### 9. `calculo_progressao`
**Input**: `pena_anos`, `inicio_cumprimento`, `reincidente` (opcional), `hediondo` (opcional), `violencia` (opcional), `resultado_morte` (opcional), `dias_trabalhados` (opcional), `horas_estudo` (opcional), `dias_detracao` (opcional)

Progressão de regime (LEP art.

### 10. `calculo_partilha`
**Input**: `regime`, `bens`, `dividas` (opcional), `nomes` (opcional)

Partilha de bens no divórcio por regime (Código Civil): apura a massa partilhável (bens − dívidas conforme o regime) e a quota de cada cônjuge, com torna por desequilíbrio.

### 11. `calculo_tempo_contribuicao`
**Input**: `sexo`, `vinculos`

Tempo de contribuição (CNIS): soma os vínculos contando concomitância uma vez e converte atividade especial em comum (fatores EC 103/2019, só até 13/11/2019).

### 12. `calculo_rmi`
**Input**: `sexo`, `media_salarios`, `tempo_contribuicao_anos`, `salario_minimo` (opcional), `teto_inss` (opcional)

RMI — Renda Mensal Inicial (pós-reforma EC 103/2019): média dos salários de contribuição × coeficiente (60% + 2% por ano acima de 20H/15M), com piso (salário mínimo) e teto (INSS).

### 13. `calculo_revisional`
**Input**: `valor_financiado`, `num_parcelas`, `taxa_contratada_am`, `parcela_paga`, `sistema` (opcional), `modalidade` (opcional), `data_contrato` (opcional), `taxa_bacen_am` (opcional)

Revisional de contrato bancário: recalcula o financiamento pela taxa média de mercado do BACEN (busca ao vivo por modalidade+mês) e apura o excedente por parcela (Price ou SAC).

### 14. `calculo_superendividamento`
**Input**: `renda_liquida`, `dividas`, `minimo_existencial` (opcional), `prazo_meses` (opcional)

Superendividamento (Lei 14.181/2021): % da renda comprometida, mínimo existencial (R$600, parametrizável), renda disponível e capacidade de pagamento de um plano de até 5 anos.

### 15. `calculo_rmc_rcc`
**Input**: `beneficio_mensal`, `descontos`, `indice` (opcional), `data_calculo` (opcional), `tipo` (opcional)

RMC/RCC — reserva de margem consignável de cartão (INSS, códigos 217/268): limites de 5% e restituição corrigida dos descontos.

### 16. `calculo_restituicao_inss`
**Input**: `descontos`, `indice` (opcional), `data_calculo` (opcional)

Restituição de descontos indevidos no INSS (fraude associativa, códigos 280/304/310/378): soma as parcelas descontadas corrigidas.

## Prompts de exemplo

```
Recalcule este financiamento com juros de mercado pela SELIC
Compare os juros do contrato com a taxa média do BACEN no período
```
