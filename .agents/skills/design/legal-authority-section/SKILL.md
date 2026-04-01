---
name: legal-authority-section
description: Design da seção de autoridade com foto do advogado, biografia e credenciais. Baseado nas referências Antonio Lamark e Método COP.
---

# Legal Authority Section

Design da seção que apresenta o advogado, suas credenciais e constrói autoridade.

## Análise das Referências

### Padrão 1: Antonio Lamark (IMG_2096)
```
┌────────────────────┬────────────────────┐
│                    │                    │
│  [Foto do          │  Quem é Antonio    │
│   Advogado]        │  Lamark            │
│                    │                    │
│                    │  - Formação USP    │
│                    │  - 20 anos de exp  │
│                    │  - Especialista    │
│                    │                    │
│                    │  [+300] [+570]     │
│                    │  [+1000]           │
└────────────────────┴────────────────────┘
```
**Características:**
- Layout 2 colunas: foto + texto
- Bio completa com formação e experiência
- Números de destaque (prova social quantitativa)
- CTA "Falar com advogado" no final

### Padrão 2: Método COP (IMG_2165)
```
┌────────────────────┬────────────────────┐
│                    │                    │
│  [Foto do          │  Dr. Carlos        │
│   Advogado]        │  Oliveira          │
│                    │                    │
│                    │  "Reconhecido      │
│                    │   nacionalmente..."│
│                    │                    │
│                    │  - 20 anos de      │
│                    │    carreira        │
│                    │  - Escritório      │
│                    │    respeitado      │
└────────────────────┴────────────────────┘
```
**Características:**
- Layout 2 colunas
- Citação/depoimento destacado
- Bullets com conquistas

## Estrutura da Seção

| Elemento | Posição | Características |
|----------|---------|-----------------|
| **Foto** | Coluna esquerda | Imagem profissional, redonda ou retangular, 200-300px |
| **Nome** | Coluna direita | 24-32px, bold, cor escura |
| **Título/Cargo** | Abaixo do nome | 16-18px, cor secundária, "Advogado Especialista em..." |
| **Bio** | Abaixo do título | Texto corrido, 16px, line-height 1.6 |
| **Credenciais** | Bullets ou lista | Formação, anos de experiência, associações |
| **Números** | Opcional | Cards com +X clientes, +X casos |
| **CTA** | Final da coluna direita | Botão secundário ou link para contato |

## Layout Responsivo

### Desktop (≥1024px)
- Grid 2 colunas (40% foto, 60% texto)
- Foto alinhada ao topo
- Espaçamento horizontal: 48px

### Tablet (768px - 1024px)
- Grid 2 colunas (35% foto, 65% texto)
- Espaçamento horizontal: 32px

### Mobile (<768px)
- Grid 1 coluna
- Foto centralizada, largura máxima 200px
- Texto abaixo da foto
- Espaçamento vertical: 24px

## Estilos Base (Tailwind)

```css
.authority-section {
  @apply py-16 bg-gray-50;
}

.authority-image {
  @apply rounded-2xl shadow-lg object-cover;
  width: 100%;
  max-width: 280px;
  aspect-ratio: 1 / 1;
}

.authority-name {
  @apply text-3xl font-bold text-gray-900 mb-2;
}

.authority-title {
  @apply text-lg text-primary-600 font-medium mb-4;
}

.authority-bio {
  @apply text-gray-600 leading-relaxed mb-6;
}

.authority-credentials {
  @apply space-y-2 mb-6;
}

.authority-credential-item {
  @apply flex items-start gap-2 text-gray-700;
}

.authority-numbers {
  @apply grid grid-cols-3 gap-4 mb-6;
}

.authority-number-card {
  @apply text-center;
}

.authority-number-value {
  @apply text-2xl font-bold text-gray-900;
}

.authority-number-label {
  @apply text-sm text-gray-500;
}
```

## Integração com Skills de Copy

Este skill deve ser usado APÓS a execução de:
- `legal-copy-strategy` (para definir tom e persona)
- `trust-markers-copy` (para números e depoimentos)

## Saída Esperada

1. Layout responsivo 2 colunas
2. Componente de foto otimizada
3. Seção de números/destaques (se disponíveis)
4. CTA integrado
