# Aplicações ARCTM

Três aplicações num só sítio, cada uma num ficheiro HTML independente.
Não precisam de servidor, de contas nem de instalação.

## O que está aqui

    index.html          menu com as três
    pos/index.html      Registadora — vender ao balcão, caixa e relatórios
    senhas/index.html   Visor de senhas — chamada para ecrã grande
    pedidos/index.html  Visor de pedidos — em preparação e a entregar

## Publicar no GitHub Pages

1. Crie um repositório público (por exemplo `arctm`).
2. Carregue esta pasta inteira: **Add file → Upload files**, e arraste a pasta.
3. **Settings → Pages** → Source: *Deploy from a branch*, ramo `main`, pasta `/ (root)`. Guardar.
4. Ao fim de um ou dois minutos fica com:
   - `https://<utilizador>.github.io/arctm/`
   - `https://<utilizador>.github.io/arctm/pos/`
   - `https://<utilizador>.github.io/arctm/senhas/`
   - `https://<utilizador>.github.io/arctm/pedidos/`

## Sincronizar ecrãs (visores)

Nas definições de cada visor, em **Uso → Partilhar entre dispositivos**, escolha
**Sala com código** e preencha:

- **Nome da sala** — por exemplo `arctm-festa`
- **Palavra-passe da sala** — inventada por si

Todos os ecrãs com o mesmo par veem o mesmo estado. O endereço do canal nasce de
uma impressão digital desse par, e o conteúdo viaja cifrado com AES-256, por isso
quem não souber a palavra-passe não lê nem consegue injetar nada.

Notas:
- A sala precisa de internet e de a página estar em **https** (o GitHub Pages é).
- Dentro do claude.ai a sala não funciona: as páginas publicadas lá bloqueiam
  ligações a servidores externos.
- A registadora guarda tudo no próprio dispositivo. Para levar dados para outro,
  use **Definições → Dados → Exportar / Importar**.

## Cópias de segurança

- Registadora: Definições → Dados → *Exportar tudo* (eventos, produtos, vendas).
- Preferências de aspeto: *Copiar definições* em qualquer das apps, e *Colar* na outra.

## Atualizar

Substitua o ficheiro `index.html` da pasta respetiva pela versão nova e volte a
carregar no GitHub. Os dados guardados no dispositivo não se perdem.
