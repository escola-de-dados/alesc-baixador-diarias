# alesc-baixador-diarias
Simples passo-a-passo (macOS ou Linux) para baixar arquivos PDF do portal de transparência da Assembleia Legislativa de Santa Catarina (http://transparencia.alesc.sc.gov.br/diarias.php) desenvolvido pela Escola de Dados e utilizado pelo jornal Diário Catarinense

Os links para os PDFs respeitam uma lógica:

``http://diarias.alesc.sc.gov.br/prestacao-contas/<número de 5 dígitos>``

## 1. Instalar o wget (https://www.gnu.org/software/wget/)

Na maior parte das distribuições GNU/Linux já vem instalado; nas baseadas em Debian (Ubuntu, Mint etc.), basta rodar (caso não esteja instalado):

    sudo apt-get install wget
    

## 2. Digitar na linha de comando:

``for i in {62000..62999}; do wget -c -t 3 -O "$i.pdf" "http://diarias.alesc.sc.gov.br/prestacao-contas/$i"; done``

O comando acima baixa todos os arquivos do número `62000` ao `62999` - você pode alterá-los para baixar outros PDFs desejados - e os salva no diretório corrente (em que o comando foi executado) com o nome `<NUMERO>.pdf`. Caso exista algum erro de conexão, o comando tentará 3 vezes (`-t 3`) e, caso o download tenha sido interrompido, ele continuará de onde parou (`-c`).
