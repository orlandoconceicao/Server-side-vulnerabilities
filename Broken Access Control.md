# Broken Access Control

## O que é  
Broken Access Control é uma falha onde o sistema não valida corretamente as permissões do usuário, permitindo acesso não autorizado a áreas, funções ou dados restritos.

## Impacto  
Pode permitir escalonamento de privilégios, acesso ao painel administrativo, visualização ou alteração de dados de outros usuários e comprometimento da aplicação.

## Como usei  
Neste laboratório, identifiquei que o acesso ao painel admin era controlado por um cookie (`Admin=false`). Alterei manualmente esse valor para `Admin=true` usando o Burp Suite e consegui acessar a área administrativa.

## Aprendizado  
Aprendi que não se deve confiar em dados controlados pelo cliente, como cookies. A verificação de permissões deve ser feita sempre no servidor para evitar manipulações.

## Ferramentas  
- HTTP History: análise da requisição contendo cookies de sessão e privilégio  
- Repeater: modificação manual do cookie para testar escalonamento de acesso  
- Proxy: interceptação do tráfego entre navegador e servidor  
- Intercept ON/OFF: controle de captura de requisições  
- Manipulação de Cookies: alteração de `Admin=false → Admin=true` mantendo a session válida  