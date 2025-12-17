# responsividade

# Responsividade em CSS

## Descrição

Este conteúdo reúne meus **estudos sobre responsividade**, abordando conceitos e técnicas para adaptar layouts, imagens, vídeos e elementos de acordo com diferentes tamanhos de tela.

O foco é desenvolver interfaces funcionais tanto no **desktop** quanto no **mobile**.

## Objetivo

* Entender a diferença entre layout adaptativo e responsivo
* Aplicar boas práticas de responsividade
* Trabalhar com imagens, vídeos e elementos flexíveis
* Utilizar `@media` para diferentes contextos

## Conceito de Responsividade

Todo site deve ser pensado inicialmente para desktop, **considerando desde o início como ele se comportará no mobile**, garantindo a melhor adaptação possível.

### Layout Adaptativo x Responsivo

* **Adaptativo**: usa tamanhos pré-definidos para cada resolução
* **Responsivo**: se ajusta dinamicamente ao tamanho da tela disponível

## Imagens Responsivas

* Uso de `srcset` para trocar imagens conforme a largura da tela
* Possibilidade de manter proporção usando `object-fit`

### object-fit

* `cover` → mantém o foco no centro e corta as bordas (mais usado)
* `none` → mantém o tamanho original da imagem

## Responsividade com @media

Permite reescrever propriedades conforme condições específicas:

```css
@media (parametros) {
  body {
    background-color: #ccc;
  }

  h1 {
    font-size: 15px;
  }
}
```

### Estilos para Impressão

```css
@media only print {
  body {
    background-color: #fff;
  }

  h1 {
    font-size: 10px;
  }
}
```

## Orientação de Tela

* **Portrait** → vertical
* **Landscape** → horizontal

## Aspect Ratio

Define a proporção da tela ou elemento:

* `aspect-ratio`
* `min-aspect-ratio`

Exemplos:

* `1 / 1`
* `2 / 3`
* `1 / 2`

## Variáveis CSS com @media

Uso de variáveis para facilitar mudanças:

```css
:root {
  --bg-color: #fff;
}

@media (parametros) {
  body {
    background-color: var(--bg-color);
  }
}
```

## Vídeos Responsivos

Manter a proporção original do vídeo usando containers:

```html
<div class="container">
  <div class="video-area">
    <iframe></iframe>
  </div>
</div>
```

```css
.video-area {
  position: relative;
  height: 0;
  padding: 0 0 56.25%;
}

.video-area iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}
```

## 🔧 Funções Úteis

### min() e max()

Usadas para controlar tamanhos responsivos:

* `min(valor%, valorpx, valorvh)`
* `max(valor%, valorpx, valorvh)`

### calc()

Ajusta medidas sem quebrar o layout:

```css
width: calc(100% - 20px);
width: calc(600px - 20%);
width: calc(70% - 15px);
```

##  Observações

Este material faz parte do meu processo de aprendizado contínuo em **CSS e responsividade**.

---

Conteúdo criado para estudo e prática de layouts responsivos.
