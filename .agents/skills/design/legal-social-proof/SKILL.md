---
name: legal-social-proof
description: Design da seção de prova social para sites de advogados. Inclui depoimentos, números de destaque e selos de credibilidade.
---

# Legal Social Proof

Design da seção que exibe depoimentos de clientes, números de destaque e selos de confiança.

## Análise das Referências

### Padrão Depoimentos: Método COP (IMG_2165)
```
┌─────────────────────────────────────────┐
│  "Conteúdo transmitido por quem vive    │
│   a advocacia..."                       │
│  — Dr. Carlos Oliveira                  │
└─────────────────────────────────────────┘
```
**Características:**
- Aspas visuais
- Texto em itálico ou fonte diferenciada
- Autor com nome e cargo

### Padrão Números: Antonio Lamark (IMG_2096)
```
┌──────────┬──────────┬──────────┐
│  +300    │  +570    │  +1000   │
│  Clientes│ Contratos│ Processos│
│  Atendidos│ Fechados │ Executivos│
└──────────┴──────────┴──────────┘
```
**Características:**
- Números grandes (32-48px)
- Labels descritivos
- Grid 3 colunas

## Estrutura da Seção de Prova Social

### 1. Depoimentos

| Elemento | Características |
|----------|-----------------|
| **Citação** | Texto em itálico ou fonte diferenciada, 18-20px, line-height 1.5 |
| **Autor** | Nome + cargo/área, 14-16px, regular |
| **Foto (opcional)** | 40-48px, circular, ao lado do nome |
| **Avaliação (opcional)** | Estrelas (5/5) ou nota numérica |

**Layouts de Depoimentos:**
- **Carrossel**: múltiplos depoimentos em slider
- **Grid**: 2-3 depoimentos lado a lado
- **Destaque**: um depoimento principal em formato de card

### 2. Números de Destaque

| Elemento | Características |
|----------|-----------------|
| **Valor** | 32-48px, bold, cor primária ou escura |
| **Label** | 14-16px, regular, cor secundária |
| **Ícone (opcional)** | Pequeno SVG antes do valor |

**Layouts de Números:**
- **Grid 3-4 colunas** no desktop
- **Grid 2 colunas** no mobile
- Cada número em card com fundo suave

### 3. Selos e Prêmios

| Elemento | Características |
|----------|-----------------|
| **Ícone/Selo** | 48-64px, consistente |
| **Nome do prêmio** | 14px, bold |
| **Ano (opcional)** | 12px, regular |

## Estilos Base (Tailwind)

```css
/* Depoimentos */
.testimonial-card {
  @apply bg-white p-6 rounded-xl shadow-sm border border-gray-100;
}

.testimonial-quote {
  @apply text-gray-700 text-lg italic leading-relaxed mb-4;
}

.testimonial-author {
  @apply flex items-center gap-3;
}

.testimonial-author-name {
  @apply font-semibold text-gray-900;
}

.testimonial-author-title {
  @apply text-sm text-gray-500;
}

/* Números */
.number-card {
  @apply text-center p-6;
}

.number-value {
  @apply text-4xl font-bold text-primary-600;
}

.number-label {
  @apply text-gray-600 mt-2;
}

/* Selos */
.selo-card {
  @apply text-center p-4;
}

.selo-image {
  @apply w-16 h-16 mx-auto mb-2;
}

.selo-name {
  @apply text-sm font-medium text-gray-700;
}
```

## Layout Responsivo

### Desktop (≥1024px)
- Depoimentos: grid-cols-2 ou carrossel
- Números: grid-cols-3 ou grid-cols-4
- Selos: grid-cols-4 ou grid-cols-6

### Mobile (<768px)
- Depoimentos: grid-cols-1
- Números: grid-cols-2
- Selos: grid-cols-3

## Integração com Skills de Copy

Este skill deve ser usado APÓS a execução de `trust-markers-copy`. O conteúdo gerado (depoimentos, números, selos) alimenta o design.

## Saída Esperada

1. Componente de depoimentos (carrossel ou grid)
2. Componente de números de destaque
3. Componente de selos e prêmios
4. Todos responsivos
