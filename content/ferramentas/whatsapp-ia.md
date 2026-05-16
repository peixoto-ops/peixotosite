---
title: "WhatsApp AI"
date: 2026-05-16T17:44:00-03:00
draft: false
image: ""
tags: ["ferramentas", "inteligência artificial", "whatsapp", "automação"]
---

## Atendimento Via Inteligência Artificial Integrado ao WhatsApp

O escritório opera um canal de atendimento via WhatsApp com suporte de inteligência artificial — não como um chatbot genérico de prateleira, mas como um **assistente alimentado pelo perfil real de atuação** do escritório, construído a partir da classificação sistemática de cada caso atendido.

### Como o Site Alimenta a IA com o Perfil Real de Atuação

O sistema de classificação CDD (Classificação Decimal de Direito) é a base de conhecimento que alimenta o assistente. Cada caso já atendido foi classificado segundo a tabela CDD, gerando um **mapa de atuação com 11 ramos do direito** extraídos de 45+ códigos CDD identificados na prática real do escritório.

Esse mapa é consolidado em um contexto que a IA carrega ao iniciar o atendimento:

```
Perfil consolidado (11 ramos):
├── Direito Civil (Obrigações, Contratos, Responsabilidade Civil)
├── Direito de Família (Alimentos, Guarda, Divórcio)
├── Direito das Sucessões (Inventários, Partilhas, Testamento)
├── Direito Imobiliário (Usucapião, Registro, Locação)
├── Direito Penal e Processual Penal (Habeas Corpus, Garantismo)
├── Direito Constitucional (Eficácia Horizontal, Direitos Fundamentais)
├── Direitos Humanos e Integridade Cognitiva
├── Direito Digital e LGPD (Responsabilidade de Plataformas, Cibersegurança)
├── Direito Administrativo e Ambiental
├── Direito do Consumidor
└── Processo Civil Estratégico e Recursal
```

Quando um cliente inicia uma conversa, o assistente consulta este perfil para **identificar a qual ramo a demanda se relaciona** e direcionar a resposta com precisão — sem palpites genéricos sobre áreas em que o escritório não atua.

### Triagem de Demandas

A primeira camada do atendimento é a triagem. O assistente IA:

1. **Escuta a descrição inicial** do problema — o cliente conta a situação com suas próprias palavras
2. **Classifica a demanda** contra o mapa de 11 ramos — identifica se o caso se enquadra em uma área de atuação real do escritório
3. **Qualifica o estágio** — consulta preliminar, caso em andamento, segunda via de documento, prazo processual
4. **Direciona** — se a demanda se encaixa no perfil, o assistente prepara o terreno para a consulta; se não se encaixa, orienta o cliente de forma transparente

A triagem não substitui a análise do advogado — é um **filtro inicial** que organiza a demanda antes do contato humano, reduzindo o tempo perdido com atendimentos que não correspondem ao perfil de atuação.

### Agendamento de Consultas

Identificada a demanda e confirmado o encaixe no perfil, o assistente:

- Apresenta ao cliente as opções disponíveis (presencial no escritório na Estrada do Capenha, 155 — Pechincha, Jacarepaguá, ou consulta remota)
- Registra a solicitação de agendamento com os dados preliminares do caso
- Dispara notificação para a agenda do escritório

O agendamento é confirmado por um operador humano — a IA organiza a demanda, não a substitui.

### Infraestrutura

O WhatsApp Router roda no **VPS CERYX** (2.57.91.91), em container Docker, utilizando a biblioteca Baileys para conexão com o WhatsApp. A comunicação é feita via webhooks, com a IA orquestrada pelo **Sistema LKE v5.0** — o mesmo que estrutura a redação de petições, pesquisas e a organização do conhecimento no escritório.

| Componente | Stack |
|:-----------|:------|
| Canal de atendimento | WhatsApp (Baileys bridge) |
| Roteamento | whatsapp-router.js (ceryx-toolkit) |
| Motor de IA | Hermes Agent / DeepSeek V4 Flash |
| Base de conhecimento | Mapa CDD de 11 ramos (45+ códigos) |
| Infraestrutura | Docker / VPS CERYX (16GB RAM) |
| Segurança | TLS, 2FA no acesso à área do cliente |

### Prática, Não Promessa

O que está descrito aqui não é um plano futuro — é o que já está rodando. O WhatsApp Router está implantado, o mapa CDD está consolidado a partir de casos reais, e a integração entre o perfil de atuação do site e o assistente IA é o elo que fecha o ciclo: **o site documenta o que o escritório faz, e a IA usa essa documentação para atender.**

Quer testar? Mande uma mensagem pelo WhatsApp — o assistente IA já sabe o que o escritório faz e pode confirmar se sua demanda se encaixa no perfil antes mesmo de você falar com um advogado.
