# Quem sou eu? — Apresentação pessoal

Página de apresentação pessoal desenvolvida em **HTML, CSS e Bootstrap**, com layout **responsivo** (computador, tablet e celular).

Este projeto é a **Etapa 2** do trabalho de apresentação pessoal. Na etapa 1, a página foi feita só com HTML e CSS. Nesta etapa, ela foi aprimorada com um framework CSS (Bootstrap) e com media queries.

- **Autor:** Rauan Guilherme Faustino Abdon
- **Disciplina:** AUTORIA WEB
- **Instituição:** INSTUTO FEDERAL DE EDUCAÇÃO, CIÊNCIAS E TECNOLOGIA DO RIO GRANDE DO NORTE

---

## Sumário

1. [Sobre o projeto](#sobre-o-projeto)
2. [Tecnologias utilizadas](#tecnologias-utilizadas)
3. [Estrutura de pastas](#estrutura-de-pastas)
4. [Como executar](#como-executar)
5. [O que a página tem](#o-que-a-página-tem)
6. [Componentes do Bootstrap utilizados](#componentes-do-bootstrap-utilizados)
7. [Responsividade e media queries](#responsividade-e-media-queries)
8. [Mudanças da etapa 1 para a etapa 2](#mudanças-da-etapa-1-para-a-etapa-2)
9. [Decisões de implementação](#decisões-de-implementação)
10. [Como testar a responsividade](#como-testar-a-responsividade)
11. [Possíveis melhorias](#possíveis-melhorias)
12. [Autor](#autor)

---

## Sobre o projeto

A página apresenta o autor: quem ele é, onde mora, o que o interessa, seus links de redes sociais e o que ele gosta e por quê.

Os objetivos desta etapa foram:

- usar um framework CSS (Bootstrap);
- adaptar o layout a diferentes tamanhos de tela com **media queries**;
- melhorar a organização, a aparência e a experiência de uso da página;
- disponibilizar o código-fonte no GitHub.

---

## Tecnologias utilizadas

| Tecnologia | Para que foi usada |
|---|---|
| **HTML5** | Estrutura da página |
| **CSS3** | Estilos próprios e media queries |
| **Bootstrap 5.3.3** | Componentes e classes utilitárias (carregado por CDN) |

A página **não usa JavaScript**. O Bootstrap é usado apenas pelo CSS.

---

## Estrutura de pastas

```
QuemSouEu/
├── index.html        # Estrutura da página
├── style.css         # Estilos próprios e media queries
└── imagens/
    ├── mutano.jpg        # Foto de perfil
    ├── flamengo.png      # Favicon (ícone da aba)
    ├── instagram.webp    # Ícone do Instagram
    ├── spotify.webp      # Ícone do Spotify
    └── youtube.webp      # Ícone do YouTube
```

---

## Como executar

1. Baixe ou clone o repositório.
2. Abra a pasta `QuemSouEu`.
3. Abra o arquivo `index.html` em qualquer navegador (duplo clique).

> **Atenção:** é preciso estar conectado à internet, porque o Bootstrap é carregado por CDN. Sem internet, a página abre, mas sem os estilos do Bootstrap.

O Bootstrap está ligado por esta linha no `<head>` do `index.html`, antes do `style.css`:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
```

O link vem **antes** do `style.css` para que o CSS próprio possa sobrescrever o do Bootstrap quando necessário.

---

## O que a página tem

- **Título:** "Quem sou eu?".
- **Card de apresentação:** foto de perfil e dois parágrafos de texto.
- **Redes sociais:** links para Instagram, Spotify e YouTube, com ícones. Ao passar o mouse sobre cada ícone, aparece o nome da rede.
- **"O que eu gosto e por quê?":** uma lista com as preferências pessoais (Futebol, Tecnologia e Música) e o motivo de cada uma.
- **Ícone da aba (favicon):** o escudo do Flamengo.

---

## Componentes do Bootstrap utilizados

| Componente | Onde é usado | Classes principais |
|---|---|---|
| **Card** | Foto e parágrafos de apresentação | `card`, `card-body` |
| **List group** (horizontal) | Linha com os ícones das redes sociais | `list-group`, `list-group-horizontal`, `list-group-item` |
| **Buttons** | Cada link de rede social | `btn`, `btn-outline-secondary` |
| **List group** (vertical) | Lista de preferências ("O que eu gosto e por quê?") | `list-group`, `list-group-item`, `active` |

### Classes utilitárias do Bootstrap

| Classe | Função |
|---|---|
| `container` | Centraliza o conteúdo e adapta a largura à tela |
| `mx-auto` | Centraliza horizontalmente um bloco |
| `shadow` | Sombra no card |
| `mb-3`, `my-4` | Espaçamentos (margens) |
| `justify-content-center` | Centraliza os ícones das redes na linha |

Documentação consultada: <https://getbootstrap.com/docs/5.3/>

---

## Responsividade e media queries

A página se adapta às telas por três recursos:

1. **Meta `viewport`** no `<head>`, que faz o celular usar a largura real da tela:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
2. **`container` do Bootstrap**, que muda de largura conforme a tela.
3. **Media queries** no `style.css`, com três pontos de quebra.

### Pontos de quebra (breakpoints)

| Tela | Largura | O que muda |
|---|---|---|
| **Computador** | acima de 768px | Valores normais: foto de 300px, ícones de 70px |
| **Tablet** | até 768px | `h1` com 2rem, `h2` com 1.5rem, foto de 250px, texto com 0.95rem |
| **Celular** | até 576px | `h1` com 1.7rem, `h2` com 1.3rem, foto de 200px, texto com 0.9rem e alinhado à esquerda, ícones de 55px |
| **Celular pequeno** | até 400px | `h1` com 1.5rem, foto de 150px, ícones de 45px |

Exemplo de uma das media queries:

```css
@media (max-width: 576px) {
    h1 {
        font-size: 1.7rem;
    }

    .foto_perfil {
        width: 200px;
    }

    p {
        text-align: left;
        font-size: 0.9rem;
    }
}
```

> No celular, o texto passa de justificado para alinhado à esquerda, porque o texto justificado em telas estreitas deixa espaços grandes entre as palavras.

---

## Mudanças da etapa 2 para a etapa 3

| Elemento | Etapa 2 | Etapa 3 |
|---|---|---|
| Estilo geral | CSS escrito à mão | CSS próprio + Bootstrap |
| Foto e parágrafos | Soltos na página | Dentro de um **Card** com sombra |
| Redes sociais | `ul` com `display: flex` no CSS | **List group** horizontal, com cada link como **Button** |
| Nome das redes | Sem indicação | Texto ao passar o mouse (atributo `title`) |
| Preferências | Tabela (`<table>`) | **List group** |
| Responsividade | Sem adaptação | **Media queries** e `container` |
| Largura do conteúdo | Valores fixos | `max-width`, que se adapta à tela |

---

## Decisões de implementação

- **Sem JavaScript.** Os componentes escolhidos (Card, List group e Buttons) funcionam só com CSS. Por isso, o script do Bootstrap não foi incluído.
- **Nome das redes com `title`.** O tooltip do Bootstrap exigiria JavaScript. O atributo `title` do HTML mostra o nome ao passar o mouse, sem nenhum script.
- **List group no lugar da tabela.** O accordion do Bootstrap, que também seria uma opção, depende de JavaScript. O list group mostra todas as preferências ao mesmo tempo, sem script.
- **`max-width` em vez de `width` fixa.** Com `max-width`, o elemento cresce até o limite e encolhe se a tela for menor. Com uma largura fixa, ele ultrapassaria a tela do celular.
- **Media queries no final do CSS.** Elas ficam depois das regras normais, para sobrescrevê-las quando a tela é pequena.
- **`aria-current` nos títulos da lista.** Atributo de acessibilidade, que segue o exemplo da documentação do Bootstrap, para leitores de tela.

---

## Como testar a responsividade

1. Abra o `index.html` no navegador.
2. Aperte **F12** para abrir as ferramentas do desenvolvedor.
3. Clique no ícone de **celular/tablet** (modo responsivo).
4. Escolha um dispositivo ou arraste a largura da tela.
5. Confira o que muda perto de **768px**, **576px** e **400px**: tamanho dos títulos, da foto, dos ícones e do texto.

---

## Possíveis melhorias

- Deixar a foto de perfil perfeitamente circular (hoje ela fica oval, porque a imagem não é quadrada).
- Colocar os links reais dos perfis nas redes sociais.
- Adicionar um rodapé e um menu de navegação.
- Hospedar a página no GitHub Pages.

---

## Autor

**Rauan Guilherme Faustino Abdon**