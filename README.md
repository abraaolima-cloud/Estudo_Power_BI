

# Estudo_Power_bi DAX

📊 Funções DAX por categoria
➕ Agregação

Base para medidas.

SUM

SUMX

AVERAGE

AVERAGEX

MIN

MAX

MINX

MAXX

COUNT

COUNTA

COUNTX

COUNTROWS

DISTINCTCOUNT

Ex:

Total Vendas = SUM(Vendas[Valor])

🧠 Lógicas

IF

SWITCH

AND

OR

NOT

COALESCE

Meta Atingida = IF([Total] > 1000, "Sim", "Não")

📅 Data e Hora

Muito pedidas em entrevistas.

TODAY

NOW

DATE

YEAR

MONTH

DAY

WEEKDAY

EOMONTH

EDATE

DATEDIFF

CALENDAR

CALENDARAUTO

Inteligência de tempo:

TOTALYTD

TOTALMTD

TOTALQTD

SAMEPERIODLASTYEAR

DATEADD

DATESYTD

DATESMTD

🔎 Filtro e Contexto (o coração do DAX)

Aqui mora o nível sênior.

CALCULATE

CALCULATETABLE

FILTER

ALL

ALLEXCEPT

ALLSELECTED

KEEPFILTERS

VALUES

SELECTEDVALUE

HASONEVALUE

ISFILTERED

Vendas Ano Passado =
CALCULATE(
    [Total Vendas],
    SAMEPERIODLASTYEAR(Calendario[Data])
)

🧮 Tabela

ADDCOLUMNS

SUMMARIZE

SUMMARIZECOLUMNS

SELECTCOLUMNS

DISTINCT

UNION

INTERSECT

EXCEPT

CROSSJOIN

🔗 Relacionamento

RELATED

RELATEDTABLE

USERELATIONSHIP

TREATAS

🔤 Texto

CONCATENATE

CONCATENATEX

LEFT

RIGHT

MID

LEN

UPPER

LOWER

FORMAT

TRIM

🔢 Matemáticas

DIVIDE

ROUND

INT

ABS

MOD

Margem = DIVIDE([Lucro], [Receita], 0)

🎯 Estatísticas

RANKX

TOPN

PERCENTILEX.INC

MEDIAN

STDEVX.P

🚀 As 15 que você PRECISA dominar para o mercado

Se souber usar bem essas, já joga em nível alto:

CALCULATE, FILTER, ALL, ALLEXCEPT, VALUES, SELECTEDVALUE,
SUMX, AVERAGEX, COUNTROWS,
TOTALYTD, SAMEPERIODLASTYEAR,
DIVIDE, IF, SWITCH, RANKX.


🧠 As essenciais do DAX – explicação curta
CALCULATE

Muda o contexto de filtro de um cálculo.

A função mais importante do DAX.

CALCULATE([Total Vendas], Ano[Ano] = 2025)

FILTER

Cria um filtro com base em uma condição.

FILTER(Vendas, Vendas[Valor] > 100)

ALL

Remove filtros de uma tabela ou coluna.

CALCULATE([Total], ALL(Vendas))

ALLEXCEPT

Remove todos os filtros menos os informados.

CALCULATE([Total], ALLEXCEPT(Vendas, Vendas[Produto]))

VALUES

Retorna valores únicos dentro do contexto.

VALUES(Vendas[Produto])

SELECTEDVALUE

Retorna o valor quando apenas um está selecionado.

SELECTEDVALUE(Vendas[Produto])


Se tiver mais de um → retorna vazio ou valor padrão.

SUMX

Soma após fazer um cálculo linha a linha.

SUMX(Vendas, Vendas[Qtd] * Vendas[Preço])

AVERAGEX

Mesma ideia do SUMX, mas tira média.

COUNTROWS

Conta quantas linhas existem em uma tabela.

COUNTROWS(Vendas)

TOTALYTD

Calcula o acumulado no ano.

TOTALYTD([Total], Calendario[Data])

SAMEPERIODLASTYEAR

Puxa o mesmo período do ano anterior.

CALCULATE([Total], SAMEPERIODLASTYEAR(Calendario[Data]))

DIVIDE

Divisão segura (evita erro por zero).

DIVIDE([Lucro], [Receita], 0)

IF

Condição simples.

IF([Total] > 1000, "Bateu", "Não bateu")

SWITCH

Várias condições → mais organizado que vários IF.

SWITCH(
    TRUE(),
    [Total] < 100, "Baixo",
    [Total] < 500, "Médio",
    "Alto"
)

RANKX

Cria ranking.

RANKX(ALL(Produtos), [Total Vendas])

🎯 Tradução simples do que é DAX no dia a dia

CALCULATE → manda na regra do jogo

FILTER → define quem participa

ALL → limpa o histórico

X (SUMX, AVERAGEX) → calcula linha por linha

Tempo → compara períodos

DIVIDE / IF / SWITCH → cria inteligência de negócio

RANKX → competição
