# 📦 Instruções para Upload no Git

## 🎯 Passos para Subir as Alterações

### 1. Configurar seu repositório Git

```bash
# Entre no diretório do projeto
cd /caminho/para/heyform

# Configure seu nome e email (se ainda não configurou)
git config user.name "Seu Nome"
git config user.email "seu@email.com"
```

### 2. Verificar as alterações

```bash
# Ver todos os arquivos modificados
git status

# Ver detalhes das alterações
git diff
```

### 3. Adicionar os arquivos ao staging

```bash
# Adicionar todos os arquivos modificados
git add .

# OU adicionar arquivos específicos:
git add packages/webapp/src/locales/pt-BR.json
git add packages/webapp/src/consts/locale.ts
git add packages/webapp/src/i18n.ts
git add packages/webapp/src/locales/*.json
git add TRADUCAO_PT-BR.md
```

### 4. Fazer o commit

```bash
# Commit com mensagem descritiva
git commit -m "feat: adicionar tradução pt-BR (Português Brasileiro)

- Adicionar arquivo de tradução pt-BR.json com 1.142 strings
- Atualizar locale.ts para incluir pt-BR nas opções de idioma
- Configurar i18n.ts com suporte ao pt-BR
- Atualizar todos os arquivos de idioma com referência ao pt-BR
- Adicionar documentação em TRADUCAO_PT-BR.md"
```

### 5. Criar um novo repositório no GitHub (se necessário)

1. Acesse https://github.com/new
2. Crie um novo repositório (ex: `heyform-pt-br`)
3. **NÃO** inicialize com README, .gitignore ou licença

### 6. Conectar ao repositório remoto

```bash
# Se for um novo repositório
git remote add origin https://github.com/seu-usuario/heyform-pt-br.git

# OU se quiser substituir o origin existente
git remote set-url origin https://github.com/seu-usuario/heyform-pt-br.git

# Verificar o remote
git remote -v
```

### 7. Fazer push para o GitHub

```bash
# Push para a branch principal
git push -u origin next

# OU criar uma nova branch para as alterações
git checkout -b feature/pt-br-translation
git push -u origin feature/pt-br-translation
```

## 🔄 Alternativa: Criar um Fork

Se preferir manter a conexão com o repositório original:

```bash
# 1. Fazer fork do repositório original no GitHub
# Acesse: https://github.com/heyform/heyform e clique em "Fork"

# 2. Adicionar seu fork como remote
git remote add myfork https://github.com/seu-usuario/heyform.git

# 3. Push para seu fork
git push myfork next
```

## 📋 Resumo dos Arquivos Alterados

```json
{
  "novos_arquivos": [
    "packages/webapp/src/locales/pt-BR.json",
    "TRADUCAO_PT-BR.md",
    "INSTRUCOES_GIT.md"
  ],
  "arquivos_modificados": [
    "packages/webapp/src/consts/locale.ts",
    "packages/webapp/src/i18n.ts",
    "packages/webapp/src/locales/de.json",
    "packages/webapp/src/locales/en.json",
    "packages/webapp/src/locales/fr.json",
    "packages/webapp/src/locales/ja.json",
    "packages/webapp/src/locales/pl.json",
    "packages/webapp/src/locales/zh-cn.json",
    "packages/webapp/src/locales/zh-tw.json"
  ]
}
```

## 🚀 Após o Push

### Criar Pull Request (opcional)

Se quiser contribuir com o projeto original:

1. Acesse seu fork no GitHub
2. Clique em "Pull Request"
3. Selecione a branch com suas alterações
4. Adicione título: "feat: Add pt-BR (Brazilian Portuguese) translation"
5. Descreva as alterações no corpo do PR
6. Envie o Pull Request

### Compartilhar seu Fork

Seu repositório estará disponível em:
```
https://github.com/seu-usuario/heyform-pt-br
```

## 💡 Dicas

- **Mantenha sincronizado:** Periodicamente, sincronize com o repositório original
- **Documentação:** O arquivo TRADUCAO_PT-BR.md explica todas as alterações
- **Testes:** Recomenda-se testar a aplicação localmente antes do push
- **Branch:** Considere usar branches separadas para features

## 🆘 Solução de Problemas

### Erro de autenticação
```bash
# Use Personal Access Token em vez de senha
# Gere em: https://github.com/settings/tokens
```

### Conflitos de merge
```bash
# Atualizar do repositório original
git fetch origin
git merge origin/next
# Resolver conflitos manualmente
git add .
git commit -m "fix: resolver conflitos de merge"
```

### Desfazer último commit (se necessário)
```bash
# Mantém as alterações
git reset --soft HEAD~1

# Remove as alterações
git reset --hard HEAD~1
```

---

**Pronto!** Suas alterações estarão disponíveis no GitHub para compartilhamento ou contribuição.
