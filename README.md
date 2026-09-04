# Aplicações ARCTM

Três aplicações para eventos e balcão, cada uma num único ficheiro HTML.
Sem servidor, sem contas, sem instalação: abrem em qualquer browser e
funcionam mesmo sem internet.

| | Aplicação | Para que serve |
|---|---|---|
| 🧾 | [`pos/`](pos/) | **Registadora** — vender ao balcão, movimentos de caixa e relatórios por evento |
| 🔢 | [`senhas/`](senhas/) | **Visor de senhas** — chamada de senhas num ecrã grande |
| 🍽️ | [`pedidos/`](pedidos/) | **Visor de pedidos** — o que está em preparação e o que está a entregar |

## Publicar

Este repositório é servido pelo GitHub Pages.

1. **Settings → Pages**
2. *Source*: **Deploy from a branch**, ramo `main`, pasta `/ (root)`
3. Guardar e esperar um ou dois minutos

Os endereços ficam assim:

```
https://<utilizador>.github.io/<repositório>/          menu
https://<utilizador>.github.io/<repositório>/pos/      registadora
https://<utilizador>.github.io/<repositório>/senhas/   visor de senhas
https://<utilizador>.github.io/<repositório>/pedidos/  visor de pedidos
```

## Sincronizar vários ecrãs

Nos visores, em **Definições → Uso → Partilhar entre dispositivos**, escolha
**Sala com código** e preencha nos dois ecrãs:

- **Nome da sala** — por exemplo `arctm-festa`
- **Palavra-passe da sala** — inventada por si

Todos os ecrãs com o mesmo par passam a ver o mesmo estado: o que se chama num,
aparece no outro.

**Como está protegido.** O endereço do canal nasce de uma impressão digital do
nome com a palavra-passe, por isso não se adivinha. As mensagens viajam cifradas
com AES-256, com a chave derivada da palavra-passe, e uma mensagem que não abra
com essa chave é ignorada — ninguém de fora lê nem consegue injetar números.

Para quem tiver servidor próprio, há em **Servidor de mensagens (avançado)** os
campos de endereço, utilizador e palavra-passe.

### Limitações

- A sala precisa de internet e de a página estar em `https` — o GitHub Pages é.
- Dentro do claude.ai a sala não funciona: as páginas publicadas lá bloqueiam
  ligações a servidores externos.
- A registadora guarda tudo no dispositivo onde corre. Para passar dados para
  outro, use **Definições → Dados → Exportar / Importar**.

## Proteger com palavra-passe

As páginas do GitHub Pages são públicas. Para as fechar, use a ferramenta
[`proteger.html`](proteger.html) — abra-a **no seu computador**, não a publique.

Ela cifra a aplicação inteira com AES-256 a partir de uma palavra-passe sua e
devolve um `index.html` protegido. Quem abrir a página vê só o pedido de
palavra-passe; quem descarregar o ficheiro encontra ruído.

1. Abra `proteger.html` no browser (duplo clique chega).
2. Escolha o `index.html` da aplicação, defina a palavra-passe e gere.
3. Substitua o ficheiro original pelo protegido, na pasta respetiva.
4. Repita para cada aplicação — as palavras-passe podem ser diferentes.

Nos ecrãs fixos, marque *Lembrar neste dispositivo* na primeira vez: passam a
abrir sozinhos, e os outros continuam a precisar da palavra-passe.

**Guarde a palavra-passe.** Sem ela não há como recuperar o conteúdo do ficheiro
protegido — o original fica sempre disponível aqui, mas o protegido não se abre.

## Cópias de segurança

- **Dados de vendas** — Registadora → Definições → Dados → *Exportar tudo*
  (eventos, produtos, vendas e movimentos de caixa num ficheiro).
- **Preferências de aspeto** — *Copiar definições* num dispositivo e
  *Colar definições* no outro, em qualquer das três aplicações.

## Atualizar

Substitua o `index.html` da pasta respetiva pela versão nova e volte a carregar.
Os dados guardados em cada dispositivo não se perdem, porque vivem no browser e
não nos ficheiros.

## Privacidade

Nada é enviado para lado nenhum sem ser pedido. As vendas, os produtos e as
imagens ficam no armazenamento local do browser de cada dispositivo. A única
comunicação para fora é a sala de sincronização, quando a liga, e mesmo essa vai
cifrada.
