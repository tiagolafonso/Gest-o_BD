# Introdução à gestão de bases de dados
Tiago Afonso
2025-11-25

<img
src="Introdução_BD_files\figure-markdown_strict\descarregar.png"
/>


# Objetivos

-   Compreender importância da gestão de dados
-   Conhecer conceitos fundamentais
-   Identificar tipos de dados em contextos empresariais

# Conteúdos

-   Conceito dado vs. informação;
-   Importância qualidade dados;
-   Tipos de dados (pessoais, comerciais);
-   Bases de dados relacionais;
-   Características base de dados

## O que é um dado?

Dado é um facto bruto, um elemento **isolado** que, por si só, não
transmite significado ou contexto. É a matéria-prima que, quando
processada e organizada, pode ser transformada em informação útil para a
tomada de decisões.

### Exemplos de dados

-   João Silva
-   912345678
-   25
-   Lisboa

Esses são dados individuais, elementos de informação, quando
organizados, tornam-se úteis.

## O que é informação?

Informação é o resultado do processamento, organização e interpretação
dos dados. É o dado contextualizado que fornece significado e valor,
permitindo a compreensão e a tomada de decisões informadas em factos
específicos.

## Dados vs. Informação

<table>
<colgroup>
<col style="width: 37%" />
<col style="width: 62%" />
</colgroup>
<thead>
<tr>
<th>Dados</th>
<th>Informação</th>
</tr>
</thead>
<tbody>
<tr>
<td>Silva<br>912345678<br>João<br>Lisboa<br>Cliente</td>
<td>- João Silva é um cliente de Lisboa<br>- Pode ser contatado pelo
telefone 912345678<br>- Registado como cliente ativo</td>
</tr>
</tbody>
</table>

## Importância da qualidade dos dados

Dados brutos vs. informação contextualizada

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr>
<th>Dados</th>
</tr>
</thead>
<tbody>
<tr>
<td>Silva, João - 912345678 - joao@email.com; Maria Costa 961234567
maria@email.pt Lisboa; pedro@email.com - Pedro Oliveira 68901234;Braga -
Rita Santos - rita@email.pt</td>
</tr>
</tbody>
</table>

Dados Organizados em Tabela

<table>
<thead>
<tr>
<th>Nome</th>
<th>Telefone</th>
<th>Email</th>
<th>Cidade</th>
</tr>
</thead>
<tbody>
<tr>
<td>João Silva</td>
<td>912345678</td>
<td>joao@email.com</td>
<td>Lisboa</td>
</tr>
<tr>
<td>Maria Costa</td>
<td>961234567</td>
<td>maria@email.pt</td>
<td></td>
</tr>
<tr>
<td>Pedro Oliveira</td>
<td>968901234</td>
<td>pedro@email.com</td>
<td></td>
</tr>
<tr>
<td>Rita Santos</td>
<td></td>
<td>rita@email.pt</td>
<td>Braga</td>
</tr>
</tbody>
</table>

A mesma informação mas agora organizada de forma clara e acessível.

## Tipos de dados/variáveis

-   **Dados Qualitativos** Não podem ser medidos, ou facilmente
    convertidos em números. Normalmente são listados como *Nomes*,
    *Descrições* ou *Categorias*.

    -   **Ordenados** São dados que podem ser ordenados ou classificados
        numa escala. Por exemplo, a classificação de um filme ou a
        posição de um atleta numa corrida.

    -   **Nominais** São dados que podem ser categorizados sem uma
        ordem. Por exemplo, a cor de um carro.

-   **Dados Quantitativos** Podem ser medidos e expressos em números.
    Representam *quantidades*, *medidas* ou *intervalos*.

    -   **Discretos** São dados que podem ser contados e que têm um
        número finito de valores possíveis. Por exemplo, o número de
        alunos numa sala de aula ou o número de carros numa rua. Não
        existe 1,5 carros.

    -   **Contínuos** São dados que podem ser medidos e que têm um
        número infinito de valores possíveis. Por exemplo, a altura de
        uma pessoa ou a velocidade de um carro. Existe 1,5111111(1)
        metros de altura.

## Formato dos dados

-   **Dados Tabulares/estruturados** São dados organizados em linhas e
    colunas. Cada linha representa um registo e cada coluna representa
    um atributo. Podem não ser necessariamente uma tabela visível, mas
    sim uma estrutura organizada. Por exemplo, ficheiro `csv`:

<table>
<thead>
<tr>
<th>Nome; Idade; Cidade</th>
</tr>
</thead>
<tbody>
<tr>
<td>João Silva; 30; Lisboa</td>
</tr>
<tr>
<td>Maria Costa; 25; Porto</td>
</tr>
</tbody>
</table>

-   **Dados Não-estruturados** São dados que não estão organizados numa
    estrutura específica. Por exemplo, texto, imagens, vídeos, áudio,
    etc.

## Quanto ao período de tempo

Para determinar o período de tempo, é importante considerar:

-   **Frequência de atualização** - Com que frequência os dados são
    atualizados? Anualmente, mensalmente, diariamente, intra
    diariamente, etc.

-   **Granularidade dos dados** - Qual é a unidade de tempo dos dados?
    Segundos, minutos, horas, dias, semanas, meses, anos, etc.

-   **Horizonte temporal** - Qual é o horizonte temporal dos dados?
    2000-2020, 2010-2020, 2020-2025, etc.

Tendo em a periodicidade dos dados, podemos dividir os dados em duas
categorias:

-   **Dados Estáticos** - Dados que não mudam ao longo do tempo. Por
    exemplo, *inquéritos de satisfação*, *listas de clientes*, *listas
    de produtos*, etc.

-   **Dados dinâmicos/Séries Temporais** - Dados que mudam ao longo do
    tempo. Por exemplo, *vendas diárias*, *temperatura diária*, *preço
    das ações*, etc.

## Recolher dados

Considerando a recolha de dados, podemos dividir o processo em dois
tipos:

-   **Dados primários** - Dados recolhidos diretamente pelo investigador
    para um propósito específico. Por exemplo, *inquéritos*,
    *entrevistas*, etc.

    -   Vantagens:
        -   Controlo total sobre a recolha de dados.
        -   Dados específicos para o propósito do estudo.
    -   Desvantagens:
        -   Custo e tempo associados à recolha de dados.
        -   Possibilidade de enviesamento dos dados.

O enviesamento dos dados ou da amostra é um problema comum na recolha de
dados primários. Pode ocorrer quando a amostra não é representativa da
população ou quando os dados são recolhidos de forma tendenciosa (para
obter um determinado resultado). Por exemplo: *amostra de conveniência*,
*amostra de voluntários*, *amostra de amigos*, etc.

-   **Dados secundários** - Dados que já foram recolhidos por outra
    pessoa ou organização para um propósito diferente. Por exemplo,
    *bases de dados públicas*, *relatórios de mercado*, *estudos
    científicos*, etc.

    -   Vantagens:
        -   Custo e tempo reduzidos na recolha de dados.
        -   Dados de fontes credíveis e confiáveis.
        -   Possibilidade de comparação com outros estudos.
        -   garantia de metodologia adequada na recolha de dados.
    -   Desvantagens:
        -   Dados podem não ser específicos para o propósito do estudo.
        -   Dados podem estar desatualizados ou incompletos.
        -   Dados podem não estar disponíveis para o período de tempo
            desejado.

Quando recorremos a dados secundários, é importante avaliar a qualidade
dos dados e a credibilidade da fonte. Por exemplo, verificar a
metodologia de recolha de dados, a representatividade da amostra a
fiabilidade dos dados.

# Estrutura de dados

Os dados podem estar organizados de diferentes formas, dependendo do
tipo de análise que pretendemos realizar. As duas formas mais comuns de
organizar os dados são:

## Dados em formato largo (*wide data*)

Os dados em formato largo são organizados de forma a que cada linha
represente uma observação e cada coluna represente uma variável. Este
formato é mais comum em bases de dados tabulares e é mais fácil de ler e
interpretar.

Por exemplo, considere a seguinte tabela com dados de vendas de
produtos:

<table>
<thead>
<tr>
<th>Data</th>
<th>Produto A</th>
<th>Produto B</th>
<th>Produto C</th>
</tr>
</thead>
<tbody>
<tr>
<td>2025-01-01</td>
<td>100</td>
<td>200</td>
<td>150</td>
</tr>
<tr>
<td>2025-01-02</td>
<td>120</td>
<td>180</td>
<td>160</td>
</tr>
<tr>
<td>2025-01-03</td>
<td>130</td>
<td>190</td>
<td>170</td>
</tr>
</tbody>
</table>

Neste formato, cada linha representa uma data e cada coluna representa
um produto. Este formato é útil para análises que envolvem comparações
entre produtos ou ao longo do tempo.

## Dados em formato longo (*long data*)

Os dados em formato longo são organizados de forma a que cada linha
represente uma observação única. Este formato é mais comum em análises
estatísticas e é mais eficiente para armazenar grandes volumes de dados.

Por exemplo, considere a seguinte tabela com os mesmos dados de vendas
de produtos, mas em formato longo:

<table>
<thead>
<tr>
<th>Data</th>
<th>Produto</th>
<th>Vendas</th>
</tr>
</thead>
<tbody>
<tr>
<td>2025-01-01</td>
<td>A</td>
<td>100</td>
</tr>
<tr>
<td>2025-01-01</td>
<td>B</td>
<td>200</td>
</tr>
<tr>
<td>2025-01-01</td>
<td>C</td>
<td>150</td>
</tr>
<tr>
<td>2025-01-02</td>
<td>A</td>
<td>120</td>
</tr>
<tr>
<td>2025-01-02</td>
<td>B</td>
<td>180</td>
</tr>
<tr>
<td>2025-01-02</td>
<td>C</td>
<td>160</td>
</tr>
<tr>
<td>2025-01-03</td>
<td>A</td>
<td>130</td>
</tr>
<tr>
<td>2025-01-03</td>
<td>B</td>
<td>190</td>
</tr>
<tr>
<td>2025-01-03</td>
<td>C</td>
<td>170</td>
</tr>
</tbody>
</table>

Neste formato, cada linha representa uma venda de um produto numa
determinada data. Este formato é útil para análises estatísticas que
envolvem a comparação de diferentes produtos ou datas.

## Componentes da estrutura de dados

Na área da economia, os dados podem ser organizados de diferentes
formas, dependendo do tipo de análise que pretendemos realizar. Por
exemplo, os dados macroeconómicos são normalmente organizados em séries
temporais, onde cada linha representa uma observação ao longo do tempo.

Nos dados económicos existem 3 dimensões:

-   **Entidades** (*i* = 1, ...*n*) - Indivíduos, empresas, países, etc.

-   **Variáveis**
    (*x*<sub>1</sub>, *x*<sub>2</sub>, *x*<sub>3</sub>, ..., *x*<sub>*j*</sub>) -
    compras, vendas, preços, etc.

-   **Períodos de tempo** (*t* = 1, ..., *T*) - Anos, trimestres, meses,
    etc.

### Dados seccionais

Várias entidades (*i* = 1, ...*n*), varias variáveis
(*x*<sub>1</sub>, *x*<sub>2</sub>, *x*<sub>3</sub>, *x*<sub>*j*</sub>) e
um periodo de tempo (*t* = 1)

Os *dados seccionais* são dados recolhidos numa determinada altura e
referem-se a uma amostra de indivíduos, empresas, países, etc. Por
exemplo, um inquérito de satisfação aos clientes de um supermercado num
determinado dia/mês. Exemplo:

<table>
<thead>
<tr>
<th>Cliente</th>
<th>Idade</th>
<th>Sexo</th>
<th>Profissão</th>
<th>Rendimento</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>25</td>
<td>M</td>
<td>Estudante</td>
<td>1000</td>
</tr>
<tr>
<td>2</td>
<td>35</td>
<td>F</td>
<td>Empresária</td>
<td>2000</td>
</tr>
<tr>
<td>3</td>
<td>45</td>
<td>M</td>
<td>Médico</td>
<td>3000</td>
</tr>
</tbody>
</table>

### Séries Temporais

Uma entidade (*i* = 1), várias variáveis
(*x*<sub>1</sub>, *x*<sub>2</sub>, *x*<sub>3</sub>, *x*<sub>*j*</sub>) e
vários periodos de tempo (*t* = 1, ...*T*)

As *séries temporais* são dados recolhidos ao longo do tempo e
referem-se a uma unidade (indivíduo, empresa, país, etc.). Por exemplo,
o histórico de vendas de uma empresa ao longo de vários anos.

Exemplo:

<table>
<thead>
<tr>
<th>Ano</th>
<th>Vendas</th>
<th>Preço Unitário</th>
</tr>
</thead>
<tbody>
<tr>
<td>2022</td>
<td>1000</td>
<td>10</td>
</tr>
<tr>
<td>2023</td>
<td>1100</td>
<td>11</td>
</tr>
<tr>
<td>2024</td>
<td>1200</td>
<td>12</td>
</tr>
<tr>
<td>2025</td>
<td>1300</td>
<td>13</td>
</tr>
</tbody>
</table>

### Dados em painel

Várias entidades (*i* = 1, ...*n*), várias variáveis
(*x*<sub>1</sub>, *x*<sub>2</sub>, *x*<sub>3</sub>, .., *x*<sub>*j*</sub>)
e vários periodos de tempo (*t* = 1, ...*T*)

Os *dados em painel* combinam as características dos dados seccionais e
longitudinais, ou seja, são dados recolhidos ao longo do tempo e
referem-se a uma amostra de indivíduos, empresas, países, etc. Por
exemplo, o histórico de vendas de várias empresas ao longo de vários
anos.

Exemplo:

<table>
<thead>
<tr>
<th>País</th>
<th>Ano</th>
<th>Vendas</th>
<th>Preço Unitário</th>
</tr>
</thead>
<tbody>
<tr>
<td>Portugal</td>
<td>2022</td>
<td>1000</td>
<td>10</td>
</tr>
<tr>
<td>Portugal</td>
<td>2023</td>
<td>1100</td>
<td>11</td>
</tr>
<tr>
<td>Portugal</td>
<td>2024</td>
<td>1200</td>
<td>12</td>
</tr>
<tr>
<td>Portugal</td>
<td>2025</td>
<td>1300</td>
<td>13</td>
</tr>
<tr>
<td>Espanha</td>
<td>2022</td>
<td>2000</td>
<td>20</td>
</tr>
<tr>
<td>Espanha</td>
<td>2023</td>
<td>2100</td>
<td>21</td>
</tr>
<tr>
<td>Espanha</td>
<td>2024</td>
<td>2200</td>
<td>22</td>
</tr>
<tr>
<td>Espanha</td>
<td>2025</td>
<td>2300</td>
<td>23</td>
</tr>
</tbody>
</table>

## Tipos de dados em contexto empresarial

-   **Dados Pessoais** - Informações que identificam ou podem
    identificar um indivíduo, como nome, endereço, número de telefone,
    e-mail, etc.

-   

-   **Dados Comerciais** - Informações relacionadas com as operações
    comerciais de uma empresa, como vendas, compras, inventário,
    clientes, fornecedores, etc.

-   

-   **Dados Financeiros** - Informações relacionadas com as finanças de
    uma empresa, como receitas, despesas, lucros, perdas, balanços, etc.

-   

-   **Dados Operacionais** - Informações relacionadas com as operações
    diárias de uma empresa, como produção, logística, recursos humanos,
    etc.

-   

-   **Dados de Marketing** - Informações relacionadas com as atividades
    de marketing de uma empresa, como campanhas publicitárias, pesquisas
    de mercado, comportamento do consumidor, etc.

-   **Dados Técnicos** - Informações relacionadas com os aspectos
    técnicos de uma empresa, como especificações de produtos, manuais de
    operação, marcas e modelos, etc.

# Porque é importante a Qualidade dos Dados nas Empresas?

-   **Decisões Informadas**: dados errados podem levar a decisões
    incorretas.

-   **Confiança dos clientes**: erros na base de dados podem prejudicar
    a imagem da empresa.

-   **Eficiência Operacional**: dados de má qualidade podem causar
    atrasos e erros nos processos.

-   **Conformidade Legal**: dados incorretos podem levar a multas e
    sanções.

## Dinâmica do telefone estragado

# A Pirâmide de Valor

O ocnceito de Pirâmide de Valor ilustra como os dados brutos, quando
processados e analisados, podem gerar valor significativo para as
empresas.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 38%" />
<col style="width: 36%" />
</colgroup>
<thead>
<tr>
<th>Nível</th>
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dados</td>
<td>Fatos brutos e não processados</td>
<td>Registos de vendas diárias</td>
</tr>
<tr>
<td>Informação</td>
<td>Dados organizados e contextualizados</td>
<td>Relatórios mensais de vendas por produto</td>
</tr>
<tr>
<td>Conhecimento</td>
<td>Análise e interpretação da informação</td>
<td>Tendências de vendas e preferências dos clientes</td>
</tr>
<tr>
<td>Sabedoria</td>
<td>Aplicação do conhecimento para decisões estratégicas</td>
<td></td>
</tr>
<tr>
<td>Estratégias de marketing baseadas em análises de vendas</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Base: DADOS (Símbolos, Fatos brutos). Ex: “5”, “Azul”, “Sim”.
Meio-Baixo: INFORMAÇÃO (Dados + Contexto). Ex: “5 reclamações”, “Cor
Azul”, “Cliente VIP: Sim”. Meio-Alto: CONHECIMENTO (Padrões,
Experiência). Ex: “Os produtos azuis têm 5 reclamações, logo têm
defeito.” Topo: SABEDORIA/AÇÃO (Decisão). Ex: “Retirar produtos azuis do
catálogo.”.5

# O que é uma Base de Dados?

## Definição: Base de Dados

> **O que é uma Base de Dados?**
>
> Um **conjunto organizado de informações** estruturado de forma lógica,
> permitindo fácil **armazenamento**, **consulta** e **atualização**.

Uma base de dados é que um arquivo digital muito eficiente. Organizamos
informações em tabelas com Campos e registos.

Exemplo de base de dados de clientes:

<table>
<thead>
<tr>
<th>ID Cliente</th>
<th>Nome</th>
<th>Telefone</th>
<th>Email</th>
<th>Cidade</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>João Silva</td>
<td>912345678</td>
<td>joao@email.com</td>
<td>Lisboa</td>
</tr>
<tr>
<td>2</td>
<td>Maria Costa</td>
<td>961234567</td>
<td>maria@email.com</td>
<td>Porto</td>
</tr>
<tr>
<td>3</td>
<td>Pedro Oliveira</td>
<td>968901234</td>
<td>pedro@email.com</td>
<td>Coimbra</td>
</tr>
<tr>
<td>4</td>
<td>Rita Santos</td>
<td>934567890</td>
<td>rita@email.com</td>
<td>Faro</td>
</tr>
</tbody>
</table>

## Principais benefícios das Bases de Dados

-   Acesso rápido e fácil a informações
-   Redução de erros e inconsistências
-   Economia de tempo nas buscas
-   Facilita análise e tomada de decisão
-   Segurança e proteção de dados
-   Escalabilidade - cresce com o negócio

## Exemplo Real: Loja Online

Empresa: Loja Online “*TechStore*”

**Situação**: A loja tinha informações de clientes espalhadas por folhas
de Excel, e-mails e ficheiros de papel.

**Problema**: Clientes duplicados, contactos errados, ofertas não
personalizadas, muitos clientes insatisfeitos.

**Solução**: Implementação de uma base de dados centralizada com todos
os clientes estruturados.

**Resultados**:

-   Redução de 30% de duplicatas.
-   Melhoria de 25% da satisfação dos clientes.
-   Economia de 8 horas por semana na gestão manual.
-   Possibilidade de análise para vender melhor.

## Desafios mais comuns na gestão de bases de dados

-   Dados duplicados:

O mesmo cliente registado várias vezes com variações no nome ou
contacto.

-   Inconsistências:

Formato diferente de campos (João vs Joao vs JOÃO).

-   Dados incompletos:

Campos importantes em branco, com informação parcial.

-   Falta de segurança:

Acesso não autorizado a dados sensíveis.

-   Organização deficiente:

Dados mal estruturados, dificultando buscas e análises.

## Entidade e Atributos

O conceito de entidade e atributos é fundamental em bases de dados. Na
realidade para construirmos esse modelo, temos de identificar as coisas
sobre as quais queremos guardar informação. Chamamos essas coisas
entidades.

Exemplos de entidades em negócios: clientes, fornecedores, produtos
encomendas.

Cada entidade tem características ou propriedades que queremos
armazenar. Essas características são chamadas **ATRIBUTOS**.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr>
<th>ID (Identificador)</th>
<th>Nome (Texto)</th>
<th>NIF (Nominal)</th>
<th>Cidade (Nominal)</th>
<th>Data Nascimento (Tempo)</th>
<th style="text-align: right;">Saldo (€) (Quantitativo)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Ana Silva</td>
<td>200…</td>
<td>Lisboa</td>
<td>12/05/1985</td>
<td style="text-align: right;">50,00</td>
</tr>
<tr>
<td>2</td>
<td>Rui Costa</td>
<td>190…</td>
<td>Porto</td>
<td>01/01/1990</td>
<td style="text-align: right;">-10,00</td>
</tr>
</tbody>
</table>

## Atomicidade

Cada atributo deve ser atómico, ou seja, não deve ser possível dividi-lo
em partes menores. Por exemplo, o atributo “Nome” deve conter apenas o
nome completo, e não o nome e o sobrenome separados.

## Unicidade do Identificador

Imaginem que entra outro cliente chamado Ana Silva. Como é que o
computador (ou o nosso arquivo de papel) sabe qual é qual? O nome não
serve como chave porque há homónimos. O NIF pode servir, mas e se for um
cliente estrangeiro sem NIF português?

Por isso criamos um ID Interno (1, 2, 3…). É um número que nunca muda e
nunca se repete. É a matrícula do cliente na nossa empresa.

## Armadilha da tabela larga

Vamos registas as vendas mensais. Temos 3 produtos (A, B, C).

<table>
<thead>
<tr>
<th>Produto</th>
<th>Vendas Jan</th>
</tr>
</thead>
<tbody>
<tr>
<td>A</td>
<td>100</td>
</tr>
<tr>
<td>B</td>
<td>150</td>
</tr>
<tr>
<td>C</td>
<td>200</td>
</tr>
</tbody>
</table>

Aggora para Fevereiro:

<table>
<thead>
<tr>
<th>Produto</th>
<th>Vendas Jan</th>
<th>Vendas Fev</th>
</tr>
</thead>
<tbody>
<tr>
<td>A</td>
<td>100</td>
<td>120</td>
</tr>
<tr>
<td>B</td>
<td>150</td>
<td>130</td>
</tr>
<tr>
<td>C</td>
<td>200</td>
<td>180</td>
</tr>
</tbody>
</table>

Qual o problema? sempre que adicionaoms uma coluna nova temos de alterar
a estrutura da base de dados. Para isso utilizamos o formato longo:

<table>
<thead>
<tr>
<th>Produto</th>
<th>Mês</th>
<th>Vendas</th>
</tr>
</thead>
<tbody>
<tr>
<td>A</td>
<td>Jan</td>
<td>100</td>
</tr>
<tr>
<td>A</td>
<td>Fev</td>
<td>120</td>
</tr>
<tr>
<td>B</td>
<td>Jan</td>
<td>150</td>
</tr>
<tr>
<td>B</td>
<td>Fev</td>
<td>130</td>
</tr>
<tr>
<td>C</td>
<td>Jan</td>
<td>200</td>
</tr>
<tr>
<td>C</td>
<td>Fev</td>
<td>180</td>
</tr>
</tbody>
</table>

Desta forma, sempre que adicionamos um mês novo, só temos de adicionar
linhas novas. A estrutura da base de dados mantém-se igual.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 37%" />
<col style="width: 37%" />
</colgroup>
<thead>
<tr>
<th>Característica</th>
<th>Formato Largo (Wide)</th>
<th>Formato Longo (Long)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Leitura Humana</td>
<td>Fácil (visualmente intuitivo)</td>
<td>Difícil (repetitivo)</td>
</tr>
<tr>
<td>Entrada de Dados</td>
<td>Exige criar novas colunas (mudança estrutural)</td>
<td>Apenas adicionar linhas (conteúdo)</td>
</tr>
<tr>
<td>Análise (Filtros)</td>
<td>Difícil comparar Jan com Fev automaticamente</td>
<td>Fácil filtrar por “Mês” ou “Produto”</td>
</tr>
<tr>
<td>Escalabilidade</td>
<td>Limitada pela largura da página/ecrã</td>
<td>Infinita (vertical)</td>
</tr>
</tbody>
</table>

O formato lonfo é mais flexível e escalável para bases de dados
dinâmicas, onde os dados são atualizados regularmente. O formato largo é
mais adequado para relatórios estáticos ou apresentações.

## Lógica Relacional e Normalização

A redundância de dados é o inimigo silencioso da eficiência. Em sistemas
manuais, a redundância (escrever a morada do cliente em cada nova
fatura) é fisicamente dolorosa. Em sistemas digitais, é perigosa porque
cria anomalias de atualização. A Normalização de Bases de Dados é o
processo formal de organizar dados para minimizar a redundância. Embora
existam várias “Formas Normais” complexas (1NF, 2NF, 3NF, BCNF), para
iniciantes, o foco deve ser nos princípios práticos: Atomicidade e
Eliminação de Repetições.
(https://learn.microsoft.com/en-us/troubleshoot/microsoft-365-apps/access/database-normalization-description
e https://www.knack.com/blog/database-normalization-no-code/).

As anomalias de base de dados explicam porque normalizamos :

-   Anomalia de Inserção: Não conseguir registar um fornecedor porque
    ele ainda não tem produtos associados.
-   Anomalia de Atualização: Ter de corrigir o telefone do fornecedor em
    500 faturas antigas.
-   Anomalia de Eliminação: Apagar a última fatura de um cliente e
    perder, inadvertidamente, o contacto dele.

## Base de Dados Relacional

1.  **Tabelas**: Dados organizados em tabelas (entidades) com linhas
    (registos) e colunas (atributos). Também chamadas de “concultas”.

2.  **Chaves Primárias**: Identificadores únicos para cada registo numa
    tabela (ex: ID Cliente).

3.  **Chaves Estrangeiras**: Atributos que ligam tabelas diferentes,
    referenciando a chave primária de outra tabela (ex: ID Cliente numa
    tabela de encomendas). Por vezes também é chamada de chave
    secundária ou de ligação.

Tabela de clientes:

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 21%" />
<col style="width: 14%" />
<col style="width: 36%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr>
<th>ID Cliente</th>
<th>Nome</th>
<th>Telefone</th>
<th>Email</th>
<th>Cidade</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>João Silva</td>
<td>912345678</td>
<td>joao.silva@email.com</td>
<td>Lisboa</td>
</tr>
<tr>
<td>2</td>
<td>Maria Costa</td>
<td>961234567</td>
<td>maria.costa@email.com</td>
<td>Porto</td>
</tr>
<tr>
<td>3</td>
<td>Pedro Oliveira</td>
<td>968901234</td>
<td>pedro.oliveira@email.com</td>
<td>Coimbra</td>
</tr>
</tbody>
</table>

Tabela de vendas:

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 15%" />
<col style="width: 16%" />
<col style="width: 21%" />
</colgroup>
<thead>
<tr>
<th>ID Venda</th>
<th>ID Cliente</th>
<th>Data</th>
<th>Produto</th>
<th>Quantidade</th>
<th>Preço Unitário</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>1</td>
<td>2025-01-15</td>
<td>Produto A</td>
<td>2</td>
<td>50,00</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>2025-01-20</td>
<td>Produto B</td>
<td>1</td>
<td>100,00</td>
</tr>
<tr>
<td>3</td>
<td>1</td>
<td>2025-02-05</td>
<td>Produto C</td>
<td>3</td>
<td>30,00</td>
</tr>
</tbody>
</table>

Tabela de produtos:

<table>
<thead>
<tr>
<th>ID Produto</th>
<th>Nome</th>
<th>Categoria</th>
<th>Preço Base</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Produto A</td>
<td>Eletrónica</td>
<td>50,00</td>
</tr>
<tr>
<td>2</td>
<td>Produto B</td>
<td>Eletrodomésticos</td>
<td>100,00</td>
</tr>
<tr>
<td>3</td>
<td>Produto C</td>
<td>Acessórios</td>
<td>30,00</td>
</tr>
</tbody>
</table>

As tabelas estão ligadas através das chaves primárias e estrangeiras.
Por exemplo, a tabela de vendas usa o ID Cliente como chave estrangeira
para referenciar a tabela de clientes. Isto permite consultas complexas,
como obter todas as vendas de um cliente específico ou calcular o total
de vendas por produto.

## Diagrama Entidade-Relação (ER)

Um Diagrama Entidade-Relação (ER) é uma representação visual das
entidades, atributos e relações numa base de dados. Ele ajuda a
compreender a estrutura da base de dados e a identificar como as
diferentes entidades estão interligadas.

<figure class=''>

<img
src="Introdução_BD_files\figure-markdown_strict\mermaid-figure-1.png"
style="width:6.02in;height:7.01in" />

</figure>

## Violações de Normalização

**Caso 1**: A Lista de Compras na mesma célula Tabela:

<table>
<thead>
<tr>
<th>Cliente</th>
<th>Produtos Comprados</th>
</tr>
</thead>
<tbody>
<tr>
<td>Ana</td>
<td>Pão, Leite, Café</td>
</tr>
</tbody>
</table>

Problema: Violação da 1ª Forma Normal (Atomicidade). Não consigo somar o
preço do “Leite” porque está misturado com o “Pão”. Solução: Transformar
em formato Longo (3 linhas: Ana-Pão, Ana-Leite, Ana-Café).

**Caso 2**: O Fornecedor Repetido Tabela de Produtos:

<table>
<thead>
<tr>
<th>Produto</th>
<th>Fornecedor</th>
<th>Telefone Fornecedor</th>
</tr>
</thead>
<tbody>
<tr>
<td>Martelo</td>
<td>Ferramentas Lda</td>
<td>212…</td>
</tr>
<tr>
<td>Serra</td>
<td>Ferramentas Lda</td>
<td>212…</td>
</tr>
</tbody>
</table>

Problema: Violação da 2ª/3ª Forma Normal. O telefone depende do
Fornecedor, não do Produto. Se eu apagar o Martelo e o Serrote, perco o
telefone do fornecedor (Anomalia de Eliminação). Solução: Criar tabela
separada de Fornecedores.

## **Exercício**:

Desenhar o esquema completo para uma empresa que compra a Fornecedores e
vende a Clientes:

    - Tabela Clientes (ID, Dados Qualitativos).

    - Tabela Fornecedores (ID, Dados Qualitativos).

    - Tabela Produtos (ID, Nome, Preço, ID_Fornecedor).

    - Tabela Vendas (ID, Data, ID_Cliente).

    - Tabela Detalhes_Venda (ID_Venda, ID_Produto, Quantidade).

<img
src="Introdução_BD_files\figure-markdown_strict\Logotipo.png"
style="width:6.02in;height:7.01in" />



