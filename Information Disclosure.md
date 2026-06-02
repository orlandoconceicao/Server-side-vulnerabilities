# Information Disclosure

## O que é
Information Disclosure é uma vulnerabilidade onde a aplicação expõe dados sensíveis de forma não intencional, como caminhos internos, arquivos de configuração, código-fonte ou endpoints administrativos.

## Impacto
Pode permitir que um atacante descubra áreas ocultas da aplicação, como painéis administrativos, credenciais, chaves de API ou estruturas internas do sistema, facilitando ataques mais avançados.

## Como identifiquei
No lab, identifiquei a vulnerabilidade em dois pontos principais:

- robots.txt: acessei o arquivo e encontrei diretórios ocultos que não estavam visíveis na interface da aplicação.
- Source Code / JavaScript: analisei os arquivos JavaScript do site e encontrei referências a endpoints administrativos escondidos, permitindo acesso a funcionalidades restritas.

## Aprendizado
Aprendi que nem sempre a segurança está apenas na interface visível. Arquivos públicos como robots.txt e códigos JavaScript podem revelar informações críticas que ajudam a mapear toda a aplicação e encontrar superfícies de ataque.

## Ferramentas
- Burp Suite (Proxy / HTTP History / Repeater)
- Browser / DevTools (Network / Sources)
- View Page Source (HTML)
- robots.txt inspection