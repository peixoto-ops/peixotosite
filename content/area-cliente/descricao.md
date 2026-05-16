---
title: "Área do Cliente"
date: 2026-05-16T17:43:00-03:00
draft: false
image: "down/buildings.jpg"
tags: ["segurança", "cliente"]
---

## Acesso ao FileBrowser

A plataforma de compartilhamento de documentos está disponível em **[app.luizpeixoto.com](https://app.luizpeixoto.com)**. O acesso é restrito a clientes e colaboradores previamente cadastrados, mediante autenticação de dois fatores.

## O que o cliente encontra

Ao acessar o FileBrowser, o cliente tem à disposição um diretório pessoal e intransferível onde são disponibilizados:

- Documentos do processo (petições, decisões, intimações)
- Contratos e procurações digitalizados
- Relatórios de andamento processual
- Guias de pagamento e comprovantes
- Demais arquivos pertinentes à relação advocatícia

Cada cliente enxerga exclusivamente sua própria pasta — não há compartilhamento cruzado entre pastas de diferentes clientes. O upload e download são feitos diretamente pelo navegador, sem necessidade de instalação de software adicional.

## Segurança implementada

### Autenticação com dois fatores (2FA / TOTP)

O login no FileBrowser exige senha individual **e** código de verificação gerado por aplicativo autenticador (Google Authenticator, Authy ou similar). O código TOTP (Time-based One-Time Password) é renovado a cada 30 segundos, o que torna inviável o acesso mesmo em caso de vazamento da senha.

### Criptografia em trânsito (HTTPS / TLS)

Toda a comunicação entre o navegador do cliente e o servidor é criptografada via HTTPS, com certificado SSL gerenciado pelo Certbot (Let's Encrypt). Isso garante que os dados trafeguem protegidos contra interceptação em redes públicas ou privadas.

### Conformidade com a LGPD (Lei nº 13.709/2018)

Os dados pessoais e documentos dos clientes são armazenados em servidor localizado no Brasil (datacenter da Hostinger), sob controle direto do escritório. O acesso é estritamente nominal e vinculado a cada cliente individualmente — não há tratamento compartilhado ou indiscriminado de dados. A base legal para o tratamento é o exercício regular de direito na advocacia (art. 7º, VI, da LGPD) e a execução de contrato (art. 7º, V).

### Logs de auditoria

Toda operação realizada no FileBrowser — login, upload, download, exclusão e renomeação de arquivos — é registrada em log com carimbo de data e hora, endereço IP de origem e identificação do usuário. Esses logs são retidos para eventual verificação de conformidade e podem ser disponibilizados ao cliente mediante solicitação.

### Infraestrutura

O FileBrowser roda em container Docker no VPS CERYX (2.57.91.91), com Nginx como proxy reverso e firewall configurado para bloquear tráfego não autorizado. O sistema operacional do servidor é mantido atualizado com as correções de segurança mais recentes.

## Como usar

1. Acesse **[app.luizpeixoto.com](https://app.luizpeixoto.com)**
2. Informe seu usuário e senha fornecidos pelo escritório
3. Abra o aplicativo autenticador no seu celular e digite o código TOTP exibido
4. Pronto: você está na sua pasta pessoal de documentos

Caso ainda não tenha recebido suas credenciais ou precise configurar o 2FA em um novo dispositivo, entre em contato conosco.
