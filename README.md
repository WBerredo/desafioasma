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

Para visualização, além do filtro padrão por **data**, foram utilizados filtros por **sexo** e **faixa etária**; sempre utilizando a agregração do tipo **soma** para contabilizar o número de casos que ocorreram no período de tempo avaliado.

## Dados
Para este projeto, foram utilizados dados de 2007 a 2016.

Os dados utilizados foram coletados das seguintes fontes:
  * [Painel de Monitoramento da Mortalidade CID-10](http://svs.aids.gov.br/dantps/centrais-de-conteudos/paineis-de-monitoramento/mortalidade/cid10), agregados por data, sexo e idade.
  
  * [Portal da Transparência 2018](http://www.portaltransparencia.gov.br/funcoes/10-saude?ano=2018): Distribuição das despesas com saúde por localidade.

## Uso
Para utilizar o observatório, é necessário:
* Acessar o [link](https://wberredo.github.io/desafioasma/);

* Visualizar os dados mostrados;

* Se necessário, para uma melhor visualização e análise, utilizar os filtros disponíveis(apenas clickando nos dados a se visualizar):

  * Por data;
  * Por sexo;
  * Por faixa etária.

## Colaboradores
* Wesley Berrêdo
* Robert Burga
* Charles William

