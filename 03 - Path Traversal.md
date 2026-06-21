# Path Traversal

## O que é
Path Traversal é uma vulnerabilidade que permite acessar arquivos fora do diretório permitido da aplicação, manipulando caminhos de arquivos (como ../) em parâmetros de requisição.

## Impacto
Pode permitir a leitura de arquivos sensíveis do servidor, como arquivos de configuração, logs e arquivos do sistema operacional (ex: /etc/passwd), podendo expor credenciais e informações internas.

## Como identifiquei
No lab, identifiquei a falha ao testar um parâmetro que carregava arquivos no servidor. Ao modificar o valor com sequências de path traversal (../), consegui sair do diretório permitido e acessar arquivos internos do sistema.

## Aprendizado
Aprendi que validações fracas em parâmetros de arquivos podem permitir acesso a partes críticas do sistema. Também entendi a importância de filtrar e normalizar entradas antes de usá-las em operações de leitura de arquivos.

## Ferramentas
- Burp Suite (Proxy / HTTP History / Repeater)
- Browser / DevTools (Network)
- Manipulação de parâmetros na URL
- HTTP History para interceptar requisições
- Repeater para testar variações de payloads