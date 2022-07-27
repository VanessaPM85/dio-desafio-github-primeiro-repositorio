# Repositório do Desafio de Projeto sobre Git/GitHub da DIO
Desafio de Projeto sobre Git/GitHub

### Anotações e dicas do curso
instalar git bash
verificar marcação -> Git Bash Here
                      Git GUI Here
SHA 1 -> criptografa texto, imagens etc em 40 caracteres
echo "ola mundo" | open sha1 > (stdin) = f9fc856e559...
Blobs -> bolhas, contém metadados e quando ccriptografamos, gera um código diferente do sha1 pois acrescenta o tamanho do arquivo, \0, blob. Exemplo:
  echo 'conteudo' | git hash-object -- stdin 
  > fc 31e91b26cf85a55...
  echo -e 'conteudo' | openssl sha1
  > 65bododda479cc03cc... -> percebe que gerou um código diferente pois o comando da linha 11 também é o comando sha mas levando em consideeração ps objetos como o blob. Para o comando sha levar em consideração os metadados, basta fazer assim:
eho -e 'blob' 9\oconteudo | openssl sha1
>fc31e91b26cf85a55eo724...
Ou seja, usar blob junto com o comando echo + 9 (tamanho arquivo) + \o
Tree -> árvores, armazenam blobs
Blobs não armazenam o nome do arquivo já as árvores sim
----------------------------------
-     Tree          <tamanho>    -
-                                -
-                                -
-  \o                            -
-                                -
-  blob     sa4d8s    texto.txt  -
----------------------------------

