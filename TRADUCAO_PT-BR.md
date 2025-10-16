# Tradução pt-BR para HeyForm

## 📋 Resumo das Alterações

Este fork adiciona suporte completo ao idioma **Português Brasileiro (pt-BR)** no HeyForm.

## 🎯 Arquivos Modificados

### Novos Arquivos
- `packages/webapp/src/locales/pt-BR.json` - Arquivo de tradução completo com 1.142 strings

### Arquivos Atualizados

#### Configuração de Idiomas
- `packages/webapp/src/consts/locale.ts` - Adicionado pt-BR na lista de idiomas disponíveis
- `packages/webapp/src/i18n.ts` - Configurado suporte ao pt-BR no sistema de internacionalização

#### Arquivos de Tradução (seção languages atualizada)
- `packages/webapp/src/locales/de.json`
- `packages/webapp/src/locales/en.json`
- `packages/webapp/src/locales/fr.json`
- `packages/webapp/src/locales/ja.json`
- `packages/webapp/src/locales/pl.json`
- `packages/webapp/src/locales/zh-cn.json`
- `packages/webapp/src/locales/zh-tw.json`

## 🔧 Detalhes Técnicos

### Alterações em `locale.ts`
Adicionado objeto de configuração para pt-BR:
```typescript
{
  value: 'pt-BR',
  label: 'languages.pt-BR.original',
  translated: 'languages.pt-BR.translated'
}
```

### Alterações em `i18n.ts`
1. **Import do arquivo de tradução:**
```typescript
import ptBR from '@/locales/pt-BR.json'
```

2. **Adicionado ao objeto resources:**
```typescript
'pt-BR': {
  translation: {
    ...ptBR,
    ...locales['pt-BR']?.translation || {}
  }
}
```

3. **Configurado fallback para português:**
```typescript
fallbackLng: {
  default: [DEFAULT_LNG],
  zh: ['zh-cn'],
  pt: ['pt-BR']
}
```

## 📊 Estatísticas da Tradução

- **Total de strings traduzidas:** 1.142
- **Estrutura JSON:** Idêntica ao arquivo original en.json
- **Encoding:** UTF-8 sem BOM
- **Qualidade:** Tradução profissional mantendo variáveis, tags HTML e placeholders

## ✅ Características da Tradução

- ✅ Mantém todas as variáveis `{{variable}}` intactas
- ✅ Preserva tags HTML (`<span>`, `<strong>`, etc.)
- ✅ Mantém placeholders de internacionalização `$t(...)`
- ✅ Linguagem natural e fluente em português brasileiro
- ✅ Termos técnicos traduzidos conforme convenções brasileiras

## 🚀 Como Usar

### Opção 1: Clonar este repositório
```bash
git clone [seu-repositorio]
cd heyform
```

### Opção 2: Aplicar as alterações manualmente
1. Copie o arquivo `pt-BR.json` para `packages/webapp/src/locales/`
2. Atualize os arquivos `locale.ts` e `i18n.ts` conforme descrito acima
3. Atualize os arquivos de tradução existentes com a entrada pt-BR

### Compilar e executar
```bash
# Instalar dependências
npm install

# Executar em modo desenvolvimento
npm run dev

# Build para produção
npm run build
```

## 📝 Exemplos de Tradução

| Chave | Inglês | Português (Brasil) |
|-------|--------|-------------------|
| workspace.sidebar.workspaces | Workspaces | Ambientes de trabalho |
| workspace.sidebar.logout | Logout | Sair |
| dashboard.title | Dashboard | Painel |
| settings.title | Workspace Settings | Configurações do Ambiente |
| members.title | Members | Membros |

## 🤝 Contribuindo

Se encontrar erros de tradução ou tiver sugestões de melhorias:

1. Abra uma issue descrevendo o problema
2. Ou envie um pull request com a correção

## 📄 Licença

Este projeto mantém a mesma licença do HeyForm original.

---

**Data de criação:** Outubro 2025  
**Versão:** 1.0  
**Baseado em:** HeyForm (branch next)
