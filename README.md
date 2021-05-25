# Estrutura de Aqruivos e Pastas

```
|__ README.md                        <- apresentação do projeto
│__ README_datasets.md               <- informações referentes aos dados utilizados no projeto
|
├── notebooks                        <- Jupyter notebooks
│   |__centralizando_bases.ipynb
|
└── assets                            <- mídias usadas e/ou produzidas no projeto
    |__ pitch.mov                     <- vídeo de apresentação inicial do projeto
    |__ cronograma_v2.png             <- cronograma inicial do projeto
```

# Projeto `Analisando parâmetros multidimensionais: como direcionar o foco na vacinação prioritária de populações-chave`

# Project `Multi Dimensional parameters analysis: how to direct the focus on priority vaccination of key-population`

# Apresentação

O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [Ciência e Visualização de Dados em Saúde](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

| Nome  | RA | Especialização |
| :---: | :-: | :-----------: |
| Andreza Aparecida dos Santos | 164213  | Computação |
| Leonardo Marçal  | 225240 | Computação |
| Lígia Vasconcellos  | 081938 | Estatística |
| Mariana Amaral Raposo  | 262866 | Saúde |

# Descrição Resumida do Projeto

O coronavírus 2019 (COVID-19) é causado por um novo coronavírus conhecido como síndrome respiratória aguda grave coronavírus 2 (SARS-CoV-2). A rápida disseminação desse patógeno e o número crescente de casos e óbitos têm levado vários países ao colapso sanitário, hospitalar e econômico.
O Brasil viveu em março de 2021 o mês mais mortal da pandemia de COVID-19, com 66 mil óbitos registrados e a saturação dos sistemas de saúde públicos e privados. O que destaca a necessidade urgente de medidas efetivas de controle da doença como forma de evitar o avanço descontrolado e a incidência de novos picos.

Estudos de eficácia (ZHANG et al., 2021; WU et al., 2021) confirmam o impacto que elas teriam caso aplicadas em massa na população, trazendo uma queda nos índices de mortalidade da doença e, consequentemente, reduzindo as taxas de ocupação dos hospitais, enfatizando sua importância. Atualmente, a campanha de vacinação utilizada segue os moldes determinados pelo PLANO NACIONAL DE OPERACIONALIZAÇÃO DA VACINAÇÃO CONTRA A COVID-19 (Ministério da Saúde, 2021), estudo que analisou os perfis dos casos hospitalizados ou óbitos por Síndrome Aguda Grave (SRAG) por COVID-19 no Brasil até Setembro de 2020. Desta análise, identificou-se que o grupo de maior risco para hospitalização e óbito encontra-se na faixa etária a partir de 45 anos, além de outros grupos mais vulneráveis. Definiu-se, então, o esquema de vacinação da população iniciando-se nesses grupos onde temos os idosos, povos indígenas, profissionais de saúde e de serviços essenciais. Entretanto, por ser um país de dimensões continentais e detentor de grandes diferenças econômicas e populacionais entre suas regiões, a cada dia verificamos mais desafios na produção e acesso total da população à vacinação.

Neste sentido e considerando a necessidade iminente de medidas mais efetivas de minimização da crise sanitária e econômica atual, o presente projeto tem o intuito de analisar parâmetros multidimensionais relacionados ao COVID-19 em cada região do Brasil, buscando por relações nos dados que possam ser capazes de fornecer uma melhor análise estatística das regiões e levantar possíveis planos de vacinação que impactem mais rapidamente no controle da pandemia.

O poder da vacinação em grupos e regiões prioritárias que mais são afetadas pelas crises sanitárias e econômicas poderão auxiliar na redução da taxa de mortalidade e no equilíbrio do sistema de saúde.

O video disponível neste [link](./assets/pitch.mov) trás a apresentação da proposta.

# Perguntas de Pesquisa

* De acordo com parâmetros multidimensionais correlacionados ao COVID-19, quais regiões e públicos-alvo deveriam ser priorizados na campanha de vacinação visando minimizar o efeito da crise sanitária e econômica?

> Perguntas de pesquisa (revisadas e atualizadas) que o projeto pretende responder ou hipóteses a serem avaliadas, enunciadas de maneira objetiva e verificável. 
> Se a análise exploratória contribuiu para as perguntas de pesquisa, apresente aqui elementos de análise exploratória que ajudem a responder a questão.


# Metodologia

Este trabalho tem como finalidade a realização de um estudo com o objetivo de compreender a potencial influência da vacinação aplicada prioritariamente a perfis em condições mais propensas a mortalidade, considerando não apenas como critério a idade do indivíduo a ser imunizado. Para isso, inicialmente será realizada uma análise de dados estatística exploratória correlacionando todas as variáveis encontradas provenientes de múltiplas origens de bases de dados. Esta primeira exploração possibilitará identificar relações de causa e efeito e características do meio em que o indivíduo está inserido, tais como PIB, disponibilidade de leitos, médicos e materiais hospitalares, bem como características sociodemográficas: idade, condições de saúde, gênero, etc.

Após a fase inicial em que teremos um panorama da situação do COVID no Brasil, passaremos a estudar o ponto mais específico do estudo: quais são os perfis de indivíduos que deveriam ser priorizados na vacinação? Para tal, construiremos uma base cuja unidade de análise será indivíduos contaminados ou com suspeita de covid e todas as suas características específicas. A esta base será atribuído um target: morte ou não devido ao covid.

Através desta base, serão aplicados múltiplas técnicas de algoritmos supervisionados, tais como regressão logística, random forest, árvore de decisão, SVM e redes neurais. Ao final destes testes de algoritmos, também se fará necessária a aplicação de um método de clusterização para identificação de perfis similares que poderiam ser utilizados como “grupos de prioridade”.

## Bases de Dados e Evolução

Com o objetivo de obter uma base com variáveis que permitam a resposta da pergunta principal do projeto, concluiu-se que seria necessária que esta base tenha informações a nível de indivíduo. Isso quer dizer que, para cada indivíduo infectado, precisamos obter informações relavantes quanto ao seus estado de saúde como resultados de exames de sangue e outros exames efetuados, mas também informações macro sobre a região e contexto social as quais estaria inserido. Tendo em mãos estas informações, teoricamente pode-se testar técnicas de clusterização dos indivíduos com características comuns para que depois essas informações sejam utilizadas por algoritmos supervisionados com o objetivo de determinar quais conjuntos de características correspondem a maiores taxas de letalidade dentre os infectados por COVID-19.

### Bases Estudadas mas Não Adotadas

| Base de Dados  | Endereço na Web | Resumo descritivo |
| :------------: | :-------------: | :---------------: |
| 1. owid-covid-data.csv | https://github.com/owid/covid-19-data/tree/master/public/data  | Base com informações sobre o avanço da doença COVID-19 a nível de  país. |
| 2. Coronavirus (COVID-19) - Brazil Dataset | https://www.kaggle.com/unanimad/corona-virus-brazil | Base com informações sobre o avanço da doença COVID-19 a nível de país, estado e cidade.  |

#### 1. OWID Coronavirus-data

Esta base de dados é composta por arquivos que possuem informações referentes a números relacionadas a COVID-19 por país, como números de casos, mortes, recuperados, quantidade de vacinados, dados gerais da população, entre outros (dados desde 26.02.2020 ate 06.04.2021). A base apresenta as seguintes variáveis:

> iso_code, continent, location, date, weekly_hosp_admissions_per_million, new_cases, new_cases_smoothed, total_deaths, new_deaths, new_deaths_smoothed, total_cases_per_million, new_cases_per_million, new_cases_smoothed_per_million, total_deaths_per_million, new_deaths_per_million, new_deaths_smoothed_per_million, reproduction_rate,icu_patients, icu_patients_per_million, hosp_patients, hosp_patients_per_million, weekly_icu_admissions, weekly_icu_admissions_per_million, weekly_hosp_admissions, total_cases, new_tests, total_tests, total_tests_per_thousand, new_tests_per_thousand, new_tests_smoothed, new_tests_smoothed_per_thousand, positive_rate, tests_per_case, tests_units, total_vaccinations, people_vaccinated, people_fully_vaccinated, new_vaccinations, new_vaccinations_smoothed, people_vaccinated_per_hundred, people_fully_vaccinated_per_hundred, new_vaccinations_smoothed_per_million, stringency_index, population, population_density,  median_age, aged_65_older, aged_70_older, gdp_per_capita, extreme_poverty, cardiovasc_death_rate, diabetes_prevalence, female_smokers, male_smokers, handwashing_facilities, hospital_beds_per_thousand, life_expectancy, human_development_index

Essa base possui bastante informação relevante para o estudo proposto, entretanto as informações estão a nível de continente, ou seja, cada variável representa o somatório correspondente a território nacional. Como o objetivo dessa etapa do projeto é encontrar variáveis que possam ser utilizadas em algoritmos supervisionados para tentar determinar perfis de indivíduos que deveriam ser priorizados na atual etapa de vacinação contra COVID-19, concluiu-se que esta base a nível nacional não seria utilizada para os fins desse projeto.


#### 2. Coronavirus (COVID-19) - Brazil Dataset

Esta base de dados está organizada em 5 arquivos .csv. Estes arquivos possuem dados organizados como séries temporais (dados acumulativos) e possuem informações referentes aos números de casos, mortes e recuperados da Covid-19 por estado do Brasil. Discriminamos cada arquivo um a seguir:

1. **brazil_cities_coordinates.csv**: este arquivo contém as variáveis `state_code, city_code, city_name, lat, long e capital`. Estas variáveis com dados geográficos foram avaliadas como não necessárias para os fins do trablaho. Portanto este arquivo não será utilizado no projeto.
2. **brazil_covid19.csv**: este arquivo contém as variáveis `data, region, state, cases e deaths`. Nessa base temos as informaçõe de casos e mortes por COVID-19 apresentadas como um somatório por estado. Como explicado anteriormente para a base OWID Coronavirus-data, não conseguimos utilizar essas variáveis como entrada para nossos algoritmos supervisionados para realizar predições por indivíduos. Portanto este arquivo não será utilizado no projeto.
3. **brazil_covid19_cities.csv**: este arquivo possui as variáveis `date, state, name, code, cases e deaths`. Nessa base temos as informações apresentadas como um somatório por estado e cidade. Pelo mesmo motivo explicado anteriormente, este arquivo não será utilizado no projeto.
4. **brazil_covid19_macro.csv**: este arquivo possui as variáveis `date, country, week, cases, deaths, recovered e monitoring`. Nessa base temos as informações apresentadas como um somatório do país. Pelo mesmo motivo explicado anteriormente, este arquivo não será utilizado no projeto.
5. **brazil_population_2019.csv**: este arquivo possui as variáveis `region, state, city, state_code, city_code, health_region_code, health_region e population`. Após avaliação desse arquivo, chegamos a conclusão de que a única variável útil para os finsd o projeto seria a `population`, entretanto esse dado já está presente em outra base que será utilizada. Portanto este arquivo não será utilizado no projeto.


### Bases Estudadas e Adotadas

Para as bases adotadas neste projeto, realizamos um centralização dos dados em um único arquivo para que as análises das variáveis em relação a nossa variável de resposta pudesse ser feita de forma mais direta. Foram centralizadas as seguintes bases:

| Base de Dados  | Endereço na Web | Resumo descritivo |
| :------------: | :-------------: | :---------------: |
| 1. INFLUD-05-04-2021.csv | https://covid.saude.gov.br/  | Base com informações por indivíduos contaminados com COVID-19. |
| 2. esus-vepi.LeitoOcupacao_28_04_2021.csv  | https://opendatasus.saude.gov.br/dataset/registro-de-ocupacao-hospitalar/resource/f9391f7c-9775-4fac-a3ce-bf384e2674c2?view_id=04f2877a-2ea0-4b59-b630-5c530d8db3f2 | Base com informações de disponibilidade de leitos de UTI e Clínicos.  |
| 3. agencia_ibge_noticias_.xlsx | https://agenciadenoticias.ibge.gov.br/agencia-detalhe-de-midia.html?view=mediaibge&catid=2103&id=3702 | Base com informações sobre disponibilidade de respiradores, leitos, profissionais médicos e enfermeiros. |
| 4. ibge_PIB_tabelas_completas.xlsx |   | Base com informações de distribuição do PIB pelo território naciaonal. |
| 5. ibge_trabalhadores_informais.xlsx  |   | Base com informações sobre quantidade de trabalhadores informais por município e estado. |

#### Integração entre Bases 

Devido a nossa enorme quantidade de dados, o processo de integração entre as bases precisou ser feito em duas etapas: (1) integração das bases 2,3,4 e 5, de tamanhos menores em relação a base 1, entre si. (2) integração da base resultante de (2) na base 1.

A primeira integração foi feita utilizando-se como chaves referentes as informações de UF e Município das bases 3, 4 e 5 para gerarmos um arquivo único com todas as informações. Após essa etapa, utilizamos as chaves referentes ao UF, Município e Data de Notificação presentes na base 2 para centralizar todas as variáveis. Após essa etapa, partimos para a integração com a base 1. Tivemos um grande desafio inicial para centralizar estas duas bases, devido ao tamanho e alto custo operacional, que consumiu bastante tempo do projeto em busca de maneiras de processar essa quantidade de dados.

Ao final da centralização, obtivemos um banco de dados de 1.189.743 linhas e 194 colunas. Para facilitar os futuros processamentos e reduzir o custo de memória, simplificamos os dados redundantes, a exemplo de códigos que representam os municípios, nomes e códigos de hospitais e outros, de modo que ao final permaneceram 159 colunas no banco de dados.


#### Análise Exploratória

Devido ao tamanho final da base de dados e da análise exploratória dos dados ser muito extensa, optamos por fornacê-la através deste [arquivo separado](./assets/analise_exploratoria.pdf) disponível no repositório.


# Ferramentas

Com base na visão atual do grupo sobre o projeto, acreditamos que as ferramentas utilizadas serão o python e algumas bibliotecas consagradas para machine learning e análise de dados: Sklearn, Tensorflow, Pandas e etc. Como insumo, utilizaremos múltiplas fontes públicas de informações sobre dados de covid e informações sociodemográficas dos brasileiros.


# Cronograma
![Cronograma de entregas](./assets/cronograma_v2.png)

# Referências

* ZHANG, Yanjun et al. Safety, tolerability, and immunogenicity of an inactivated SARS-CoV-2 vaccine in healthy adults aged 18–59 years: a randomised, double-blind, placebo-controlled, phase 1/2 clinical trial. The Lancet Infectious Diseases, [S.L.], v. 21, n. 2, p. 181-192, fev. 2021. Elsevier BV. http://dx.doi.org/10.1016/s1473-3099(20)30843-4
* WU, Zhiwei et al. Safety, tolerability, and immunogenicity of an inactivated SARS-CoV-2 vaccine (CoronaVac) in healthy adults aged 60 years and older: a randomised, double-blind, placebo-controlled, phase 1/2 clinical trial. The Lancet Infectious Diseases, [S.L.], v. [], n. [], p. 1-8, 3 fev. 2021. Elsevier BV. http://dx.doi.org/10.1016/s1473-3099(20)30987-7. Disponível em: https://www.thelancet.com/journals/laninf/article/PIIS1473-3099(20)30987-7/fulltext. Acesso em: 06 abr. 2021.
* Ministério da Saúde, 2021. PLANO NACIONAL DE OPERACIONALIZAÇÃO DA VACINAÇÃO CONTRA A COVID-19. Disponível em: https://www.gov.br/saude/pt-br/media/pdf/2021/janeiro/29/planovacinacaocovid_v2_29jan21_nucom.pdf . Acessado em: 12/04/2021
