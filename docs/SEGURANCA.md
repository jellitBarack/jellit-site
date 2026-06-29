# Segurança e antispam

## Dados sensíveis
Nunca publique senhas, tokens, secrets, chaves SSH, arquivos `.env`, dumps de banco ou dados de clientes.

## Formulário
Este site é estático. Por padrão o formulário abre WhatsApp e usa campo honeypot contra bots simples. Para envio por e-mail, configure EmailJS com template seguro e limite de domínio.

## GitHub
- Use autenticação em dois fatores.
- Não suba arquivos `.env`.
- Configure branch protection quando possível.
- Revise Pull Requests antes de merge.

## Mensagens maliciosas
- Não clique em links suspeitos.
- Não baixe anexos desconhecidos.
- Peça logs mascarados.
- Nunca execute código recebido sem análise.
