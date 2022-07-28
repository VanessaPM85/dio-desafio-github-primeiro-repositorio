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
Tree -> <tamanho> 
        \o 
        blob 
        sa4d8s 
        texto.txt
Commit -> é o mais completo, apontando a tree, blobs e outros commits antes dele. Junta tudo.
          tree
          parente
          autor
          mensagem
          timestamp
          <tamanho>
          s4a5sq1
          a98acq1
          perkles
          "inicia..."
Para gerar chave pública e privada que são usadas para o reconhecimeneto da minha máquina, além do login e senha, chaves SSH e GPG, digitar no git bash:
ssh-keygen -t ed25519 -c medeirospondian@gmail.com
Não deu certo o código acima então digitei apenas:
ssh-keygen
Para achar a pasta com a chave SSH -> cd /c/User/caminho...
Listar o que tem dentro da pasta -> ls
A chave que tem pub na frente é a pública que vai para o github
Para mostra o conteúdo do documento -> cat id_rsa.pub
Completar comando -> tab
Caminho completo de onde vc se encontra -> pwd
Para criar Token no github clicar na minha foto de perfil que se encontra no canto superior na direita e depois em Settings, em seguida Developer settings, Personal acess tokens, Generate new token, dar um nome, 60 dias para expirar, selecionar repo
Para abrir o git direto na pasta ou diretório que deseja, basta abrir a paasta desejada, então iniciar o git com a aba da pasta aberta, clicando com o botão direito do mouse em um espaço em branco, clicar em mostrar mais opções e depois em git bash here. Observe que o git vai inicializar já no diretório
Limpar a tela -> Ctrl + l
Criar pasta -> mkdir
O git fica oculto dentro da pasta, sendo nececessário o comando ls -a para ser mostrado
cd... -> voltar na pasta anterior
