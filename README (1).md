# Encrenca! RPG de Bolso no Owlbear Rodeo

O `index.html` é o seu app de sempre (ficha, dados, tabelas, bestiário, masmorra e aventura), com uma ponte
que só liga quando ele roda **dentro do Owlbear**. Aberto direto no navegador, ele funciona exatamente como antes.

## O que muda dentro do Owlbear

- **Jogador:** usa o app normalmente. A ficha que estiver aberta é enviada para a sala a cada alteração
  (sem o histórico de alterações), e as rolagens da aba Dados e as conjurações aparecem como aviso para a mesa.
- **Mestre:** ganha uma aba **Mesa** com um cartão por jogador: Vida (com barra), PM, Sorte, armadura,
  os quatro atributos e, ao abrir o cartão, perícias, talentos, magias e itens. Atualiza em tempo real
  e mostra quem ainda não compartilhou ficha. Ela é só de leitura.
- **Recuperação:** se o navegador do jogador perder a ficha local, o app traz de volta a cópia da sala.
- **Tema:** o app acompanha o tema claro ou escuro do Owlbear.

## Colocar no ar (grátis)

Como o app é um arquivo único, qualquer hospedagem de site estático serve. Exemplo com GitHub Pages:

1. Crie um repositório público em github.com (por exemplo `encrenca`).
2. **Add file > Upload files**: envie `index.html`, `manifest.json` e `icon.svg`, e confirme.
3. **Settings > Pages**: *Deploy from a branch*, branch `main`, pasta `/ (root)`. Salve.
4. Espere um ou dois minutos. O manifest ficará em
   `https://SEU-USUARIO.github.io/encrenca/manifest.json`. Abra o link para conferir.

Se você já hospeda o app em algum lugar, basta trocar o `index.html` de lá por este e adicionar
`manifest.json` e `icon.svg` na mesma pasta. O mesmo endereço continua servindo como app normal.
Em Cloudflare Pages ou Netlify, inclua também o `_headers` (libera o acesso do Owlbear).

## Instalar

1. No Owlbear, abra o **perfil** > **Add Extension** e cole o endereço do `manifest.json`.
2. Ao criar a sala, **ative a extensão**. Ela aparece como um botão no canto superior esquerdo.

## Cuidados

- **Fichas já existentes:** cada lugar (navegador comum, app instalado, Owlbear) guarda as próprias fichas.
  Para levar uma ficha para dentro do Owlbear, use *Copiar backup* no app de fora e *Restaurar da caixa* lá dentro.
- **Confirmações:** alguns iframes bloqueiam as janelas de confirmação do navegador. Quando isso acontece,
  o app avisa na tela e pede um segundo toque na mesma ação para confirmar.
- **Espaço:** a sala guarda no máximo 16 kB de metadados no total (compartilhado com outras extensões).
  Cada ficha compartilhada usa de 0,4 a 2 kB, e o mestre vê o uso na aba Mesa.
- **Privacidade:** os dados da ficha ficam visíveis a quem sabe programar na sala. Entre amigos não costuma
  ser problema.
- O SDK do Owlbear é carregado da internet (versão 3.1.0 fixa).
