# Estratégia de testes de aceitação
------
## Sobre a estratégia
O que é este documento? o que eu encontro nele? como foi dividido? Que tópicos contém? Se possível, inclua links de âncora para navegação neste documento.

Esta documentação possui as seguintes seções:

1. [Abordagem de teste](#abordagem-de-teste)
2. [Entregáveis de teste](#entregaveis-de-teste)
3. [Cenários de teste](#cenarios-de-teste)
4. [Ambiente de Testes](#ambiente-de-testes)
5. [Abordagem para automação de teste](#abordagem-para-automacao-de-teste)
    * [Escolhendo a ferramenta para automatizar testes de UI](#escolhendo-a-ferramenta-para-automatizar-testes-de-ui)
    * [Escolha dos testes que serão automatizados na UI](#ecolha-dos-testes-que-serao-automatizados-na-ui)
6. [Executando os scripts de teste](#executando-os-scripts-de-teste)
7. [Relatório de teste](#relatorio-de-teste)
8. [Dependências](#dependencias)
9. [Relatório de erros](#relatorio-de-erros)
10. [Referências](#referencias)

- - - -
## Abordagem de teste

Como os cenários de teste serão descritos? _(Gherkin, passo a passo, etc)_

Onde encontro casos de teste detalhados? _(Ferramenta de gestão de testes, caminhos no repositório, etc)_

Como os testes foram priorizados? Que critérios foram usados? Quem foram as pessoas envolvidas durante esta priorização?

Quais níveis de teste serão realizados? Quais foram os critérios para esta decisão?

Que tipos de teste não funcionais serão realizados (teste de carga, teste de segurança, teste de desempenho, teste CrossBrowser etc.)? Quais foram os critérios utilizados para esta decisão?


- - - -
## Entregáveis de teste
* Os estregáveis de teste são:
    * Arquivos .feature, contendo a descrição dos cenários e casos de teste no formato Gherkin;
    * Base de código **_[LINGUAGEM DE PROGRAMAÇÃO]_** utilizando o framework **_[FRAMEWORK]_** (Bitbucket, Github, etc);
    * Relatórios **_[FORMATO DO RELATÓRIO]_** localizados em **_[CAMINHO DO RELATÓRIO]_**;
    * Evidências de teste no formato **_[FORMATO]_** localizadas em **_[CAMINHO DAS EVIDÊNCIAS]_**;
    * Scripts de execução dos testes **_[LINGUAGEM DE SCRIPTS UTILIZADA (MAKE, RAKE, ETC)]_**. A intenção é que os testes sejam passíveis de integração em pipeline.
    * Relatório de defeitos que será descrito na ferramenta **_[FERRAMENTA DE GESTÃO DE DEFEITOS]_**. [Link para acessar a ferramenta aqui.](https://www.google.com)

- - - -
## Cenários de teste

Os cenários de teste foram modelados com base nas seguintes técnicas:
* Particionamento de equivalência
* Análise de valor limite
* Tabela de Decisão
* Teste de transição de estado

### Lista de cenários de teste:
|        ID          |                               Descrição                                            |  Técnica |
|   :-------------:  |                             --------------                                           | --------- |
|      [CT-001]      | Verifique o comportamento do sistema quando um e-mail e uma senha **válidos** forem inseridos.|     |
|      [CT-002]      | Verifique o comportamento do sistema quando um email **inválido** e uma senha **válida** forem inseridos.|     |
|      [CT-003]      | Verifique o comportamento do sistema quando o email **inválido** e a senha **inválida** forem inseridos. |     |
|      [CT-004]      | Verifique o comportamento do sistema quando o e-mail e a senha forem deixados em branco. |     |
|      [CT-005]      | Verifique se _**Esqueceu sua senha**_ está funcionando como esperado.                                   |     |

- - - -
## Ambiente de Testes
Abaixo estão todas as ferramentas/plataformas usadas durante o desenvolvimento da estratégia de teste e do código de teste automatizado:

|        Item        |        Descrição        |        Versão        |        Nota        | 
|       :----:       |        -----------        |       :-------:       |        ----        | 
| IntelliJ IDEA      |           IDE             |        Última disponível           |         N/A        |
| Google Chrome      | Testes de navegador           |       87.0.4280.88    |         N/A        |
|    Pa11y           | Ferramenta de automação de teste de acessibilidade |  5.0.0    |         N/A        |
| GitHub             | Repositório de código e documentação |   N/A         |         N/A        |
| Ferramenta/Plataforma   | Descrição               |        Última disponível            |         N/A        |
| Ferramenta/Plataforma   | Descrição               |        Última disponível            |         N/A        |

- - - -
## Abordagem para automação de teste

### Escolhendo a ferramenta para automatizar testes de UI

A ferramenta de automação foi escolhida com base nos seguintes critérios:

**!!! APAGAR CRITÉRIOS QUE NÃO SE APLICAM E DEIXAR SOMENTE OS QUE FORAM REALMENTE UTILIZADOS !!!**

* **Facilidade de desenvolver e manter os scripts:** O desenvolvimento e a manutenção dos scripts de teste devem ser o mais simples possível para diminuir a utilização de recursos humanos e de tempo.
* **Facilidade de execução de testes para usuários não técnicos:** A execução do conjunto de testes deve ser simples para qualquer membro do projeto para executá-los facilmente como e quando necessário. Além disso, deve ser fácil para testadores manuais com muito pouco ou nenhum conhecimento técnico.
* **Suporte para aplicativos da Web, Desktop e Mobile:** Aproveitar 3 ferramentas diferentes para 3 tipos de plataformas para automação de teste é uma tarefa complicada de lidar. É melhor selecionar uma ferramenta que suporte todas as três plataformas.
* **Relatório de teste intuitivo:** Os relatórios de teste aumentam a confiança e, portanto, os relatórios precisam ser intuitivos e simples para que a equipe de gerenciamento os compreenda facilmente.
* **Teste entre navegadores:** O suporte ao teste entre navegadores é obrigatório quando há vários usuários finais e nenhuma restrição específica do navegador.
* **Suporte para teste orientado por palavras-chave e dados:** O teste orientado por palavras-chave atua como uma extensão da estrutura de teste orientado por dados. Quando um projeto se torna complexo, a estrutura de teste precisa ser estendida.
* **Suporte e assistência técnica:** Os engenheiros de automação definitivamente precisam de ajuda ao lidar com problemas críticos de um projeto. A ferramenta que fornece suporte técnico e assistência seria de grande ajuda.
* **Suporte de linguagem como C #, Java, Python e outros:** Todos os cenários de teste não podem ser registrados. Em alguns casos, o testador deve escrever o código. Portanto, a ferramenta que oferece suporte ao idioma necessário para escrever os scripts personalizados seria útil.
* **Integração TFS DevOps com compilações:** Suporte para integração com ferramentas de integração contínua para compilações e implantações automatizadas é necessário.
* **Preço:** Dependendo das qualidades acima e das estimativas de custo do projeto, avalie a diferença de custo entre as outras ferramentas de automação disponíveis.

### Escolha dos testes que serão automatizados na UI
Abaixo, os critérios que foram usados para decidir quais testes são bons candidatos para automação:

**!!!!!!! APAGAR CRITÉRIOS QUE NÃO SE APLICAM E DEIXAR SOMENTE OS QUE FORAM REALMENTE UTILIZADOS !!!!!**

_Como você escolhe quais testes automatizar e quais testes deixar para o teste manual?_

**Testes que devem ser automatizados:**
* Caminhos críticos para os negócios - os recursos ou fluxos de usuários que, se falharem, causam danos consideráveis ​​aos negócios.
* Testes que precisam ser executados em cada build / lançamento do aplicativo, como teste de fumaça, teste de sanidade e teste de regressão.
* Testes que precisam ser executados em várias configurações - diferentes combinações de sistema operacional e navegador.
* Testes que executam o mesmo fluxo de trabalho, mas usam dados diferentes para suas entradas para cada execução de teste, por exemplo, orientado por dados.
* Testes que envolvem a entrada de grandes volumes de dados, como o preenchimento de formulários muito longos.
* Testes que podem ser usados ​​para testes de desempenho, como testes de estresse e carga.
* Testes que demoram muito para serem realizados e podem precisar ser executados durante os intervalos ou durante a noite.
* Testes durante os quais as imagens devem ser capturadas para provar que o aplicativo se comportou conforme o esperado ou para verificar se uma infinidade de páginas da web tem a mesma aparência em vários navegadores.
* De modo geral, quanto mais repetitivo o teste, melhor para a automação.

**Testes que não devem ser automatizados:**
* Testes que você executará apenas uma vez. A única exceção a esta regra é que se você deseja executar um teste com um conjunto muito grande de dados, mesmo que seja apenas uma vez, faz sentido automatizá-lo.
* Testes de experiência do usuário para usabilidade (testes que exigem que o usuário responda sobre a facilidade de uso do aplicativo).
* Testes que precisam ser executados o mais rápido possível. Normalmente, um novo recurso que é desenvolvido requer um feedback rápido, portanto, testando-o manualmente no início
* Testes que requerem teste ad hoc / aleatório com base no conhecimento / experiência do domínio - Teste Exploratório.
* Testes intermitentes. Testes sem resultados previsíveis causam mais ruído desse valor. Para obter o melhor valor da automação, os testes devem produzir resultados previsíveis e confiáveis ​​para produzir condições de aprovação e reprovação.
* Testes que requerem confirmação visual, no entanto, podemos capturar imagens da página durante o teste automatizado e, em seguida, fazer uma verificação manual das imagens.
* Testes que não podem ser 100% automatizados não devem ser automatizados de forma alguma, a menos que isso economize uma quantidade considerável de tempo.

### Lista de cenários que foram automatizados com base em critérios estabelecidos
* CT-001 - Verifique o comportamento do sistema quando a id de e-mail e a senha **válidas** forem inseridas.
* CT-002 - Verifique o comportamento do sistema quando um id de e-mail **inválido** e uma senha **válida** forem inseridos.
* CT-003 - Verifique o comportamento do sistema quando um id de email **inválido** e uma senha **inválida** forem inseridos.
* CT-004 - Verifique o comportamento do sistema quando a id de e-mail e a senha forem deixadas em branco e o Login for inserido.
* CT-005 - Verifique se **_Esqueceu sua senha_** está funcionando como esperado.

- - - -
## Executando os scripts de teste
* Os seguintes scripts fazem, respectivamente:

| Descrição		| 	Comando   |
|	----------		|	:-------------:	|
| Instala as dependências necessárias para o projeto	 |   `make setup` | 
| Executas os testes automatizados no navegador **Chrome** |     `make e2e_tests_on_chrome`    |
| Executas os testes automatizados no navegador **Firefox** |  `make e2e_tests_on_firefox` |
| Executas os testes automatizados no navegador **Safari** |  `make e2e_tests_on_safari` |

- - - -
## Relatório de teste
* Abaixo está uma imagem do relatório de execução do teste:

 ![](README/report_screenshot.png)

- - - -
## Dependências
As dependências usadas no projeto de automação de testes funcionais são:

| Dependência		| 	Versão   |
|----------		|   :-------------:	|
| Dependência1 		|   `2.7.0` 	| 
| Dependência2 	|     `3.1.2`    	|
| Dependência3 	|     `3.32.1`    	|
| Dependência4 	|     `3.4.2`    	|
| Dependência5 	|     `3.142.7`    	|

- - - -
## Relatório de erros

* **Id do bug:** [001]
* **Gravidade:** Alta
* **Prioridade:** Alta
* **Relatado por:** eu
* **Relatado em:** 01/10/2021
* **Status:** Novo
* **Ambiente:** Safari
* **Descrição:** Descreva aqui um breve resumo do problema.
* **Passos para reproduzir o problema:** Descreva aqui a sequência de passos necessários para reproduzir o problema:
1. Etapa 1
2. Etapa 2
3. Etapa 3
4. Etapa N
	* **Resultado obtido:** Através das etapas descritas acima, o que deveria ter acontecido? Como o sistema realmente se comportou? Qual é a evidência para este mau funcionamento? Adicione capturas de tela, vídeos, logs ... E tudo o mais que possa fornecer informações sobre o estado incorreto atual do sistema.
	* **Resultado Esperado:** Através das etapas descritas acima, o que deve acontecer? Qual comportamento o sistema deve se comportar? Coloque aqui evidências que justifiquem isso (Texto da documentação que você utilizou para chegar a esta conclusão).


* **Id do bug:** [002]
* **Gravidade:** Alta
* **Prioridade:** Alta
* **Relatado por:** eu
* **Relatado em:** 01/10/2021
* **Status:** Fixo
* **Ambiente:** Chrome
* **Descrição:** Descreva aqui um breve resumo do problema.
* **Passos para reproduzir o problema:** Descreva aqui a sequência de passos necessários para reproduzir o problema:
1. Etapa 1
2. Etapa 2
3. Etapa 3
4. Etapa N
	* **Resultado obtido:** Através das etapas descritas acima, o que deveria ter acontecido? Como o sistema realmente se comportou? Qual é a evidência para este mau funcionamento? Adicione capturas de tela, vídeos, logs ... E tudo o mais que possa fornecer informações sobre o estado incorreto atual do sistema.
	* **Resultado Esperado:** Através das etapas descritas acima, o que deve acontecer? Qual comportamento o sistema deve se comportar? Coloque aqui evidências que justifiquem isso (Texto da documentação que você utilizou para chegar a esta conclusão).
- - - -
## Referências
Links importantes que apoiaram o desenvolvimento desta estratégia de teste:

* [Faça um README](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fwww.makeareadme.com%2F)
* [Como criar um documento de estratégia de teste (modelo de amostra)](https://translate.google.com/translate?sl=en&tl=pt&u=https://www.guru99.com/how-to-create-test-strategy-document.html)
* [Como Escrever Um Documento De Estratégia De Teste (Com Modelo De Estratégia De Teste De Amostra)](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fwww.softwaretestinghelp.com%2Fwriting-test-strategy-document-template%2F)
* [Editor de Markdown Online - Dillinger, o Último Editor de Markdown de todos os tempos](https://dillinger.io/)
* [O que é cenário de teste? Modelo com exemplos](https://translate.google.com/translate?sl=en&tl=pt&u=https://www.guru99.com/test-scenario.html)
* [Análise de valor limite e teste de particionamento de equivalência](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fwww.guru99.com%2Fequivalence-partitioning-boundary-value-analysis.html)
* [Teste da Tabela de Decisão: Aprenda com Exemplos](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fwww.guru99.com%2Fdecision-table-testing.html)
* [O que é teste de transição de estado? Diagrama, Técnica, Exemplo](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fwww.guru99.com%2Fstate-transition-testing.html%231)
* [Como escolher qual teste automatizar?](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fdevqa.io%2Fchoose-tests-automate%2F)
* [4 etapas simples para selecionar a ferramenta certa de automação de teste para o seu projeto](https://translate.google.com/translate?hl=&sl=en&tl=pt&u=https%3A%2F%2Fwww.saviantconsulting.com%2Fblog%2F4-steps-select-test-automation-tool.aspx)
* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Este template - English Version](https://github.com/knludi/testing-strategy-template)




