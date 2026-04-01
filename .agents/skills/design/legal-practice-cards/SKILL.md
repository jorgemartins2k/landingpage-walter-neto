---
name: legal-practice-cards
description: Design de cards para áreas de atuação e perfis de clientes em sites de advogados. Baseado nas referências Attorneyster, Antonio Lamark e Método COP.
---

# Legal Practice Cards

Design de cards modulares para apresentar serviços, especialidades ou perfis de clientes.

## Análise das Referências

### Padrão 1: Attorneyster (IMG_2164)
```
┌─────────────────────┐
│  [Ícone]            │
│  Business Law       │
│  "We recover of your│
│   development..."   │
└─────────────────────┘
```
**Características:**
- Ícone no topo
- Título em negrito
- Descrição curta (1 linha)
- Grid 3 colunas

### Padrão 2: Método COP (IMG_2165)
```
┌─────────────────────┐
│  Estudantes de      │
│  Direito            │
│  "Para ingressar no │
│   mercado..."       │
└─────────────────────┘
```
**Características:**
- Título como foco principal
- Descrição funcional
- Grid 4 colunas no desktop

### Padrão 3: Antonio Lamark (IMG_2096)
```
┌─────────────────────┐
│  Delegacia de       │
│  Polícia            │
│  "Orientação em     │
│   procedimentos..." │
│  [Ver mais]         │
└─────────────────────┘
```
**Características:**
- Título + descrição
- Link "Ver mais" (opcional)
- Grid responsivo

## Estrutura do Card

| Elemento | Obrigatório | Posição | Características |
|----------|-------------|---------|-----------------|
| **Ícone/Imagem** | Opcional | Topo | SVG ou ícone simples, cor consistente |
| **Título** | Sim | Após ícone | 18-24px, bold, cor primária ou escura |
| **Descrição** | Sim | Abaixo título | 14-16px, regular, máx 2 linhas |
| **Link/CTA** | Opcional | Final do card | "Saiba mais", "Ver mais", cor secundária |

## Layouts de Grid

### Desktop (≥1024px)
| Nº de Cards | Layout |
|-------------|--------|
| 3 cards | grid-cols-3, gap-6 |
| 4 cards | grid-cols-4, gap-6 |
| 6 cards | grid-cols-3 (2 linhas), gap-6 |

### Tablet (768px - 1024px)
| Nº de Cards | Layout |
|-------------|--------|
| 3-4 cards | grid-cols-2, gap-4 |

### Mobile (<768px)
| Nº de Cards | Layout |
|-------------|--------|
| Qualquer | grid-cols-1, gap-4, cards empilhados |

## Estilos Base (Tailwind)

```css
.card {
  @apply bg-white rounded-xl p-6 shadow-sm border border-gray-100;
  transition: transform 0.2s, box-shadow 0.2s;
}

.card:hover {
  @apply shadow-md;
  transform: translateY(-2px);
}

.card-icon {
  @apply w-12 h-12 mb-4 text-primary-600;
}

.card-title {
  @apply text-xl font-semibold text-gray-900 mb-2;
}

.card-description {
  @apply text-gray-600 leading-relaxed;
}

.card-link {
  @apply text-primary-600 font-medium mt-4 inline-flex items-center gap-1 hover:gap-2 transition-all;
}
```

## Integração com Skills de Copy

Este skill deve ser usado APÓS a execução do `practice-area-copy`. O conteúdo textual gerado pelo skill de copy é inserido nos cards.

## Variações de Card

### Variação A: Com Ícone (Attorneyster)
Ideal para áreas de atuação com ícones representativos.

### Variação B: Sem Ícone (Método COP)
Ideal para perfis de clientes ou categorias.

### Variação C: Com "Ver mais" (Antonio Lamark)
Ideal quando cada card direciona para uma página específica.

## Saída Esperada

1. Estrutura HTML com grid responsivo
2. Classes Tailwind para cards
3. Configuração de hover e transições
4. Ícones (SVG ou biblioteca como Lucide, Heroicons)
