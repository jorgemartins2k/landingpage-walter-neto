---
name: legal-faq-accordion
description: Design da seção de FAQ com acordeão para sites de advogados. Baseado nas melhores práticas de acessibilidade e experiência do usuário.
---

# Legal FAQ Accordion

Design da seção de perguntas frequentes com componente acordeão expansível.

## Análise das Referências

### Padrão FAQ: IMG_2097
```
Perguntas Frequentes:
1. Como funciona o processamento de consulta jurídica?
2. Porque é importante manter um arquivo de documentos?
3. Como posso acompanhar o andamento do meu processo?
4. Quanto tempo leva para resolver um processo criminal?
```
**Características:**
- Lista numerada de perguntas
- Simples, sem acordeão (expande na página)
- Ideal para perguntas curtas

### Padrão Acordeão (Melhores Práticas)
```
┌─────────────────────────────────────────┐
│  ▼ Como funciona o processo de consulta?│
├─────────────────────────────────────────┤
│  [Resposta expandida com detalhes]      │
└─────────────────────────────────────────┘
┌─────────────────────────────────────────┐
│  ▶ Quanto tempo demora um processo?     │
└─────────────────────────────────────────┘
```

## Estrutura do Acordeão

| Elemento | Características |
|----------|-----------------|
| **Pergunta (Trigger)** | 16-18px, semibold, cursor pointer, hover effect |
| **Ícone** | Chevron (▼/▶) ou (+/-), transição suave |
| **Resposta** | 14-16px, regular, padding, borda ou fundo diferenciado |

## Acessibilidade (ARIA)

```html
<div class="faq-item">
  <button 
    class="faq-question" 
    aria-expanded="false"
    aria-controls="faq-answer-1"
  >
    <span>Como funciona o processo de consulta jurídica?</span>
    <svg class="faq-icon" aria-hidden="true">...</svg>
  </button>
  <div 
    id="faq-answer-1" 
    class="faq-answer" 
    aria-hidden="true"
  >
    <p>Resposta detalhada...</p>
  </div>
</div>
```

## Estilos Base (Tailwind)

```css
.faq-section {
  @apply py-16 bg-white;
}

.faq-item {
  @apply border-b border-gray-200 last:border-b-0;
}

.faq-question {
  @apply w-full flex justify-between items-center py-4 text-left font-medium text-gray-900 hover:text-primary-600 transition-colors;
}

.faq-icon {
  @apply w-5 h-5 transition-transform duration-200;
}

.faq-icon.open {
  @apply rotate-180;
}

.faq-answer {
  @apply pb-4 text-gray-600 leading-relaxed;
}

/* Animação suave */
.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-out;
}

.faq-answer.open {
  max-height: 500px;
  transition: max-height 0.5s ease-in;
}
```

## Layout Responsivo

- Desktop: largura máxima 800px, centralizado
- Mobile: padding lateral 16px, texto 14px
- Espaçamento vertical entre perguntas: 0 (border separa)

## SEO Considerations

- FAQ em formato de acordeão ainda é indexado pelo Google
- Incluir schema markup FAQPage para rich snippets
- Perguntas devem ser em formato interrogativo (como, quando, onde)

## Integração com Skills de Copy

Este skill deve ser usado APÓS a execução de `practice-area-copy` (que já inclui FAQ) ou `seo-content-optimizer`.

## Saída Esperada

1. Componente acordeão com JavaScript (ou CSS puro)
2. ARIA labels para acessibilidade
3. Schema markup JSON-LD para FAQPage
4. Transições suaves
