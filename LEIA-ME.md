# LP Bia — Receitas da Bia

`index.html` = clone da estrutura e do design de **seupercilio.com**
(mesmas seções, mesma ordem, mesmo CSS, barra fixa, popup de saída, FAQ,
carrosséis e script de UTM), com o conteúdo do produto Receitas da Bia.

`index-v1-renato.html` = versão anterior (modelo Renato Moreira), guardada de backup.

## Como abrir
Dê dois cliques em `index.html`, ou sirva a pasta:
```
python -m http.server 8000
```

## O que trocar antes de publicar

### 1. Links de checkout (obrigatório)
No fim do `index.html`, procure `TROCAR AQUI`:
```js
var CHECKOUT_URL = 'https://pay.cakto.com.br/SEU_CODIGO_AQUI';           // R$ 29,90
var CHECKOUT_DESCONTO_URL = 'https://pay.cakto.com.br/SEU_CODIGO_POPUP'; // R$ 19,90
```
Todos os 7 botões de compra usam a primeira; o popup usa a segunda.
UTMs e fbclid são repassados automaticamente (mesmo script do original).

### 2. Depoimentos e prints (obrigatório antes de rodar anúncio)
- **Seção "Mensagens reais"**: troque `assets/feedback-placeholder.svg` por prints
  reais do direct (ex.: `assets/depoimento-1.webp`) — formato vertical.
- **Seção "Resultados reais"**: troque os textos entre `[colchetes]` por
  depoimentos reais, com nome autorizado pelo cliente.
- Enquanto não tiver depoimentos, apague as duas seções (estão marcadas com
  comentário `TROCAR` no HTML). Não invente depoimentos.

### 3. Preços (provisórios, copiados do original)
- De R$ 197,00 → R$ 29,90 (85% OFF) · 3× R$ 10,56
- Popup de saída: R$ 19,90 (abre após 2 minutos na página, timer de 10 min)
- Bônus: R$ 27 + R$ 27 + R$ 17 = R$ 71

### 4. Rodapé
Troque `contato@seudominio.com.br` e os links de Política de Privacidade e
Termos de Uso.

## O que foi diferente do original (de propósito)
- **Sem depoimentos inventados** e sem o aviso "Fulano acabou de comprar" com
  nomes aleatórios — prova social falsa e risco de bloqueio no Meta.
- **Sem promessa de cura** ("reduziu inflamação", "parei o remédio", "age em
  15 minutos"). O próprio livro da Bia nega essas promessas em todas as páginas.
- "+5.000 pessoas" virou fatos do produto (200 receitas, 5 módulos, 3 bônus,
  7 dias). Quando tiver números reais, troque na seção "Quem escreveu" e no topo.

## Imagens (`assets/`)
Fundo do topo: verde (gradiente no CSS, sem imagem).

| Arquivo                | Uso                                       |
|------------------------|-------------------------------------------|
| `bia-livro.webp`       | Topo — Bia segurando o livro              |
| `bia-cafe.webp`, `bia-carro.webp`, `bia-academia.webp` | "Quem escreveu" — carrossel (troca a cada 3,5s; para adicionar foto, coloque mais um `<img>` dentro de `#biaTrack`, formato 4:5) |
| `bonus-1..3.webp`      | Capas dos 3 bônus (dos PDFs)              |
| `feedback-placeholder.svg` | Trocar por prints reais               |
| `capa-livro.webp`      | og:image (prévia ao compartilhar o link)  |
| `hero-bg.webp`, `bia-cozinha.webp`, `bia-hero.webp`, `preview-*.webp` | Não usadas na versão atual (v1/sobras) |

As fotos originais da Bia (JPG 2K) estão na raiz da pasta.
