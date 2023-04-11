------------
Comandos GIT
------------

Inicializar um repositório

git init
------------------------------------------
Primeira Versão do projeto

touch .gitignore
git add .gitignore
git commit -m "Versão inicial do projeto" 
------------------------------------------
Adicionando novos arquivos

git add README
------------------------------------------
Verificando Status

git status
------------------------------------------
Verificando mudanças

git diff
------------------------------------------
Verifica o que vai subir no próximo commit

git diff --cached
------------------------------------------
Commits

git commit -m "Mensagem Aqui"

git commit -a -m "Mensagem: -a para arquivos sem estar no STAGE"

git commit -m "Mensagem: Refaz commit se esquecer um arquivo pra ir pro stage->" --amend 
------------------------------------------
Desfazendo Commits

Volta ao último commit e mantém os últimos arquivos no stage.
git reset --hard HEAD~1

Volta para o commit com a hash XXXXXXXXXXX:
git reset --hard XXXXXXXXXXX

Recuperando commit apagado pelo git reset
git reflog

E para aplicar
git merge {hash}
------------------------------------------
Removendo arquivos
git rm -f {arquivo}
------------------------------------------
BRANCH e MERGE

Criando uma branch
git branch nomeBranch

Movendo-se entre branchs
git checkout nomeBranch

MERGE Básico
Suponha que você decidiu que o trabalho na tarefa #53 está completo e pronto para ser feito o merge no branch master. Para fazer isso, você fará o merge do seu branch nomeBranch, bem como o merge do branch hotfix de antes. Tudo que você tem a fazer é executar o checkout do branch para onde deseja fazer o merge e então rodar o comando git merge:

git checkout master
git merge nomeBranch

Resolvendo conflitos
Ferramenta visual de merge adequada e percorre os conflitos.
git mergetool
-------------------------------------------
Histórico de Commits

git log
-------------------------------------------
Fazendo Stash

O problema é, você não quer fazer o commit de um trabalho incompleto somente para voltar a ele mais tarde. A resposta para esse problema é o comando git stash.
Você quer mudar de branch, mas não quer fazer o commit do que você ainda está trabalhando; você irá fazer o stash das modificações. Para fazer um novo stash na sua pilha, execute:

git stash

Lista de stash

git stash list

Você pode aplicar aquele que acabou de fazer o stash com o comando mostrado na saída de ajuda do comando stash original: git stash apply. Se você quer aplicar um dos stashes mais antigos, você pode especificá-lo, assim: git stash apply stash@{2}. Se você não especificar um stash, Git assume que é o stash mais recente e tenta aplicá-lo.
--------------------------------------------

Tagging
Listar TAGS
git tag 

Criar uma tag, caso não queira criar a tag anotada, somente retire os parâmetros -a e -m.,
git tag -a v1.4 -m 'my version 1.4'
---------------------------------------------
Compartilhar e atualizar projetos

Para pegar dados dos seus projetos remotos, você pode executar:
git fetch origin

Atualizando projeto local
git pull

git pull origin develop

Enviando commits

O git push é o comando em que você transfere commits a partir do seu repositório local para um repositório remoto. É a contrapartida do git fetch, que busca importações e comprometem as agências locais, utilizando o git push as exportações comprometem as filiais remotas. Para fazer isso, você executa git push [nome_do_repositório_remoto] [nome_da_sua_branch_local], que vai tentar fazer que o [nome_do_repositório_remoto] receba a sua branch [nome_da_sua_branch_local] contendo todos seus commits com alterações. Por exemplo:

git push origin develop
