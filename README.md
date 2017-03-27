# alesc-baixador-diarias
Simples passo-a-passo (macOS ou Linux) para baixar arquivos PDF do portal de transparência da Assembleia Legislativa de Santa Catarina (http://transparencia.alesc.sc.gov.br/diarias.php) desenvolvido pela Escola de Dados e utilizado pelo jornal Diário Catarinense

Os links para os PDFs respeitam uma lógica:

``http://diarias.alesc.sc.gov.br/prestacao-contas/<número de 5 dígitos>``

## 1. Instalar o wget (https://www.gnu.org/software/wget/)

## 2. Digitar na linha de comando:

``for i in {62000..62999} do wget http://diarias.alesc.sc.gov.br/prestacao-contas/$i done``

O comando acima baixa todos os arquivos do número 62000 até o 62999... eles podem ser alterados para baixar quaisquer números. 

## 3. Renomear os arquivos PDF usando o bash

Primeiro apagar aqueles que forem menor que 71kb. Em seguida, no *bash*, digitar:

``for f in *; do mv "$f" "$f.pdf"; done``
