# Disk Mensagem Stúdio Neil Marcos — App (Cliente + Admin)

Este é um **aplicativo web instalável (PWA)**, gratuito, com:

- Catálogo de mensagens por categorias (bloqueio de cópia opcional)
- Pesquisa de mensagens e exibição protegida
- Cliente escolhe **música de entrada** e **música final** pelo **link do YouTube**
- Formulário completo (quem recebe, quem envia, endereço, data, hora, tipo de local)
- **Pagamento via Pix** (gera **Pix Copia & Cola** padrão BR Code totalmente offline)
- Aviso automático se a mesma mensagem foi usada (~1 ano) pelo mesmo telefone
- Botão **Enviar pelo WhatsApp** (abre conversa com o seu número)
- Painel **Admin** com PIN para:
  - Ver pedidos, marcar **pago/pendente**, **exportar CSV**
  - CRUD de **categorias** e **mensagens**
  - **Configurações** (nome do app, WhatsApp, Pix, preço, cidade, recebedor, PIN, logo)
  - **Backup/Restore** de todos os dados (.json)

> Tudo roda **100% no navegador** usando **LocalStorage** (sem servidor). Para receber pedidos de clientes, compartilhe o link/arquivo do app e peça que finalizem via WhatsApp (o pedido vem pronto por mensagem).

---

## Como usar AGORA (mais rápido)

1. Baixe o ZIP e extraia a pasta `disk-mensagem-app` no seu computador ou celular.
2. Abra o arquivo `index.html` no navegador (Chrome recomendado).
3. Use a aba **Admin** → PIN padrão: `1234` → preencha **Configurações** e **salve**.
4. Na aba **Cliente**, faça um teste de pedido. No final, clique em **Enviar pelo WhatsApp**.

> Dica: No Admin → Mensagens, crie/edite sua biblioteca (categorias, textos e códigos).

**Obs.**: Abrindo direto do arquivo (`file://`) o app funciona normal, mas o botão "Instalar" (PWA) só aparece quando estiver hospedado via HTTPS.

---

## Como publicar de graça (para instalar no celular)

Qualquer hospedagem estática grátis serve (Netlify, GitHub Pages, Cloudflare Pages).
Exemplo com **GitHub Pages**:
1. Crie uma conta no GitHub (gratuito).
2. Crie um repositório novo e envie os **arquivos da pasta** (index.html, manifest.json, sw.js e a pasta `assets/`).
3. No repositório → Settings → Pages → Branch `main` → `/root` → Save.
4. Abra o link gerado. No Android/Chrome, toque no menu ⋮ → **Instalar App**.

> Você também pode usar o **Netlify Drop** (arraste e solte a pasta) para ter um link imediato.

---

## Pix (sem taxas mensais, 100% local)

O app gera o **Pix Copia & Cola** oficial (EMV/BR Code) **offline** usando sua **chave Pix (celular)**, **valor**, **nome do recebedor** e **cidade**.  
Você confere o crédito no seu banco e marca o pedido como **pago** no painel.

> Se quiser automação (webhook), aí precisaria de um serviço externo (Stripe/Mercado Pago), que cobram taxa por transação. O app aqui evita qualquer custo fixo.

---

## Anti-cópia de mensagens

Ativado por padrão (Admin → Mensagens → "Bloquear cópia"). Isso **dificulta** copiar/colar (desativa seleção e menu). Nenhuma solução é 100% à prova de captura de tela.

---

## Segurança / Limitações

- Os dados ficam no **navegador do dispositivo** (LocalStorage). Para centralizar em vários aparelhos, exporte/importar **Backup (.json)** ou publique e peça que os clientes **enviem o pedido pelo WhatsApp** (recomendado).
- PIN do Admin padrão é `1234`. **Troque** em Configurações.
- O app aceita **links do YouTube** somente como referência da música (não toca nada automaticamente, para evitar questões de direitos autorais).

---

## Personalizações rápidas

- **Logo**: em Admin → Configurações, envie uma imagem quadrada. Ela fica salva localmente.
- **Preço**: altere em Configurações (valor da cidade). Fora da cidade fica “a combinar”.
- **Mensagens**: adicione códigos e textos conforme necessidade. O aviso de “1 ano” compara pelo **telefone do cliente + código da mensagem**.

---

## Estrutura dos arquivos

- `index.html` — Aplicativo completo (cliente + admin) com CSS/JS embutidos
- `manifest.json` — PWA manifest
- `sw.js` — Service Worker simples para cache offline (quando hospedado)
- `assets/logo.png`, `assets/icon-192.png`, `assets/icon-512.png` — ícones (troque se quiser)

Boa estreia e bons negócios! 🚀