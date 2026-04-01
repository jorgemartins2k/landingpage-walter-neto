---
name: legal-landing-full
description: Skill orquestrador que integra todos os skills de design e copy para gerar uma landing page completa para advogados. Use quando precisar gerar a página inteira de uma vez.
---

# Legal Landing Full

Skill orquestrador que combina todos os skills de design e copy em uma landing page completa e coesa.

## Fluxo de Execução

### Fase 1: Estratégia (Copy Skills)
1. Executar `legal-copy-strategy` para definir tom, persona e briefing
2. Coletar informações do escritório/advogado

### Fase 2: Conteúdo (Copy Skills)
3. Executar `hero-copy-generator` para headline e subheadline
4. Executar `practice-area-copy` para conteúdo das áreas de atuação
5. Executar `trust-markers-copy` para depoimentos e números
6. Executar `cta-optimizer` para definir CTAs

### Fase 3: Design (Design Skills)
7. Executar `legal-landing-hero` para estrutura da hero
8. Executar `legal-practice-cards` para cards de serviços
9. Executar `legal-authority-section` para seção do advogado
10. Executar `legal-social-proof` para depoimentos e números
11. Executar `legal-faq-accordion` para FAQ
12. Executar `legal-footer` para rodapé

## Estrutura Final da Página (HTML)

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Nome do Advogado] | [Especialidade]</title>
  <meta name="description" content="[Meta description gerada pelo SEO skill]">
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2/dist/tailwind.min.css" rel="stylesheet">
  <style>
    /* Estilos customizados dos componentes */
  </style>
</head>
<body>
  <main>
    <section id="hero"><!-- legal-landing-hero --></section>
    <section id="trust-markers"><!-- legal-social-proof (números) --></section>
    <section id="practice-areas"><!-- legal-practice-cards --></section>
    <section id="authority"><!-- legal-authority-section --></section>
    <section id="testimonials"><!-- legal-social-proof (depoimentos) --></section>
    <section id="faq"><!-- legal-faq-accordion --></section>
    <section id="final-cta"><!-- cta-optimizer --></section>
    <footer id="footer"><!-- legal-footer --></footer>
  </main>
  <script>
    /* JavaScript para acordeão e interações */
  </script>
</body>
</html>
```

## Checklist de Qualidade

- [ ] Hero com H1, subtítulo e CTA claro
- [ ] Trust markers visíveis (números, selos)
- [ ] Cards de áreas de atuação (3-6 cards)
- [ ] Seção de autoridade com foto do advogado
- [ ] Depoimentos reais (ou placeholder realistas)
- [ ] FAQ com perguntas relevantes
- [ ] CTA repetido em pontos estratégicos
- [ ] Footer com contato e links legais
- [ ] Responsivo (mobile-first)
- [ ] Schema markup para SEO
- [ ] LGPD compliance (política de privacidade)

## Saída Esperada

1. Arquivo HTML completo
2. CSS inline ou linkado
3. JavaScript para interações
4. Schema JSON-LD
5. Meta tags para SEO
