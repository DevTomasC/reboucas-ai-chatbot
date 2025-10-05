# 📜 Licença Autoral — Rebô (Agente Automatizado)

Copyright (c) 2025 Tomas Fernandes Correa. Todos os direitos reservados.

# 1. Direitos de Autoria

O presente software, seus fluxos, diagramas e documentação são de autoria exclusiva do criador.
É vedada qualquer tentativa de remoção, alteração ou omissão de créditos.

# 2. Permissão de Uso

É permitido usar, copiar e adaptar este projeto, desde que mantida a menção ao autor original.
A utilização é autorizada apenas para fins não comerciais, salvo acordo escrito com o autor com referêcia para contato.

# 3. Restrições

É proibida a revenda, sublicenciamento ou comercialização direta sem autorização.
É proibida a utilização para treinamento de modelos de IA proprietários sem consentimento.
É proibido o uso para fins que infrinjam a legislação vigente.

# 4. Distribuição

Qualquer redistribuição do código ou fluxos derivados deve incluir esta licença.
Projetos derivados devem conter a seguinte nota:
" Baseado no projeto , criado por Tomas Correa
 https://github.com/DevTomasC/ChatBot-Inteligente-Reboucas-Consultoria-Academica "

# 5. Garantia

Este software é fornecido no estado em que se encontra, sujeito a mudanças mediante a demandas, sem garantias de qualquer natureza, expressas ou implícitas.
O autor não se responsabiliza por perdas, danos ou consequências resultantes do uso.

# 6. Contato
Para solicitações de uso comercial, parcerias ou sublicenciamento, contatar o autor:
📧 [dev.tomas.c@gmail.com]

-------------------------------------------------------------------------------------
# PROJETO REBOUÇAS CONSULTORIA ACADÊMICA.

Este projeto implementa um agente de atendimento chamado Rebô, responsável por direcionar clientes de forma ágil e organizada.
Toda a lógica foi construída em n8n, utilizando arquitetura modular, onde cada mensagem é tratada como um objeto independente, que ao final se integra num prompt final, permitindo agilidade, no desenvolvimento e manutenção corretiva escalável sem prejudicar o projeto, pensado para garantir clareza, reuso e fácil manutenção dos componentes.

# 🏗️ Arquitetura

Base: n8n, com integração da API EvolutionAPI (não oficial);
onde os fluxos são modelados como nós independentes.
Cada nó encapsula uma função clara (entrada → processamento → resposta das requisições).
Modularidade

Cada mensagem (ex.: 1A, SIM, CONTRATAR, desformatação) é representada como um objeto autônomo.

Objetos possuem:

Intenção (ex.: orçamento, contratação, revisão).
Resposta padrão (mensagem enviada).
Ações (coleta de dados, redirecionamento, abertura de ticket).
Escalabilidade
Fácil adicionar novos fluxos sem quebrar os existentes.
Integração natural com Google Forms, Pix, GoogleDrive, Forms e abre margem para futuras integrações com CRMs via conectores do n8n.

# 📊 Fluxo de Atendimento (resumo)

Menu principal: Mestrado MUST, Doutorado FICS, Revisão, Outros.
Cada submenu possui ramificações (1A, 1B, 1C…), tratadas como objetos herdados.
Palavras-chave especiais (SIM, CONTRATAR, desformatação, preciso de ajuda) têm rotas próprias possibilita também o uso cruzado dentro dos menus.
Chamadas críticas abrem tickets com SLA de 2h.

# 🔧 Tecnologias Utilizadas

n8n → motor de automação e orquestração.

Google Gemini Flash 2.5 como modelo de linguagem adotado.

Groq para processamento de Áudio.

Evolution Api (para integração gratuita com o Whatsapp)

VsCode para rápida modularização e construção do prompt final do projeto.

Arquitetura modular de objetos → mensagens isoladas, tratadas como entidades únicas.

# Integrações nativas:

Google Drive (arquivos do cliente).

Google Forms (comunicar pagamentos).

Pix/Financeiro.


# Rebô: MENU PRINCIPAL
┌──────────────────────────────────────────────────────────────┐
│ Por favor, selecione uma das opções abaixo:                 │
│ 1️⃣ Mestrado MUST      2️⃣ Doutorado FICS   3️⃣ Outros      │
│ 4️⃣ Revisão de Textos  5️⃣ Outra Demanda                      │
└──────────────────────────────────────────────────────────────┘
      │
      ├─ 1) Mestrado MUST
      │    ┌─────────────────────────────────────────────────┐
      │    │ 1A - ORÇAMENTO WEBQUEST/FÓRUNS                  │
      │    │  ├─ Resposta: valores, instruções, Pix, taxas   │
      │    │  ├─ Gatilhos: "SIM" -> ORIENTAÇÕES PAPEIS       │
      │    │  │          "CONTRATAR" -> COLETA DADOS (->2h)  │
      │    │  └─ Campos obrigatórios: codigo, email, nome    │
      │    └─────────────────────────────────────────────────┘
      │
      │    ┌─────────────────────────────────────────────────┐
      │    │ 1B - ORÇAMENTO DISSERTAÇÃO                      │
      │    │  └─ Enviar link drive; "CONTRATAR" -> coleta    │
      │    └─────────────────────────────────────────────────┘
      │
      │    ┌─────────────────────────────────────────────────┐
      │    │ 1C - COMUNICAR PAGAMENTO                        │
      │    │  └─ Envia Google Form (link)                    │
      │    └─────────────────────────────────────────────────┘
      │
      │    ┌─────────────────────────────────────────────────┐
      │    │ 1D - ASSESSORIA REVALIDAÇÃO                     │
      │    │  └─ Valores + "CONTRATAR" -> coleta (->2h)      │
      │    └─────────────────────────────────────────────────┘
      │
      │    ┌─────────────────────────────────────────────────┐
      │    │ 1E - FALAR COM ATENDENTE                        │
      │    │  └─ Solicitar: NOME COMPLETO + INSTITUIÇÃO      │
      │    └─────────────────────────────────────────────────┘
      │
      ├─ 2) Doutorado FICS
      │    ┌─────────────────────────────────────────────────┐
      │    │ 2A - ACOMPANHAMENTO MENSAL (R$425/mês)          │
      │    │  └─ "CONTRATAR" -> coleta + retorno em 2h       │
      │    └─────────────────────────────────────────────────┘
      │
      │    ┌─────────────────────────────────────────────────┐
      │    │ 2B - ORÇAMENTO TESE                             │
      │    │  └─ Pede descrição -> "CONTRATAR" -> coleta     │
      │    └─────────────────────────────────────────────────┘
      │
      │    ┌─────────────────────────────────────────────────┐
      │    │ 2C - FALAR COM ATENDENTE                        │
      │    │  └─ Coleta dados -> retorno em 2h               │
      │    └─────────────────────────────────────────────────┘
      │
      ├─ 3) Outros Cursos & Faculdades
      │    └─ Perguntar necessidade + nome + instituicao -> equipe acionada (retorno 2h)
      │
      ├─ 4) Revisão de Textos
      │    └─ Enviar link Drive com valores -> "CONTRATAR" -> coleta (retorno 2h)
      │
      └─ 5) Outros / Demanda Geral
           └─ Solicitar descrição breve + nome + instituicao -> equipe acionada (retorno 2h)

Respostas Especiais (aterrissagem rápida)
┌──────────────────────────────────────────────────────────────┐
│ "desformatação" -> Enviar texto explicativo sobre causas +   │
│                 offer: arquivos em Word editável, não edit., │
│                 PDF; reforçar que postagem é responsabilidade│
│                 do cliente.                                  │
│ "preciso de ajuda" / "já sou cliente" -> pedir: descrição,   │
│                 nome completo, instituição (retorno 2h).     │
└──────────────────────────────────────────────────────────────┘