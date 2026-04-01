---
name: legal-footer
description: Design do rodapé para landing pages de advogados. Inclui contato, links úteis, direitos autorais e redes sociais.
---

# Legal Footer

Design do rodapé da landing page com todas as informações necessárias para contato e conformidade.

## Análise das Referências

### Padrão Footer: Antonio Lamark (IMG_2096)
```
┌─────────────────────────────────────────┐
│  ATORNEY & LAW                          │
│  © Legal - contato@atorney.com.br       │
│  Términos e Condições                   │
│  Tel.: +55 11 2124-5678                 │
│  Copyright © Attorney Law Firm - 2023   │
└─────────────────────────────────────────┘
```
**Características:**
- Nome do escritório
- Email e telefone
- Links para termos e condições
- Copyright com ano

### Padrão Footer: Método COP (IMG_2165)
```
┌─────────────────────────────────────────┐
│  Japodegan | Todos os direitos reservados│
│  Contato@metodocop.com.br               │
│  Copyright © 2024 Todos os Direitos     │
│  Publicações de Privacidade | Termos    │
└─────────────────────────────────────────┘
```
**Características:**
- Links para políticas de privacidade
- Termos de uso
- Email de contato

## Estrutura do Footer

### Desktop (Grid 4 colunas)

| Coluna 1 | Coluna 2 | Coluna 3 | Coluna 4 |
|----------|----------|----------|----------|
| Logo | Áreas de Atuação | Links Rápidos | Contato |
| Descrição | Direito Penal | Sobre | Telefone |
| | Direito Civil | Blog | Email |
| | Direito Trabalhista | FAQ | Redes Sociais |

### Mobile (Stacked)
- Todas as colunas empilhadas
- Cada seção com espaçamento vertical
- Copyright na parte inferior

## Elementos Obrigatórios

| Elemento | Obrigatório | Motivo |
|----------|-------------|--------|
| **Nome do escritório/Logo** | Sim | Identidade visual |
| **Email de contato** | Sim | Canal de comunicação |
| **Telefone** | Sim | Conversão |
| **Copyright + Ano** | Sim | Conformidade legal |
| **Política de Privacidade** | Sim | LGPD (Brasil) |
| **Termos de Uso** | Sim | Proteção legal |

## Estilos Base (Tailwind)

```css
.footer {
  @apply bg-gray-900 text-gray-300 py-12;
}

.footer-logo {
  @apply text-white text-xl font-bold mb-4;
}

.footer-description {
  @apply text-gray-400 text-sm mb-4;
}

.footer-title {
  @apply text-white font-semibold mb-4;
}

.footer-links {
  @apply space-y-2;
}

.footer-link {
  @apply text-gray-400 hover:text-white transition-colors text-sm;
}

.footer-contact-item {
  @apply flex items-center gap-2 text-gray-400 mb-2;
}

.footer-social {
  @apply flex gap-4 mt-4;
}

.footer-copyright {
  @apply border-t border-gray-800 mt-8 pt-8 text-center text-sm text-gray-500;
}
```

## Links Obrigatórios (LGPD Brasil)

Para estar em conformidade com a LGPD, o footer deve conter:

1. **Política de Privacidade** - /privacidade
2. **Termos de Uso** - /termos
3. **Política de Cookies** - /cookies (se houver)

## Integração com Skills de Copy

Este skill pode ser usado independentemente, mas recomenda-se integrar com `legal-copy-strategy` para manter consistência de tom e branding.

## Saída Esperada

1. Grid responsivo com 4 colunas (desktop) / 1 coluna (mobile)
2. Links para políticas obrigatórias
3. Ícones de redes sociais
4. Copyright dinâmico com ano atual
