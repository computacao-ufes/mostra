
# Site da Mostra Ufes em Computação e Tecnologia

O site da mostra é construído utilizando o framework Jekyll usando o template Minimal-Mistakes.

Para atualizar o conteúdo do site você **não** precisa conhecer Jekyll a fundo. Sabendo um pouco de Markdown e como funciona o template utilizado, que é descrito na sequência desta documentação, já é suficiente para conseguir atualizar as informações do site.

Todavia, qualquer alteração estrutural do site (por exemplo, criar um layout novo ou alterar paleta de cor) é necessário entender um pouco de desenvolvimento web, bem como aprofundar no Jekyll e no template Minimal Mistakes.

## Ferramentas utilizadas para criar o site

### Markdown
O primeiro elemento que você precisa conhecer para escrever para o site é o [Markdown](https://www.markdownguide.org). Markdown é uma ferramenta de conversão de text-to-HTML. Com ele é possível você marcar títulos, listas, tabelas, etc., de forma muito mais limpa, legível e precisa, do que se fosse fazer com HTML. Essa ferramenta é usada, por exemplo, para criar READMEs em repositórios do Github. É bem simples aprender como se usa, e [neste link](https://blog.da2k.com.br/2015/02/08/aprenda-markdown/) você encontra um bom tutorial que vai te entregar basicamente tudo que precisa.

### Jekyll
Como já foi dito, você não precisa dominar Jekyll para atualizar o site. Porém, caso queira saber o que é isso, como funcionar, para que serve, etc., você pode ler o tutorial [O que é Jekyll e para que ele serve](http://blog.virtuacreative.com.br/jekyll-for-beginners-introduction.html).

Se você quiser ir mais a fundo e aprender Jekyll, você pode assistir as [vídeos aulas disponibilizadas neste canal](https://www.youtube.com/watch?v=7lI5BfHK-kA). Porém, como Jekyll é um framework web, é necessários conhecimentos mínimos de HTML e CSS.

### Minimal Mistakes
[Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) é o nome do template/tema que utilizamos dentro do Jekyll para criar o nosso site. A ideia é que não precisamos reinventar a roda para ter algo funcinal e útil. Logo, utilizamos utilizamos o template como base a alteramos o que foi necessário para montar o site.

Uma vantagem de utilizar esse template é que a documentação dele é muito boa. Sempre que quiser fazer algo diferente no site, você pode consultá-la para verificar se já não está implementado.

Todavia, o básico para alterar o site é descrito na próxima seção.

tilizar esse template é que [a documentação dele é muito boa](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/). Sempre que quiser fazer algo diferente no site, você pode consultá-la para verificar se já não está implementado.

Todavia, o básico para alterar o site é descrito na próxima seção.


## Como criar uma nova mostra

Na `home` do site é apresentada sempre a mostra mais recente. Para criar uma nova mostra, você deve acessar o arquivo `_data/mostra.yml` e inserir uma nova entrada de informações no topo do arquivo, conforme o exemplo abaixo:

```yaml
##############################################################
# MOSTRA 2025-1
##############################################################
2025-1:
  - nome: "Projeto Integrado de Computação II"
    curso: "Engenharia de Computação"
    descricao: "Integração de Hardware e Software"
    data: "28/08/2025"
    hora: "10h às 12h"
    local: "CT-XII - Sala de Extensão"
    linkprojetos: "/eventos/PIC2-EC-20251/"

  - nome: "Projeto Integrado I"
    curso: "Ciência da Computação"
    descricao: "Sistemas Web, Apps, Games"
    data: "28/08/2025"
    hora: "10h às 12h"
    local: "CT-XII - Sala de Extensão"
    linkprojetos: "/eventos/PI-CC-20251"
```

O identificador da mostra é sempre o ano seguido do número do semestre (1 ou 2). Dentro de cada mostra, você deve inserir as informações de cada curso que participou da mostra. Este arquivo contém todo o histórico de mostras já realizadas.

Observe também que existe o campo `linkprojetos`, que deve apontar para a página onde estão listados os projetos daquela mostra. A seguir, você verá como criar essa página.

**Obs 1:** esse passo só deve ser realizado uma vez. Se a mostra já estiver criada, não é necessário fazer novamente. Basta inserir a nova disciplina no semestre corrente e seguir para o próximo passo.

**Obs 2:** o sistema considera a mostra mais recente a quele que estiver no topo do arquivo `mostra.yml`. Logo, a ordem das entradas importa. Isso afeta o que será exibido na `home` do site.

**Obs 3:** para alterar a chamada na `home` do site, você deve editar o arquivo `index.md` na raiz do repositório.


## Como criar uma disciplina para a mostra

Para criar uma nova disciplina com os projetos para a mostra é bem parecido com a criação da mostra. Você deve criar um novo arquivo `yml` dentro da pasta `_data/disciplinas/<nome-da-disciplina>`. Por exemplo, para PIC 1, já existe a pasta `pic1`, e dentro dela o arquivo `ec-20202.yml`, que contém os projetos da disciplina de Engenharia de Computação do semestre 2020/2.

Dentro deste arquivo, você deve inserir as informações dos projetos conforme o exemplo abaixo:

```yaml
##############################################################
# PIC 2 EC 2025/1
##############################################################
projetos:
  - nome: "Teclado Didático"
    autores: "Arthur Jacintho, Carlos Daniel Vieira, Daniel Sattler"
    descricao: "Construção de um teclado simples com 12 teclas, 7 notas e 5 acidentes (sustenidos), com o objetivo de familiarizar qualquer um com a dinâmica básica de um teclado real e de ensinar a tocar algumas músicas nesse instrumento."
    iframe: "https://www.youtube.com/embed/l5gIYVnVHKg?si=E4IBL_RmT0qYiAsf"
    github: "https://github.com/paisdegales/PIC-2020-2"

  - nome: "Braço Robótico Interativo"
    autores: "Alexsander Barbosa Moura, Elder Ribeiro Storck, Guilherme Dayrell Cruz Soares e Jose Vitor Rodrigues Zorzal"
    descricao: "Braço Robótico Interativo para Finalidade Educacional"
    iframe: "https://www.youtube.com/embed/zgMKTRIESYY"
    github: "https://github.com/alxsn/robotic_arm"
```

Basicamente, só é necessário inserir o nome do projeto, os autores, uma breve descrição, o link para o vídeo de apresentação (iframe do Youtube) e o link para o repositório no Github. Se não existir repositório, basta deixar o campo `github` vazio ou removê-lo.

## Como criar a página da disciplina
Para criar a página da disciplina, você deve criar um novo arquivo `.md` dentro da pasta `_pages/disciplinas/<nome-da-disciplina>`. Por exemplo, para PIC 1, já existe a pasta `PIC1`, e dentro dela o arquivo `PIC1-EC-20202.md`, que contém a página da disciplina de Engenharia de Computação do semestre 2020/2.

Dentro deste arquivo, você deve inserir o conteúdo da página conforme o exemplo abaixo:

```markdown
---
layout: splash
classes: wide
permalink: /eventos/PIC1-EC-20202/
title: "Projeto Integrado em Computação I"
---


# Projeto Integrado em Computação II - 2025/1

### Professor responsável
 - Prof. Vinícius Mota

### Links
- [Fotos da mostra](https://photos.app.goo.gl/fdzUQ4dsQ6zkwr5G7)
- [Playlist da mostra](https://www.youtube.com/playlist?list=PL-MuOHPQO5MBQ64NyYTcADtNkZ8mO-PXm)

____


# Projetos

{% include projetos.html fileyml=site.data.disciplinas.pic1.ec20202 %}
```

No topo do arquivo, existe algumas configurações do Jekyll, que são necessárias para o correto funcionamento da página. Você só precisa alterar o `permalink` e o `title` para os valores corretos. No caso do `permalink`, ele deve ser igual ao valor do campo `linkprojetos` que você colocou no arquivo `mostra.yml`. O `title` deve ser o nome da disciplina.

Depois, você pode inserir o conteúdo que quiser na página. No exemplo acima, existe uma seção para o professor responsável e links relacionados à mostra. Você pode adicionar ou remover o que achar necessário.

Para aparecer os projetos da disciplina, você deve utilizar o include `projetos.html`, passando como parâmetro o arquivo `yml` que você criou na seção anterior. A partir disso, o Jekyll irá buscar os projetos dentro do arquivo e exibi-los na página.

