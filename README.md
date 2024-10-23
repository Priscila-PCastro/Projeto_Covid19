# Projeto_Covid19

# Análises Exploratórias e Estatísticas: "caso_full"  registros diários da pandemia da COVID-19

Grupo6: Natalia Camargo, Luciano, Priscila Castro, Raphael Pacheco, Thays Telles e Victor Castro.

## Informações Dataset

### Contextualização

Este notebook utiliza o dataset "caso_full", com dados diários da pandemia de COVID-19 no Brasil, organizados por município. A coleta e o tratamento dos dados foram feitos manualmente por Álvaro Justen e voluntários do projeto Brasil.IO, devido à falta de dados oficiais estruturados e acessíveis durante a crise. Informações sobre casos e mortes, frequentemente incompletas e demoradas, foram extraídas diretamente dos boletins epidemiológicos das Secretarias Estaduais de Saúde. Esse esforço colaborativo envolveu 35 voluntários e resultou em um dataset acessível via API e arquivos CSV, oferecendo uma base sólida para análises.

### Estrutura

| Coluna                                   | Descrição                                                                                                                                                          |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **city**                                 | Nome do município. Pode estar em branco se o registro se refere ao estado ou se for categorizado como "Importados/Indefinidos".                                      |
| **city_ibge_code**                       | Código IBGE do município ou estado correspondente.                                                                                                                 |
| **date**                                 | Data de coleta dos dados no formato YYYY-MM-DD.                                                                                                                    |
| **epidemiological_week**                 | Número da semana epidemiológica, no formato YYYYWW.                                                                                                                |
| **estimated_population**                 | População estimada para o município/estado em 2020, segundo o IBGE.                                                                                                |
| **estimated_population_2019**            | População estimada para o município/estado em 2019, segundo o IBGE. ATENÇÃO: esta coluna é desatualizada. Prefira usar a coluna `estimated_population`.             |
| **is_last**                              | Indica se o registro é o mais recente para aquele local (`True` ou `False`).                                                                                       |
| **is_repeated**                          | Indica se os dados daquele dia foram publicados ou se são repetidos de um boletim anterior.                                                                         |
| **last_available_confirmed**             | Número de casos confirmados até a data especificada.                                                                                                               |
| **last_available_confirmed_per_100k_inhabitants** | Número de casos confirmados por 100.000 habitantes (com base na população estimada).                                                                                |
| **last_available_date**                  | Última data para a qual há dados disponíveis.                                                                                                                      |
| **last_available_death_rate**            | Taxa de mortalidade (número de mortes dividido pelo número de casos confirmados).                                                                                   |
| **last_available_deaths**                | Número total de mortes até a data especificada.                                                                                                                    |
| **order_for_place**                      | Ordem do registro para um local específico, começando em 1 para o primeiro boletim.                                                                                 |
| **place_type**                           | Tipo de local (municipal ou estadual), com valores "city" (município) ou "state" (estado).                                                                          |
| **state**                                | Sigla do estado (exemplo: SP para São Paulo).                                                                                                                      |
| **new_confirmed**                        | Número de novos casos confirmados desde o último dia registrado.                                                                                                   |
| **new_deaths**                           | Número de novos óbitos desde o último dia registrado.                                                                                                              |


### Metodologia de Coleta

Os dados foram coletados manualmente a partir dos boletins epidemiológicos das Secretarias Estaduais de Saúde. Quando um boletim não era divulgado, o dado anterior era replicado, sendo indicado pela coluna `is_repeated`. Esse processo contínuo foi conduzido por voluntários, monitorando casos, mortes, população e outras métricas.


### Diferenças entre Contagens Estaduais e Municipais

As divergências surgem por dois fatores:  

- **Divulgação centralizada por estado**: Algumas Secretarias, como a de São Paulo, pararam de publicar dados por município.  
- **Erros de divulgação**: Informações incorretas pelas Secretarias podem causar discrepâncias.

- ### Comparação com Dados do Ministério da Saúde

Os dados do Brasil.IO podem ser mais recentes, pois a coleta é feita logo após a publicação dos boletins estaduais, enquanto o Ministério da Saúde pode receber informações antes de torná-las públicas.

### Limitações na Cobertura de Municípios

Os registros municipais podem não estar completos para todas as datas, iniciando apenas a partir do primeiro caso confirmado.

### Possíveis Análises

- Evolução temporal da COVID-19 por município  
- Taxa de mortalidade  
- Distribuição espacial dos casos  
- Casos por 100 mil habitantes  
- Comparação entre estados  
- Tendências de novos casos e mortes  
- Impacto populacional  
