---
name: legal-landing-hero
description: Design e estrutura da seção hero para landing pages de advogados. Baseado nas referências de mercado (Attorneyster, Antonio Lamark, Método COP) e tendências 2026.
---

# Legal Landing Hero

Design da seção hero baseado nas melhores práticas identificadas nas referências e nas tendências de 2026.

## Estrutura do Hero (Baseada nas Referências)

| Elemento | Posição | Características | Exemplo (das referências) |
|----------|---------|-----------------|--------------------------|
| **Título Principal (H1)** | Topo | Máx 10 palavras, benefício claro | "Advogado Criminal especializado na defesa dos seus direitos" (IMG_2096) |
| **Subtítulo** | Abaixo do H1 | Máx 20 palavras, elabora o benefício | "Atuação técnica e comprometida em processos criminais" (IMG_2096) |
| **CTA Primário** | Abaixo do subtítulo | Botão contrastante, ação clara | "Falar com advogado" / "Agende sua consulta" |
| **Trust Markers (opcional)** | Abaixo do CTA | Selos, avaliações, números | "Certified Law Professionals" (IMG_2164) |

## Layouts Baseados nas Referências

### Layout A (Attorneyster - IMG_2164)
```
┌─────────────────────────────────────────┐
│  [Logo]    Home | About | Pages | Contact│
├─────────────────────────────────────────┤
│                                         │
│  "We're Group Of Certified Law          │
│   Professionals"                        │
│                                         │
│  [Get in Touch]                         │
│                                         │
└─────────────────────────────────────────┘
```
**Características:** Título curto, selo de credibilidade, CTA direto.

### Layout B (Antonio Lamark - IMG_2096)
```
┌─────────────────────────────────────────┐
│  [Logo]                                  │
├─────────────────────────────────────────┤
│                                         │
│  "Advogado Criminal especializado       │
│   na defesa dos seus direitos"          │
│                                         │
│  "Atuação técnica e comprometida em     │
│   processos criminais"                  │
│                                         │
│  [Falar com advogado]                   │
│                                         │
└─────────────────────────────────────────┘
```
**Características:** H1 com especialidade, CTA WhatsApp-style.

### Layout C (Método COP - IMG_2165)
```
┌─────────────────────────────────────────┐
│  [Logo]                                  │
├─────────────────────────────────────────┤
│                                         │
│  "Método COP"                           │
│  "Muito além de um curso"               │
│                                         │
│  [Fala com especialista]                │
│                                         │
└─────────────────────────────────────────┘
```
**Características:** Título provocativo + subtítulo explicativo.

## Tipografia (Baseada nas Referências)

| Elemento | Tamanho (Desktop) | Peso | Fonte Sugerida |
|----------|-------------------|------|----------------|
| H1 | 48-56px | Bold (700) | Inter, Montserrat, Poppins |
| Subtítulo | 20-24px | Regular (400) | Inter, Open Sans |
| CTA | 16-18px | Medium (500) | Inter, Montserrat |

## Cores e Contraste

**Baseado nas referências:**
- Fundo: branco ou off-white (#FFFFFF, #F8F9FA)
- Texto principal: escuro (#111827, #1F2937)
- Texto secundário: cinza médio (#4B5563, #6B7280)
- CTA: cor de destaque (azul marinho, verde, azul royal) com alto contraste

**Regras de contraste:**
- CTA deve ter contraste mínimo 4.5:1 com fundo
- Fundo branco com texto escuro garante legibilidade

## Responsividade (Mobile-First)

**Mobile:**
- H1: 32-36px
- Subtítulo: 16-18px
- CTA: full-width, posição fixa inferior (opcional)
- Espaçamento vertical: 48px entre seções

**Desktop:**
- H1: 48-56px
- Subtítulo: 20-24px
- Layout pode ser dividido 50/50 (texto + imagem)

## Integração com Skills de Copy

Este skill deve ser usado APÓS a execução do `hero-copy-generator`. O copy gerado pelo skill de copy alimenta este skill de design:

```
hero-copy-generator → gera headline e subheadline
legal-landing-hero → aplica estrutura visual
```

## Saída Esperada

Ao final, este skill deve gerar:
1. Estrutura HTML/CSS da seção hero
2. Classes Tailwind ou CSS customizado
3. Configuração responsiva
4. Variáveis de cor e tipografia
