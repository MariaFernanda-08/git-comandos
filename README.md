# 🧩 Aula Prática – Git Local (sem GitHub)

## 🎯 Objetivo
Aprender a utilizar o **Git** localmente para versionar projetos, criando commits, branches e manipulando o histórico de forma segura.

---

## 🧱 1. Configuração inicial

Esses comandos configuram o nome e o e-mail do usuário (necessário para registrar os commits).

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
git config --global core.editor "code --wait"   # Define o VS Code como editor padrão (opcional)
git config --list                                # Verifica as configurações atuais
```

---

## 📂 2. Criar e iniciar um repositório

```bash
mkdir meu_projeto
cd meu_projeto
git init
```

> O comando `git init` cria um repositório local, gerando a pasta oculta `.git`.

---

## 🏷️ 3. Alterar a branch padrão de `master` para `main`

Por padrão, o Git pode criar a branch inicial como **master**.  
Para padronizar e seguir boas práticas, altere para **main**:

```bash
git branch -m master main
```

Se quiser definir **main** como padrão para novos repositórios:

```bash
git config --global init.defaultBranch main
```

---

## 📄 4. Criar arquivos e verificar status

```bash
echo "Meu primeiro arquivo" > readme.txt
git status
```

> `git status` mostra arquivos novos, modificados ou prontos para commit.

---

## 🧺 5. Adicionar arquivos à área de staging

```bash
git add readme.txt       # adiciona um arquivo específico
git add .                # adiciona todos os arquivos do diretório
git status
```

> A área de staging é onde os arquivos ficam “preparados” antes do commit.

---

## 💾 6. Fazer o primeiro commit

```bash
git commit -m "Primeiro commit - adiciona readme.txt"
```

> Um commit é o “salvamento” oficial no histórico do repositório.

---

## 🔍 7. Ver histórico e detalhes

```bash
git log
git log --oneline
git show
```

> Use `--oneline` para visualizar um resumo simplificado.

---

## ✏️ 8. Editar arquivos e registrar mudanças

```bash
echo "Adicionando nova linha" >> readme.txt
git status
git diff
git add readme.txt
git commit -m "Atualiza readme.txt com nova linha"
```

> `git diff` mostra as diferenças entre a versão atual e a anterior.

---

## ♻️ 9. Desfazer mudanças

```bash
git restore readme.txt              # descarta mudanças não adicionadas
git restore --staged readme.txt     # remove da área de staging
```

> Ideal para corrigir erros antes de um commit.

---

## 🌿 10. Criar e alternar entre branches

```bash
git branch                         # lista branches
git branch nova_funcionalidade     # cria nova branch
git switch nova_funcionalidade     # muda para ela
```

> Cada branch é uma linha independente de desenvolvimento.

---

## 🧬 11. Fazer commits em outra branch

```bash
echo "Nova feature" > feature.txt
git add feature.txt
git commit -m "Adiciona nova feature"
```

---

## 🔀 12. Voltar e mesclar mudanças

```bash
git switch main
git merge nova_funcionalidade
```

> Junta as alterações da branch `nova_funcionalidade` na `main`.

---

## 🗑️ 13. Excluir branches locais

```bash
git branch -d nova_funcionalidade
```

---

## 🧹 14. Ignorar arquivos com `.gitignore`

Crie um arquivo chamado `.gitignore` e adicione:

```
*.log
*.tmp
node_modules/
```

Depois:

```bash
git add .gitignore
git commit -m "Adiciona arquivo .gitignore"
```

---

## 🧠 15. Visualizar informações úteis

```bash
git status
git log --oneline --graph --decorate
git diff
git show HEAD
```

> `--graph` mostra o histórico com ramificações visualmente.

---

## 💡 16. Exemplo de fluxo completo

```bash
git init
echo "Aula prática Git local" > readme.txt
git add .
git commit -m "Primeiro commit"
git branch dev
git switch dev
echo "Nova versão em desenvolvimento" >> readme.txt
git add .
git commit -m "Atualiza versão dev"
git switch main
git merge dev
git log --oneline --graph
```

---

## 🛸 17. Clonar o repositório

```bash
git clone "https:/link_do_repositorio_com_fork"
```
> Baixa a cópia do repositório para seu computador, em uma nova `pasta/diretório` local
---


## ➕ 18. Adicionar arquivos

```bash
echo "Uma mensagem bem legal" > mensagem.txt
git add mensagem.txt
git add .
```
> `echo`: adiciona um texto a um arquivo

> `git add`: prepara um determinado arquivo para a área de staging

> `git add .`: prepara todos os arquivos da pasta para a área de staging
---

## 📄 19. Criar o commit

```bash
git commit -m "feat: Adiciona documentacao sobre integracao e colaboracao"
```
> Salva uma alteração preparada com o `git add`, onde será exibido a mensagem do `commit` para explicar o que foi feito, no caso do `feat`: é uma nova funcionalidade que será mostrada.
---

## 🌐 20. Enviar para o Fork no GitHub 

```bash
git push
ou
git push nome_branch
```
> Envia o branch criado com novas as alterações feitas para o seu repositório do GitHub.
---

##  GitFluence
É uma IA que ajuda desenvolvedores a encontrar facilmente os comandos Git, seria como uma biblioteca Git, só basta perguntar em como criar tal comando, que ele te mostrará diretamente o que você precisa, em apenas uma linha, por conta de sua interface simples e direta.
Ex.:
```bash
> como crio uma branch?
> git checkout -b nome_da_branch 
```
---

## 📘 Créditos

Material criado para fins educacionais na aula prática de **Git Local**,  
ministrada por *Anderson R. M. Gomes* 🧑‍🏫

**🚀 Próximos passos:**  
Na próxima aula, você aprenderá a conectar este repositório local ao GitHub com os comandos `git remote`, `git push` e `git pull`.
