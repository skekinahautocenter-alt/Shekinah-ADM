# Painel Auto Center Shekinah

Painel estático integrado à `shekinah-api`. Gerencia produtos, categorias locais e o banner do site.

## Enviar o banner

1. Entre com a senha administrativa configurada no servidor.
2. Em **Banner do site**, selecione uma arte PNG, JPG ou WebP estática de **1080 × 1080 pixels**, com até **2 MB**.
3. Preencha uma descrição acessível, confira a prévia e clique em **Publicar banner**.
4. Abra ou atualize o site para ver a imagem. O clique na arte e o CTA continuam direcionando ao WhatsApp.

**Restaurar banner padrão** remove a arte personalizada após confirmação. Imagens inválidas não substituem o banner publicado; falhas de envio mantêm a seleção para uma nova tentativa.

## Integração e publicação

- API padrão: `https://shekinah-api-mocha.vercel.app/api`.
- Site: `https://site-shekinah-six.vercel.app/` (botão Voltar ao site).
- Dependência: publique a versão da API com `/api/admin/login`, `/api/admin/session` e `/api/banner`, execute sua migração e configure os segredos antes de publicar este painel.
- O login agora é validado pelo servidor. A senha não fica no HTML; a sessão dura até 8 horas, fica em `sessionStorage` e é removida ao sair. Sessões antigas do painel não são aceitas.
- As alterações de produtos usam a mesma autenticação de banner. Leituras públicas continuam disponíveis.
- A URL da API configurada anteriormente em `shekinah_admin_api_url` continua sendo respeitada. Em testes locais, use apenas sua API isolada, nunca o banco de produção.
- A API e o site precisam receber suas alterações correspondentes. O botão Publicar banner publica a imagem no banco, não realiza deploy do código.

As categorias continuam salvas localmente, conforme o comportamento anterior.
