---
name: legal-photo-contextual-editor
description: Editor de fotos contextual para advogados que integra com o design do site. Remove fundo, aplica gradientes conforme paleta de cores do projeto, ajusta iluminação e mantém fidelidade facial. Use quando precisar editar fotos de advogados para landing pages.
---

# Legal Photo Contextual Editor

Editor de fotos que entende o contexto do design do site e aplica edições humanizadas que se integram perfeitamente ao projeto.

## Fluxo de Trabalho

### Fase 1: Análise do Contexto do Site

Antes de editar qualquer foto, o skill deve:

1. **Extrair a paleta de cores do site**
   - Ler tailwind.config.js ou CSS variables
   - Identificar cor primária, secundária e fundos
   - Exemplo: `primary: "#1e3a8a"` (azul marinho)

2. **Identificar onde a foto será inserida**
   - Seção hero? Seção de autoridade? Card de depoimento?
   - Layout: 2 colunas? Circular? Retangular?
   - Dimensões necessárias

3. **Determinar o estilo do fundo**
   - Gradiente suave?
   - Cor sólida institucional?
   - Efeito de sombra?
   - Imagem de escritório (blur)?

### Fase 2: Edição Contextual da Foto

Utilizar Nano Banana 2 com as seguintes etapas:

#### Passo 1: Remoção de Fundo com Precisão

```json
{
  "prompt": "Remove the background from this professional lawyer photo with hair-level precision. Keep the person perfectly isolated with clean edges.",
  "aspect_ratio": "3:4",
  "image_size": "2K"
}
```

#### Passo 2: Aplicar Fundo Contextual

Com base na análise do site, aplicar o fundo adequado:

**Se site tem gradiente:**
```json
{
  "prompt": "Place this person on a professional gradient background that matches the website's color scheme. Use [PRIMARY_COLOR] fading to [SECONDARY_COLOR] with a soft, elegant transition. Keep the lighting consistent with the person's original lighting.",
  "aspect_ratio": "3:4"
}
```

**Se site tem fundo sólido:**
```json
{
  "prompt": "Place this person on a solid [PRIMARY_COLOR] background that matches the website's brand identity. Add a subtle shadow behind the person to create depth and separation.",
  "aspect_ratio": "3:4"
}
```

**Se site tem fundo de escritório:**
```json
{
  "prompt": "Place this person in a modern law office background with bookshelves and professional atmosphere. Use a subtle depth-of-field blur to keep the focus on the person. Match the lighting to create a natural composite.",
  "aspect_ratio": "3:4"
}
```

#### Passo 3: Ajustes de Iluminação e Tom

```json
{
  "prompt": "Enhance the lighting to make this look like a professional headshot. Brighten the face slightly, add catchlights to the eyes, and ensure skin tones look natural and healthy. Maintain all original facial features and proportions.",
  "aspect_ratio": "3:4"
}
```

#### Passo 4: Otimização para o Layout

Baseado no local de inserção:

| Local | Ajuste |
|-------|--------|
| Hero (grande) | Manter alta resolução, foco no rosto, enquadramento 3:4 |
| Seção autoridade (médio) | Ajustar para 1:1 ou circular, manter expressão profissional |
| Card (pequeno) | Otimizar para thumbnail, reduzir tamanho mas manter qualidade |

### Fase 3: Validação e Feedback

Após cada edição, validar:

1. **Fidelidade facial**: O rosto continua reconhecível? 
2. **Integração visual**: A foto combina com o design do site?
3. **Qualidade técnica**: Resolução adequada? Iluminação natural?
4. **Consistência de estilo**: Combina com outras imagens do site?

## Integração com Skills de Design

Este skill deve ser executado ANTES dos skills de design que inserem a foto:

```
legal-photo-contextual-editor → foto editada e otimizada
legal-landing-hero → insere foto no contexto correto
legal-authority-section → insere foto na seção de autoridade
```

## Exemplo de Uso Completo

**Prompt do usuário:**
*"Aqui está a foto do Dr. Carlos para o site. O site tem tema azul marinho com gradiente suave. A foto vai na seção hero, lado direito, formato 3:4."*

**Ações do skill:**

1. **Analisa o site**: identifica `primary: #1e3a8a`, gradiente linear, layout hero 2 colunas
2. **Chama Nano Banana 2**:
   - Remove fundo com precisão
   - Aplica gradiente azul marinho combinando com o site
   - Ajusta iluminação para parecer foto profissional
   - Otimiza para formato 3:4
3. **Retorna foto pronta** para ser inserida no layout

## Saída Esperada

1. Foto editada em formato adequado (webp otimizado)
2. Variantes em diferentes resoluções (hero, mobile, thumbnail)
3. Metadados com instruções de posicionamento
4. CSS classes sugeridas para inserção

## Configuração Necessária

Para usar este skill, você precisa:

1. **API Key do Google AI Studio** (grátis para começar) 
2. **Instalar a extensão de navegador do Antigravity** para testes 
3. **Atualizar o pacote google-genai**:
```bash
pip install google-genai --upgrade
```
