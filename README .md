# 💳 card-brand-icons

> Ícones SVG de bandeiras de cartão prontos para uso — com guias de integração para Bubble, HTML/CSS e React.

[![jsDelivr](https://img.shields.io/badge/CDN-jsDelivr-orange)](https://www.jsdelivr.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Bandeiras](https://img.shields.io/badge/bandeiras-7-green)]()

---

## 📦 Bandeiras disponíveis

| Bandeira | flat | flat-rounded | outline | dark | logo | logo-border |
|---|---|---|---|---|---|---|
| Visa | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Mastercard | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Elo | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| American Express | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Hipercard | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Diners Club | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Discover | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

---

## 🗂️ Estrutura de pastas

```
card-brand-icons/
├── icons/
│   ├── flat/           # Colorido, cantos retos — uso padrão
│   ├── flat-rounded/   # Colorido, cantos arredondados — recomendado para apps modernos
│   ├── outline/        # Contorno preto e branco — ideal para fundos coloridos
│   ├── dark/           # Mono sólido — ideal para fundos escuros
│   ├── logo/           # Apenas o logo da bandeira, sem fundo
│   └── logo-border/    # Logo com borda
├── bins.json           # Mapeamento de prefixos BIN por bandeira
└── README.md
```

Cada pasta contém os seguintes arquivos:

```
visa.svg · mastercard.svg · elo.svg · amex.svg
hipercard.svg · diners.svg · discover.svg · generic.svg
```

> 💡 `generic.svg` é o ícone de cartão padrão — use como fallback quando a bandeira não for identificada.

---

## 🚀 URLs via CDN (jsDelivr)

Substitua `ESTILO` por `flat`, `flat-rounded`, `outline`, `dark`, `logo` ou `logo-border`.

```
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/visa.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/mastercard.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/elo.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/amex.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/hipercard.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/diners.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/discover.svg
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/ESTILO/generic.svg
```

**Exemplo com flat-rounded:**
```
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/visa.svg
```

---

## 🔍 Como identificar a bandeira pelo número do cartão

A identificação é feita pelos primeiros dígitos do cartão, chamados de **BIN (Bank Identification Number)**. Consulte o arquivo [`bins.json`](./bins.json) para o mapeamento completo.

| Bandeira | Começa com |
|---|---|
| Visa | `4` |
| Mastercard | `51–55` ou `2221–2720` |
| Elo | `4011`, `4576`, `5067`, `509...`, `6362...` |
| Amex | `34` ou `37` |
| Hipercard | `606282` ou `3841` |
| Diners | `300–305`, `36` ou `38` |
| Discover | `6011`, `622...`, `644–649` ou `65` |

---

## 🛠️ Integrações

### 🟣 Bubble (No-code)

#### Passo a passo

1. Adicione um elemento **Image** na sua página onde o ícone deve aparecer
2. No campo **Dynamic image**, coloque a URL do `generic.svg` como padrão
3. Vá na aba **Conditional** do elemento e adicione as regras abaixo

#### Condicionais prontas

Considere que `Input cartao` é o campo onde o usuário digita o número do cartão.

```
Condition: Input cartao's value starts with "606282"
  OR Input cartao's value starts with "3841"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/hipercard.svg

Condition: Input cartao's value starts with "4011"
  OR Input cartao's value starts with "4576"
  OR Input cartao's value starts with "5067"
  OR Input cartao's value starts with "509"
  OR Input cartao's value starts with "6362"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/elo.svg

Condition: Input cartao's value starts with "34"
  OR Input cartao's value starts with "37"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/amex.svg

Condition: Input cartao's value starts with "300"
  OR Input cartao's value starts with "301"
  OR Input cartao's value starts with "302"
  OR Input cartao's value starts with "36"
  OR Input cartao's value starts with "38"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/diners.svg

Condition: Input cartao's value starts with "6011"
  OR Input cartao's value starts with "65"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/discover.svg

Condition: Input cartao's value starts with "51"
  OR Input cartao's value starts with "52"
  OR Input cartao's value starts with "53"
  OR Input cartao's value starts with "54"
  OR Input cartao's value starts with "55"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/mastercard.svg

Condition: Input cartao's value starts with "4"
→ Set image source to:
https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/visa.svg
```

> 💡 **Importante:** As condicionais com prefixos mais longos (ex: `606282`) devem vir **antes** das mais curtas (ex: `4`), pois o Bubble aplica a primeira regra verdadeira que encontrar.

---

### 🌐 HTML / CSS puro

```html
<div class="card-input-wrapper">
  <input
    type="text"
    id="card-number"
    placeholder="0000 0000 0000 0000"
    maxlength="19"
    oninput="detectBrand(this.value)"
  />
  <img
    id="card-icon"
    src="https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/generic.svg"
    alt="Bandeira do cartão"
  />
</div>

<style>
  .card-input-wrapper {
    position: relative;
    display: inline-flex;
    align-items: center;
  }
  .card-input-wrapper input {
    font-size: 16px;
    padding: 12px 56px 12px 12px;
    border: 1px solid #ccc;
    border-radius: 8px;
    width: 280px;
  }
  .card-input-wrapper img {
    position: absolute;
    right: 12px;
    height: 28px;
    width: auto;
    transition: opacity 0.2s ease;
  }
</style>

<script>
  const BASE_URL = "https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded";

  const brands = [
    { name: "hipercard",  pattern: /^(606282|3841)/ },
    { name: "elo",        pattern: /^(4011|4312|4389|4514|4576|5041|5066|5067|509|6362|6363)/ },
    { name: "amex",       pattern: /^3[47]/ },
    { name: "diners",     pattern: /^3(0[0-5]|[68])/ },
    { name: "discover",   pattern: /^(6011|622(12[6-9]|1[3-9]|[2-8]|9[01]|92[0-5])|64[4-9]|65)/ },
    { name: "mastercard", pattern: /^(5[1-5]|2(2[2-9][1-9]|[3-6]|7[01]|720))/ },
    { name: "visa",       pattern: /^4/ },
  ];

  function detectBrand(value) {
    const clean = value.replace(/\D/g, "");
    const found = brands.find(b => b.pattern.test(clean));
    document.getElementById("card-icon").src = `${BASE_URL}/${found ? found.name : "generic"}.svg`;
  }
</script>
```

---

### ⚛️ React / JavaScript

```jsx
import { useState } from "react";

const BASE_URL = "https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded";

const brands = [
  { name: "hipercard",  pattern: /^(606282|3841)/ },
  { name: "elo",        pattern: /^(4011|4312|4389|4514|4576|5041|5066|5067|509|6362|6363)/ },
  { name: "amex",       pattern: /^3[47]/ },
  { name: "diners",     pattern: /^3(0[0-5]|[68])/ },
  { name: "discover",   pattern: /^(6011|622(12[6-9]|1[3-9]|[2-8]|9[01]|92[0-5])|64[4-9]|65)/ },
  { name: "mastercard", pattern: /^(5[1-5]|2(2[2-9][1-9]|[3-6]|7[01]|720))/ },
  { name: "visa",       pattern: /^4/ },
];

function detectBrand(value) {
  const clean = value.replace(/\D/g, "");
  const found = brands.find((b) => b.pattern.test(clean));
  return found ? found.name : "generic";
}

export default function CardInput() {
  const [cardNumber, setCardNumber] = useState("");
  const brand = detectBrand(cardNumber);

  function formatCardNumber(value) {
    return value.replace(/\D/g, "").slice(0, 16).replace(/(.{4})/g, "$1 ").trim();
  }

  return (
    <div style={{ position: "relative", display: "inline-flex", alignItems: "center" }}>
      <input
        type="text"
        value={cardNumber}
        onChange={(e) => setCardNumber(formatCardNumber(e.target.value))}
        placeholder="0000 0000 0000 0000"
        maxLength={19}
        style={{ padding: "12px 56px 12px 12px", fontSize: 16, borderRadius: 8, border: "1px solid #ccc", width: 280 }}
      />
      <img
        src={`${BASE_URL}/${brand}.svg`}
        alt={brand}
        style={{ position: "absolute", right: 12, height: 28, width: "auto", transition: "opacity 0.2s" }}
      />
    </div>
  );
}
```

#### Hook reutilizável (`useCardBrand`)

```js
// hooks/useCardBrand.js
const brands = [
  { name: "hipercard",  pattern: /^(606282|3841)/ },
  { name: "elo",        pattern: /^(4011|4312|4389|4514|4576|5041|5066|5067|509|6362|6363)/ },
  { name: "amex",       pattern: /^3[47]/ },
  { name: "diners",     pattern: /^3(0[0-5]|[68])/ },
  { name: "discover",   pattern: /^(6011|622(12[6-9]|1[3-9]|[2-8]|9[01]|92[0-5])|64[4-9]|65)/ },
  { name: "mastercard", pattern: /^(5[1-5]|2(2[2-9][1-9]|[3-6]|7[01]|720))/ },
  { name: "visa",       pattern: /^4/ },
];

export function useCardBrand(cardNumber) {
  const clean = cardNumber.replace(/\D/g, "");
  const found = brands.find((b) => b.pattern.test(clean));
  return {
    brand: found?.name ?? "generic",
    iconUrl: `https://cdn.jsdelivr.net/gh/iagosofiatti12/card-brand-icons/icons/flat-rounded/${found?.name ?? "generic"}.svg`,
  };
}

// Uso:
// const { brand, iconUrl } = useCardBrand(cardNumber);
```

---

## 📄 bins.json

O arquivo [`bins.json`](./bins.json) contém o mapeamento completo de prefixos BIN para cada bandeira, com os campos:

- `name` — nome da bandeira
- `prefixes` — lista de prefixos BIN
- `lengths` — comprimentos de cartão aceitos
- `pattern` — regex pronta para uso

---

## 📝 Licença

MIT — livre para uso pessoal e comercial. Se usar, uma estrela no repo é sempre bem-vinda! ⭐
