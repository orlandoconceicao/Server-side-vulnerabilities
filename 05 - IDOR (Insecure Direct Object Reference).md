# IDOR (Insecure Direct Object Reference)

## O que é
IDOR é uma vulnerabilidade de controle de acesso onde um usuário consegue acessar ou modificar recursos de outro usuário apenas alterando um identificador direto presente na requisição, como IDs em URLs ou parâmetros.

Nesse tipo de falha, o sistema confia no valor enviado pelo cliente sem verificar se aquele usuário realmente possui permissão para acessar o recurso solicitado.

## Impacto
Um atacante pode acessar informações privadas de outros usuários, visualizar dados de contas, modificar registros ou executar ações em nome de terceiros.

Em sistemas reais, essa vulnerabilidade pode causar exposição de dados pessoais, vazamento de informações confidenciais e comprometimento de contas.

## Como identifiquei
Durante o laboratório, foi encontrado um post no blog pertencente ao usuário Carlos. Ao observar a URL do post, foi identificado um parâmetro contendo o ID do usuário.

Após salvar esse identificador, foi realizado o login com as credenciais fornecidas e acessada a página da própria conta. Em seguida, o parâmetro "id" da requisição foi alterado para o ID do usuário Carlos.

A aplicação permitiu o acesso ao recurso de outro usuário sem realizar uma validação adequada de autorização, permitindo recuperar a chave da API associada à conta.

## Aprendizado
Aprendi que autenticação e autorização são controles diferentes. Mesmo que um usuário esteja autenticado, o sistema precisa validar se ele possui permissão para acessar cada recurso solicitado.

Também reforçou a importância de testar parâmetros manipuláveis pelo cliente, principalmente IDs presentes em URLs, requisições HTTP e APIs.

## Ferramentas
- Burp Suite (Proxy / HTTP History / Repeater)
- Browser / DevTools (se usado)