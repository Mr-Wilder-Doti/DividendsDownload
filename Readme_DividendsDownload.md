Descrição
Este script Python carrega uma lista de ativos de uma planilha do Excel, consulta dados de dividendos históricos para cada ativo usando a biblioteca yfinance, e cria uma tabela de dividendos por ativo. A tabela é então exportada para um arquivo CSV.

Funcionalidades
Carrega ativos: Lê uma lista de códigos de ativos de um arquivo Excel.
Determina o ativo mais antigo: Identifica o ativo com a data mais antiga de distribuição de dividendos.
Obtém dividendos históricos: Coleta dados históricos de dividendos para cada ativo.
Cria uma tabela de dividendos: Consolida os dividendos por ano e por ativo.
Exporta para CSV: Salva a tabela de dividendos em um arquivo CSV.

Pré-requisitos
Certifique-se de que você tem as seguintes bibliotecas instaladas:
pandas
yfinance
datetime
dateutil
Você pode instalar as bibliotecas necessárias usando o pip:
bash
Copy code
pip install pandas yfinance

Como Usar
Preparar o Arquivo Excel:
Certifique-se de que o arquivo Excel (ativos_lista.xlsx) está no caminho especificado.
O arquivo deve ter uma coluna chamada "Código" com os códigos dos ativos.
Atualizar o Caminho do Arquivo:
Verifique o caminho do arquivo Excel na variável path. Atualize-o se necessário:
python
Copy code
path = r"C:\Users\dotiw\Documents\UFMG\OneDrive\.vscode\cli\DividendsDownload\ativos_lista.xlsx"
Executar o Script:
Execute o script Python. Ele carregará a lista de ativos, buscará os dados de dividendos e criará o arquivo tabela_dividendos_por_ativo.csv.
bash
Copy code
python nome_do_script.py

Explicação do Código
Carregando Ativos:
Lê os códigos dos ativos da planilha Excel e os armazena em uma lista.
Inicializando Variáveis:
Define ativo_mais_antigo e data_dividendo_atual. data_dividendo_atual é a data e hora atuais sem fuso horário.
Iterando Sobre os Ativos:
Para cada ativo na lista, usa yfinance para obter o histórico de dividendos.
Identifica a data mais antiga de dividendos para cada ativo e atualiza data_dividendo_mais_antigo e ativo_mais_antigo.
Criando a Tabela de Dividendos:
Cria um DataFrame vazio e obtém os anos de referência.
Para cada ativo, obtém o histórico de dividendos, agrega os dividendos por ano e preenche os anos ausentes.
Adiciona os dividendos por ano ao DataFrame.
Exportando para CSV:
Salva o DataFrame resultante em um arquivo CSV chamado tabela_dividendos_por_ativo.csv.

Resultados Esperados
tabela_dividendos_por_ativo.csv: Um arquivo CSV contendo os dividendos anuais por ativo.

Problemas Conhecidos
Certifique-se de que a coluna "Código" no arquivo Excel não contém valores ausentes ou inválidos.
O script assume que todos os ativos têm o sufixo .SA para buscar os dados corretos no Yahoo Finance.

Contribuições
Se você encontrar problemas ou tiver sugestões de melhorias, sinta-se à vontade para abrir um problema ou enviar uma solicitação de pull no repositório.

