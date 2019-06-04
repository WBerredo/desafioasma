# OBAS - Observatório Braseileiro de Asma
Projeto que mostra dados referentes a Asma em todo o Brasil, disponível no link https://wberredo.github.io/desafioasma/. Projeto realizado para o [Desafio Asma](https://desafioasmagsk.inovaeinstein.com.br/).

## Metodologia
O projeto inteiro foi construído utilizando a [Elastic Stack](https://www.elastic.co/pt/products/), utilizando o banco de dados não relacional [Elasticsearch](https://www.elastic.co/pt/products/elasticsearch); recebimento, tratamento e envio de dados pelo [Logstash](https://www.elastic.co/pt/products/logstash) e visualização de dados, gráficos e métricas pelo [Kibana](https://www.elastic.co/pt/products/kibana). A suíte Elastic Stack é free e open-source.

### Logstash
Os dados foram recebidos em formato CSV e foi utilizado o Logstash para receber, tratar e enviar os dados para o banco Elasticsearch.
As configurações utilizadas para tratamento dos dados estão nos arquivos de configuração(*.conf) na raiz do projeto.

### Elasticsearch
O Elasticsearch foi o banco selecionado para receber os dados coletados, sendo necessário apenas fazer um mapeamento prévio dos tipos de dados a serem coletados. Após esse mapeamento, foi possível receber todos os dados enviados pelo Logstash e utilizados pelo Kibana.

### Kibana
O Kibana é o responsável pela agregação e visualização dos dados e métricas. Após serem criados os gráficos e as métricas a serem avaliadas, são feitas pesquisas no banco Elasticsearch para coletar, agregar e mostrar métricas.

Para visualização dos dados da asma, além do filtro padrão por **data**, foram utilizados filtros por **sexo** e **faixa etária**; sempre utilizando a agregração do tipo **soma** para contabilizar o número de casos que ocorreram no período de tempo avaliado.

Para os dados mostrados em mapas, foram utilizadas agregações por localização, nome do estado ou UF, mostrando como valor da métrica a média dos valores encontrados quando se trata de valores relativos, e soma dos valores encontrados se tratando de valores absolutos.

## Dados

Os dados utilizados foram coletados das seguintes fontes:
  * [Painel de Monitoramento da Mortalidade CID-10](http://svs.aids.gov.br/dantps/centrais-de-conteudos/paineis-de-monitoramento/mortalidade/cid10), agregados por data, sexo e idade. Foram utilizados dados de 2007 a 2016.
  
  * [Portal Brasileiro de Dados Abertos: Distribuição Unidades Básicas de Saúde em Funcionamento - UBS](http://dados.gov.br/dataset/ubs_funcionamento). Os dados utilizados são atuais.

  * [Portal da Transparência 2018](http://www.portaltransparencia.gov.br/funcoes/10-saude?ano=2018): Distribuição das despesas com saúde por localidade.

  * [Instituto Nacional de Meteorologia: NORMAIS CLIMATOLÓGICAS DO BRASIL](http://www.inmet.gov.br/portal/index.php?r=clima/normaisClimatologicas). Os dados utilizados são de 1981 a 2010.

  * [DATASUS: Cadastro Nacional de Estabelecimentos de saúde](http://www2.datasus.gov.br/DATASUS/index.php?area=0204&id=6906), dados agregados por região e tipo de estabelecimento. Os dados utilizados são de dezembro de 2018.

  * [Denatran - Frota de Veículos 2018](http://www.denatran.gov.br/estatistica/635-frota-2018). Dados agregados por tipo de veículo e estado.

  * [CNI - Perfil das Indústrias nos estados](http://perfildaindustria.portaldaindustria.com.br/). Dados agregados por estado. Os dados utilizados são de 2018.

## Uso
Para utilizar o observatório, é necessário:
* Acessar o [link](https://wberredo.github.io/desafioasma/);

* Visualizar os dados mostrados;

* Se necessário, para uma melhor visualização e análise, utilizar os filtros disponíveis(apenas clickando nos dados a se visualizar):

  * Por data;
  * Por sexo;
  * Por faixa etária;

* É possível alternar entre os dados de asmas e gráficos com informações complementares.

## Colaboradores
* Wesley Berrêdo
* Robert Burga
* Charles William

