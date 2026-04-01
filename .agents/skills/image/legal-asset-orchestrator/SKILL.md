---
name: legal-asset-orchestrator
description: Skill orquestrador que analisa imagens de referência na pasta /references, estuda o estilo, e aplica nos assets obrigatórios da pasta /assets para gerar landing pages coesas.
---

# Legal Asset Orchestrator

Este skill orquestra todo o fluxo de trabalho de assets e referências.

## Fluxo de Trabalho

### Fase 1: Leitura e Análise das Referências

A IA deve **ler todos os arquivos na pasta /references/** e extrair:

1. **Estilos de Design**
   - Paletas de cores predominantes
   - Tipografia usada
   - Espaçamentos e grids
   - Estilo de cards e botões

2. **Layouts e Estruturas**
   - Como a hero section é organizada
   - Posicionamento de CTAs
   - Hierarquia visual

3. **Estilo de Imagens**
   - Como as fotos são tratadas (circular? retangular? com sombra?)
   - Fundos usados (gradiente? sólido? blur?)
   - Tratamento de logos

### Fase 2: Extração dos Assets Obrigatórios

A IA deve **ler todos os arquivos na pasta /assets/** :

| Subpasta | O Que Contém | Como a IA Usa |
|----------|--------------|--------------|
| `client-logo/` | Logos do escritório | Insere no header, footer, favicon |
| `lawyer-photos/` | Fotos originais dos advogados | Envia para edição contextual |
| `mandatory/icones/` | Ícones personalizados | Usa nos cards de áreas de atuação |
| `mandatory/selos/` | Selos de credibilidade | Insere na seção de trust markers |
| `mandatory/backgrounds/` | Fundos customizados | Aplica como opção de fundo |

### Fase 3: Análise de Estilo (Matching)

A IA compara as referências com os assets e define:

```
## Análise de Estilo (Baseada nas Referências)

### Referência Analisada: Attorneyster (IMG_2164)
- Estilo: Moderno, limpo, muito espaço branco
- Cores: Azul marinho (#1e3a8a) + branco + cinza suave
- Fotos: Retangulares, sem fundo, com sombra sutil
- Logos: Header esquerdo, branco em fundo escuro

### Como Aplicar no Asset:

**Logo do cliente:**
- Posição: Header esquerdo
- Cor: Versão branca se fundo escuro, versão colorida se fundo claro
- Tamanho: 160px de largura

**Foto do advogado:**
- Estilo: Retangular, sem fundo, sombra sutil
- Fundo: Gradiente combinando com paleta do site
- Enquadramento: 3:4, foco no rosto
- Edição: Iluminação profissional, preservar traços

**Ícones:**
- Estilo: Linear, cor primária, 24x24px
- Posição: Topo dos cards
```

### Fase 4: Execução das Edições

Para cada foto em `/assets/lawyer-photos/`:

1. **Enviar para Nano Banana 2** com instruções contextuais:
   - *"Edite esta foto do advogado aplicando o estilo identificado nas referências"*
   - *"Remova o fundo com precisão"*
   - *"Aplique fundo [gradiente/sólido/blur] conforme referência"*
   - *"Ajuste iluminação para tom profissional"*
   - *"Preserve todos os traços faciais naturalmente"*

2. **Salvar na pasta `/output/edited-photos/`** com nomenclatura:
   - `[nome]-edited.webp` (versão principal)
   - `[nome]-edited-hero.webp` (versão hero, maior)
   - `[nome]-edited-circle.webp` (versão circular, se necessário)

### Fase 5: Geração do Código

Com tudo analisado e editado, a IA gera:

1. **Landing page completa** usando os skills de design
2. **Imagens referenciadas corretamente** do `/output/edited-photos/`
3. **CSS com as cores e estilos extraídos das referências**
4. **Logos inseridas** do `/assets/client-logo/`

## Exemplo de Uso

**Prompt do usuário:**
*"Tenho as referências na pasta /references/sites/ e os assets na pasta /assets/. Gera a landing page completa seguindo o estilo das referências."*

**Ações da IA:**

1. ✅ Lê `/references/sites/attorneyster-home.png` e extrai estilo
2. ✅ Lê `/references/sites/antonio-lamark-hero.png` e extrai layout
3. ✅ Lê `/assets/client-logo/logo-principal.png` e identifica formato
4. ✅ Lê `/assets/lawyer-photos/dr-carlos-original.jpg` e envia para edição
5. ✅ Chama Nano Banana 2 com instruções contextuais
6. ✅ Salva foto editada em `/output/edited-photos/dr-carlos-edited.webp`
7. ✅ Gera landing page com referências corretas
8. ✅ Insere logo no header e footer
9. ✅ Aplica paleta de cores extraída

## Validação Automática

Antes de finalizar, a IA valida:

- [ ] Todas as fotos foram editadas e estão em `/output/`
- [ ] A logo foi aplicada em todas as posições necessárias
- [ ] O estilo final é consistente com as referências
- [ ] As imagens estão otimizadas para web (webp, compressão)
- [ ] O layout é responsivo (mobile-first)

## Integração com Skills Existentes

Este skill orquestrador chama os outros skills na ordem correta:

```
1. legal-asset-orchestrator (análise de referências)
   ↓
2. legal-photo-contextual-editor (edição de fotos)
   ↓
3. legal-copy-strategy (definição de tom)
   ↓
4. hero-copy-generator (textos da hero)
   ↓
5. legal-landing-hero (design da hero com foto editada)
   ↓
6. legal-practice-cards (cards com ícones)
   ↓
7. legal-authority-section (seção com foto editada)
   ↓
8. legal-social-proof (depoimentos e números)
   ↓
9. legal-faq-accordion (FAQ)
   ↓
10. legal-footer (rodapé com logo)
   ↓
11. legal-landing-full (montagem final)
```
