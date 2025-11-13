# 🤖 robots.txt - Bemol VTEX Store

Arquivo robots.txt otimizado para e-commerce na plataforma VTEX, configurado para máxima performance em SEO e controle de crawlers.

## 📋 Índice

- [Visão Geral](#visão-geral)
- [Principais Bloqueios](#principais-bloqueios)
- [Bots Permitidos](#bots-permitidos)
- [Bots Bloqueados](#bots-bloqueados)
- [Como Testar](#como-testar)
- [Changelog](#changelog)

---

## 🎯 Visão Geral

Este robots.txt foi desenvolvido especificamente para lojas VTEX, considerando:

- ✅ Prevenção de conteúdo duplicado
- ✅ Proteção de áreas sensíveis (checkout, conta do cliente)
- ✅ Otimização do crawl budget
- ✅ Controle de bots de IA e scrapers
- ✅ Conformidade com melhores práticas de SEO

## 🚫 Principais Bloqueios

### Checkout e Carrinho
```
/checkout/*
/finalizacao/carrinho
```
Protege o fluxo de compra e evita indexação de páginas transitórias.

### Área do Cliente
```
/account/*
/login
```
Garante privacidade e segurança das informações dos usuários.

### Parâmetros de URL (Conteúdo Duplicado)
```
/*?*map=
/*?O=
/*?PS=
```
Bloqueia variações de URL que geram páginas duplicadas comuns na VTEX:
- `?O=` - Ordenação de produtos
- `?PS=` - Page size (produtos por página)
- `?map=` - Mapeamento de filtros

### APIs e Recursos Internos
```
/api/*
/web-api/*
/no-cache/*
/_secure/*
```
Protege endpoints de API e áreas administrativas.

### Landing Pages de Teste
```
/lp/*
/pagina-teste/*
/kit-mkt/*
```
Evita indexação de páginas temporárias ou em desenvolvimento.

## ✅ Bots Permitidos

### Buscadores Principais
- **Googlebot** - Google Search
- **Bingbot** - Bing Search
- **BingPreview** - Bing Preview

### Assistentes de IA
- **ChatGPT-User** - ChatGPT browse
- **OAI-SearchBot** - OpenAI Search
- **ClaudeBot** - Anthropic Claude
- **anthropic-ai** - Anthropic crawler
- **PerplexityBot** - Perplexity AI
- **Google-Extended** - Google AI/Gemini

### Ferramentas SEO
- **Screaming Frog SEO Spider** - Auditoria técnica

## 🛑 Bots Bloqueados

Scrapers e crawlers indesejados:

| Bot | Motivo |
|-----|--------|
| `EtaoSpider` | Scraper chinês (Alibaba) |
| `CCBot` | Common Crawl (consumo excessivo) |
| `GPTBot` | OpenAI training bot |
| `Amazonbot` | Amazon scraping |
| `FacebookBot` | Meta crawler |
| `Bytespider` | ByteDance/TikTok |
| `PetalBot` | Huawei search engine |

> 💡 **Nota**: GPTBot está bloqueado para treinamento, mas ChatGPT-User (navegação) está permitido.

## 🧪 Como Testar

### 1. Google Search Console
```
1. Acesse: https://search.google.com/search-console
2. Vá em: Indexação > robots.txt
3. Digite uma URL para testar
4. Clique em "Testar"
```

### 2. Validação Online
- [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)
- [Bing Webmaster Tools](https://www.bing.com/webmasters)

### 3. Teste Local (cURL)
```bash
curl https://www.bemol.com.br/robots.txt
```

### 4. Screaming Frog
```
1. Abra o Screaming Frog SEO Spider
2. Configuration > Robots.txt
3. Faça upload do arquivo
4. Valide as regras
```

## 📊 Monitoramento

### Google Search Console
Acompanhe regularmente:
- **Cobertura** - URLs bloqueadas vs indexadas
- **Sitemaps** - Páginas enviadas vs descobertas
- **Crawl Stats** - Solicitações do Googlebot

### Métricas Importantes
- ⬇️ Redução de crawl em páginas duplicadas
- ⬆️ Aumento de indexação de páginas importantes
- 🎯 Melhoria no ranking de produtos principais

## 📁 Estrutura do Arquivo

```
robots.txt
├── User-agent: * (Regras globais)
├── Bloqueios específicos VTEX
├── User-agents individuais (SEO tools)
├── Bots de IA (permitidos)
├── Bots principais (Google, Bing)
├── Bots indesejados (bloqueados)
└── Sitemap
```

## ⚠️ Avisos Importantes

### ❌ NÃO Bloquear
- `/arquivos/*` - Contém imagens e assets CSS/JS
- `/sistema/*` - Recursos da plataforma VTEX
- Páginas de produto e categoria principais

### ✅ Considerar Bloquear (Caso Aplicável)
- `/busca?*` - Se tiver muitas variações de busca
- `/atendimento` - Se não quiser indexar FAQ
- URLs de rastreamento (`?utm_*`) - Já tratado pelo `?*`

## 🔄 Changelog

### v2.0.0 (2024)
- ✨ Adicionado bloqueio de parâmetros VTEX (`?O=`, `?PS=`)
- ✨ Adicionado suporte a bots de IA (Claude, ChatGPT, Perplexity)
- ✨ Bloqueados scrapers maliciosos (Bytespider, PetalBot)
- 🐛 Corrigido espaçamento após `:` em todas as diretivas
- 📝 Adicionados wildcards para melhor clareza
- 🔒 Bloqueado `/api/*` e `/no-cache/*`

### v1.0.0 (Anterior)
- 🎉 Versão inicial

## 🤝 Contribuindo

Para sugerir melhorias:

1. Abra uma issue descrevendo o problema/melhoria
2. Teste as mudanças no Google Search Console
3. Envie um PR com as alterações documentadas

## 📚 Recursos Úteis

- [Documentação VTEX - SEO](https://help.vtex.com/pt/tutorial/seo-na-vtex--1lJGhFMH44WAogkqEuAOyc)
- [Google Search Central - robots.txt](https://developers.google.com/search/docs/crawling-indexing/robots/intro)
- [RFC 9309 - Robots Exclusion Protocol](https://www.rfc-editor.org/rfc/rfc9309.html)

## 📞 Suporte

Dúvidas sobre implementação? Entre em contato com a equipe de SEO Bemol 

---

**Última atualização**: Novembro 2025
**Plataforma**: VTEX IO  
**Mantido por**: Equipe Bemol Digital
