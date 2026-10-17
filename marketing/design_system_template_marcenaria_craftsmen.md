# System Design System - Woodcraft & Carpentry

## 1. Resumo visual curto
- **Estilo geral:** Artesanal corporativo, robusto e aquecido. Combina a solidez do trabalho em madeira com linhas limpas e modernas.
- **Sensação da UI:** Confiável, tátil, acolhedora, profissional e estruturada.
- **Tipo de site mais adequado:** Marcenarias sob medida, carpinteiros, estúdios de design de interiores, móveis planejados e artesãos.
- **Fontes gratuitas recomendadas:**
  1. **Urbanist** (Titulares e interface — geométrica, limpa e altamente legível. Sim, é perfeita para este estilo).
  2. **Plus Jakarta Sans** (Alternativa versátil para visual moderno e artesanal).
  3. **Cinzel** ou **Plus Jakarta Sans** (Para toque editorial nobre, combinada com **Inter** ou **Plus Jakarta Sans** para corpo).

---

## 1.1 Badge (.cs-topper)

```css
.cs-topper {
  font-size: 0.8125rem; 
  font-weight: 700;
  line-height: 1.2;
  text-transform: uppercase;
  letter-spacing: 0.12em;
  color: var(--primaryDark);
  background: rgba(163, 102, 38, 0.12);
  padding: 0.35rem 0.85rem;
  border: 1px solid rgba(163, 102, 38, 0.25);
  border-radius: var(--radius-xs); /* Cantos levemente suavizados, estilo marcenaria */
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
  margin-bottom: var(--space-sm);
  width: fit-content;
}

/* Variação para seções com fundo escuro (Dark Backgrounds) */
.cs-dark .cs-topper,
[data-theme="dark"] .cs-topper {
  color: var(--primaryLight);
  background: rgba(224, 160, 90, 0.15);
  border-color: rgba(224, 160, 90, 0.35);
}
```

---

## 2. Design Tokens em CSS

```css
:root {
	/* Colors */
	--primary: #A36626; /* Amadeirado quente médio / tom de mogno e nogueira */
	--primaryLight: #E0A05A; /* Tom amadeirado claro / carvalho natural */
	--primaryDark: #6E4114; /* Madeira escura / jacarandá */

	--secondary: #2C1E16; /* Escuro amadeirado profundo e elegante */
	--secondaryLight: #4A3528; /* Escuro médio com fundo terroso */
	--secondaryDark: #1A110C; /* Quase preto terroso para rodapé e backgrounds profundos */

	--accent: #C77A28; /* Destaque vibrante amarelado-âmbar */
	--accentLight: #F0B86E; /* Destaque claro suave */
	--accentDark: #8F5213; /* Destaque queimado */

	/* Backgrounds */
	--background: #F8F5F0; /* Creme claro orgânico/papel artesanal suave */
	--backgroundAlt: #FFFFFF; /* Branco puro para intercalar seções */
	--backgroundDark: #1F1510; /* Fundo escuro terroso de alto contraste */

	--surfaceColor: #FFFFFF; /* Cards claros sobre fundo off-white */
	--surfaceAltColor: #F2EDE4; /* Superfície levemente aquecida */
	--surfaceDarkColor: #2C1E16; /* Cards em áreas escuras */

	/* Text colors */
	--headerColor: #231812; /* Titulares escuros com base terrosa */
	--bodyTextColor: #54473E; /* Texto de corpo leitura macia e alto contraste */
	--mutedTextColor: #827368; /* Texto secundário e legendas */
	--bodyTextColorWhite: #F8F5F0; /* Texto claro para seções escuras */

	/* Text sizes */
	--headerFontSize: clamp(2.125rem, 4.5vw, 3.75rem);
	--bodyFontSize: 1rem;
	--smallFontSize: 0.875rem;

	/* Text heights */
	--lineHeightHeading: 1.2;
	--lineHeightBody: 1.6;

	/* Padding das seções */
	--sectionPadding: clamp(3.75rem, 7vw, 6.25rem) 1rem;

	/* Layout */
	--containerWidth: 80rem;
	--containerPadding: 1rem;
	--sectionGap: clamp(2rem, 4vw, 3.5rem);

	/* Spacing */
	--space-xs: 0.5rem;
	--space-sm: 0.75rem;
	--space-md: 1rem;
	--space-lg: 1.5rem;
	--space-xl: 2rem;
	--space-2xl: 3rem;
	--space-3xl: 4.5rem;

	/* Radius (Estrutura firme e precisa de marcenaria: cantos quase retos/sutis) */
	--radius-xs: 0.125rem;
	--radius-sm: 0.25rem;
	--radius-md: 0.375rem;
	--radius-lg: 0.5rem;
	--radius-xl: 0.75rem;
	--radius-pill: 999px;

	--buttonRadius: var(--radius-xs);
	--cardRadius: var(--radius-sm);
	--inputRadius: var(--radius-xs);
	--avatarRadius: var(--radius-pill);

	/* Borders Colors */
	--borderColor: rgba(74, 53, 40, 0.12);
	--borderColorLight: rgba(248, 245, 240, 0.15);
	--border-subtle: 1px solid var(--borderColor);
	--border-strong: 1px solid rgba(74, 53, 40, 0.28);

	/* Shadows */
	--shadow-xs: 0 2px 6px rgba(35, 24, 18, 0.04);
	--shadow-soft: 0 8px 24px rgba(35, 24, 18, 0.06);
	--shadow-medium: 0 16px 36px rgba(35, 24, 18, 0.09);
	--shadow-strong: 0 24px 50px rgba(35, 24, 18, 0.14);

	/* Cards */
	--cardBackground: var(--surfaceColor);
	--cardBackgroundAlt: var(--surfaceAltColor);
	--cardBackgroundDark: var(--surfaceDarkColor);
	--cardTextDark: var(--bodyTextColorWhite);
	--cardMutedTextDark: rgba(248, 245, 240, 0.75);
	--cardPadding: clamp(1.5rem, 3vw, 2.5rem);
	--cardBorder: var(--border-subtle);

	/* Buttons */
	--buttonHeight: 3.125rem;
	--buttonPadding: 0 2rem;

	--buttonPrimaryBg: var(--primary);
	--buttonPrimaryText: #FFFFFF;
	--buttonPrimaryHoverBg: var(--primaryDark);
	--buttonPrimaryHoverText: #FFFFFF;

	--buttonSecondaryBg: transparent;
	--buttonSecondaryText: var(--headerColor);
	--buttonSecondaryBorder: 2px solid var(--headerColor);
	--buttonSecondaryHoverBg: var(--headerColor);
	--buttonSecondaryHoverText: #FFFFFF;

	--buttonIconBg: #FFFFFF;
	--buttonIconColor: var(--primary);
	--buttonIconSize: 2.25rem;

	/* Images */
	--imageRadius: var(--radius-sm);
	--imageShadow: var(--shadow-soft);
	--imageOverlay: rgba(31, 21, 16, 0.45);
}
```

---

## 3. Regras rápidas de uso e Mapeamento CodeStitch

Substitua os valores padrão do CodeStitch por estas variáveis para manter consistência:

- **Botões:**
  - Substituir `border-radius: 4px / 8px` por `var(--buttonRadius)` (0.125rem / 2px).
  - Substituir `background-color` por `var(--buttonPrimaryBg)` ou modificadores HEX.
  - Substituir `padding` por `var(--buttonPadding)`.
- **Cards:**
  - Substituir `background` por `var(--cardBackground)` ou `var(--surfaceAltColor)`.
  - Substituir `border-radius` por `var(--cardRadius)`.
  - Substituir `padding` por `var(--cardPadding)`.
  - Substituir `box-shadow` por `var(--shadow-soft)`.
- **Seções:**
  - Substituir `padding` por `var(--sectionPadding)`.
  - Alternar backgrounds usando `var(--background)`, `var(--backgroundAlt)` e `var(--backgroundDark)`.
  - Ajustar lacunas com `var(--sectionGap)`.
- **Imagens:**
  - Substituir `border-radius` por `var(--imageRadius)`.
  - Adicionar overlays em heros/cards usando `var(--imageOverlay)`.
- **Tipografia:**
  - Substituir títulos por `font-family: 'Urbanist', sans-serif; color: var(--headerColor);`.
  - Aplicar `line-height: var(--lineHeightHeading)` em headers e `var(--lineHeightBody)` em parágrafos.
- **Layout:**
  - Definir containers principais com `max-width: var(--containerWidth)` e `padding: 0 var(--containerPadding)`.

---

## 4. Botões

```css
/* Base Button - Regras estruturais */
.cs-button {
  font-family: 'Urbanist', sans-serif;
  font-size: 0.9375rem;
  font-weight: 700;
  height: 3.125rem;
  padding: 0 2rem;
  border-radius: 0.125rem; /* Bordas retas e lapidadas, remetendo a cortes de madeira */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 1;
  overflow: hidden; 
  text-transform: uppercase;
  letter-spacing: 0.08em;
  text-decoration: none;
  border: none;
  cursor: pointer;
  
  /* Uso de variáveis locais com fallback em HEX */
  background-color: var(--btn-bg, #A36626);
  color: var(--btn-text, #FFFFFF);
  transition: color 0.3s ease;
  transition-delay: 0.05s;
}

/* Animação do Background no Hover */
.cs-button::before {
  content: "";
  width: 0;
  height: 100%;
  background-color: var(--btn-hover-bg, #6E4114);
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  transition: width 0.3s ease-in-out;
}

.cs-button:hover {
  color: var(--btn-hover-text, #FFFFFF);
}

.cs-button:hover::before {
  width: 100%;
}

/* Modificadores de Cor (Cores HEX exatas extraídas do Design) */
.cs-button-solid {
  --btn-bg: #A36626;
  --btn-text: #FFFFFF;
  --btn-hover-bg: #6E4114;
  --btn-hover-text: #FFFFFF;
}

.cs-button-light {
  --btn-bg: #FFFFFF;
  --btn-text: #231812;
  --btn-hover-bg: #A36626;
  --btn-hover-text: #FFFFFF;
  border: 1px solid #4A3528;
}

.cs-button-dark {
  --btn-bg: #2C1E16;
  --btn-text: #FFFFFF;
  --btn-hover-bg: #A36626;
  --btn-hover-text: #FFFFFF;
}