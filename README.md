# Orçamento Genesis Tecnologia

Este projeto é uma página HTML pronta para publicar ou enviar como link de orçamento.

## O jeito mais fácil quando você só consegue copiar e colar

Se você não conseguiu baixar o arquivo e só consegue copiar o conteúdo, faça assim:

1. Abra o arquivo `index.html` no GitHub, no editor ou onde ele estiver aparecendo.
2. Copie **somente o HTML puro**, começando exatamente por:

```html
<!DOCTYPE html>
```

3. O final do arquivo precisa terminar exatamente com:

```html
</html>
```

4. Não copie linhas que começam com `+`, `-`, `@@`, `diff --git`, `index`, `---` ou `+++`.
5. Abra o Bloco de Notas.
6. Cole o conteúdo copiado.
7. Clique em **Arquivo > Salvar como**.
8. Em **Tipo**, escolha **Todos os arquivos**.
9. Em **Nome**, coloque exatamente:

```text
orcamento-genesis.html
```

10. Em **Codificação**, escolha **UTF-8**, se aparecer essa opção.
11. Salve na Área de Trabalho.
12. Dê dois cliques no arquivo `orcamento-genesis.html`.

Pronto: ele deve abrir como uma página bonita no navegador.

## Se abriu mostrando código na tela

Isso normalmente significa uma destas coisas:

- O arquivo foi salvo como `orcamento-genesis.html.txt`, e não como `.html` de verdade.
- Você copiou o **patch/diff** em vez do HTML puro.
- Você copiou texto com sinais `+` no começo das linhas.
- Você copiou um bloco de Markdown com ```html no início ou ``` no fim.

Para corrigir:

1. Ative a visualização de extensões no Windows Explorer.
2. Confira se o arquivo termina em `.html`.
3. Se estiver como `.html.txt`, renomeie para `orcamento-genesis.html`.
4. Abra o arquivo no Bloco de Notas e confirme se a primeira linha é apenas `<!DOCTYPE html>`.
5. Confirme que não existe ```html, ``` ou `diff --git` dentro do arquivo.

## Se abriu um link estranho ou uma página nada a ver

Isso geralmente acontece quando foi salvo um **link**, uma página do GitHub, uma página de patch ou um atalho, em vez do conteúdo real do HTML.

O arquivo certo precisa conter código HTML começando com `<!DOCTYPE html>` e terminando com `</html>`.


## Se você só está vendo linhas com `+`

Você está na tela de **patch/diff**, não no arquivo HTML final. Nessa tela, o GitHub mostra cada linha nova começando com `+`. Se você copiar assim e salvar como `.html`, o navegador não vai entender direito.

### Melhor solução: abrir o arquivo em modo Raw

1. Entre no arquivo `index.html` fora da tela de patch.
2. Procure um botão chamado **Raw** ou **Download raw file**.
3. Clique nele.
4. A página vai abrir mostrando somente o HTML puro, sem os sinais `+`.
5. A primeira linha deve ser `<!DOCTYPE html>`.
6. Pressione `Ctrl + S`.
7. Salve como `orcamento-genesis.html`.
8. Depois dê dois cliques no arquivo salvo.

Se aparecer uma URL parecida com GitHub, normalmente o caminho certo é trocar `/blob/` por `/raw/` na barra de endereço.

### Se não tiver botão Raw e você só conseguir copiar o patch

Dá para resolver, mas você precisa limpar o patch antes de salvar:

1. Copie o patch inteiro.
2. Cole em um arquivo chamado `patch.txt`.
3. Abra o PowerShell na pasta onde salvou o `patch.txt`.
4. Rode este comando:

```powershell
Get-Content .\patch.txt | Where-Object { $_ -like '+*' -and $_ -notlike '+++*' } | ForEach-Object { $_.Substring(1) } | Set-Content -Encoding UTF8 .\orcamento-genesis.html
```

5. Abra o arquivo `orcamento-genesis.html`.
6. Se a primeira linha não for `<!DOCTYPE html>`, apague tudo antes dela.
7. Se tiver conteúdo depois de `</html>`, apague tudo depois.
8. Salve e dê dois cliques no arquivo.

### Se o texto copiado começa com link da imagem/logo

Isso significa que você começou a copiar do meio do arquivo, não do começo. O HTML certo começa antes das imagens. Procure a primeira linha `<!DOCTYPE html>` e copie desde ela até a última linha `</html>`.

## Como abrir o orçamento

Você tem três formas simples de visualizar o arquivo `index.html`:

### Opção 1: abrir direto no navegador

1. Baixe ou abra a pasta do projeto no seu computador.
2. Encontre o arquivo `index.html`.
3. Dê dois cliques no arquivo.
4. Ele deve abrir automaticamente no Chrome, Edge, Firefox ou Safari.

Essa é a forma mais rápida para conferir o visual.

### Opção 2: abrir pelo VS Code com Live Server

1. Abra a pasta do projeto no VS Code.
2. Instale a extensão **Live Server**, caso ainda não tenha.
3. Clique com o botão direito no arquivo `index.html`.
4. Clique em **Open with Live Server**.

Essa opção é boa quando você quer editar e ver as mudanças atualizando no navegador.

### Opção 3: abrir com servidor local pelo terminal

Se você estiver na pasta do projeto, rode:

```bash
python3 -m http.server 8000
```

Depois abra no navegador:

```text
http://localhost:8000
```

Para parar o servidor, volte no terminal e pressione `Ctrl + C`.

## Arquivo principal

- `index.html`: página completa do orçamento com layout, textos, imagens, valor, condições de pagamento e botão de aprovação via WhatsApp.

## Botão do WhatsApp

O botão de aprovação abre uma conversa com Rechard no número `(22) 99957-7703` e já deixa a mensagem pronta:

```text
Orçamento aprovado! gostaria de fazer o serviço!
```

## Publicar em um site

Para colocar público em um site, basta enviar o arquivo `index.html` para a hospedagem ou publicar o repositório em uma plataforma de site estático, como GitHub Pages, Netlify ou Vercel.
