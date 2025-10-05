# Projeto Rebô - Assistente Virtual da Rebouças Consultoria Acadêmica

## Visão Geral
O **Rebô** é um agente de IA desenvolvido na plataforma n8n que atua como secretário virtual de atendimento inicial da Rebouças Consultoria Acadêmica. Este projeto tem como objetivo principal otimizar e automatizar o processo de triagem de clientes, direcionando-os rapidamente para os setores corretos e fornecendo informações automatizadas de forma eficiente.

## Arquitetura do Sistema

### Estrutura de Menu Hierárquico
O sistema é organizado em um **menu principal** com 5 opções centrais, cada uma contendo submenus especializados:

1. **Mestrado MUST** - 5 subopções (1A a 1E)
2. **Doutorado FICS** - 3 subopções (2A a 2C)
3. **Outros Cursos & Faculdades**
4. **Revisão de Textos**
5. **Outra Demanda Geral**

### Fluxos de Atendimento Especializados
Cada opção do menu possui fluxos específicos com:
- **Respostas automáticas** para consultas comuns
- **Gatilhos de ação** ("SIM", "CONTRATAR") para transição entre etapas
- **Coleta de dados** estruturada (nome, instituição, descrição da necessidade)
- **Encaminhamento para equipe humana** quando necessário

## Funcionalidades Principais

### 🎯 Triagem Inteligente
- Identificação automática do tipo de demanda do cliente
- Direcionamento preciso para o setor especializado
- Minimização de erros de encaminhamento

### 💰 Módulo Orçamentário
- Apresentação clara de valores e condições
- Informações sobre taxas de urgência
- Instruções de pagamento via PIX
- Links para orçamentos detalhados (Google Drive)

### 📋 Processos Automatizados
- **Comunicação de pagamento** via formulário Google
- **Solicitação de orçamentos** específicos por categoria
- **Coleta padronizada** de informações do cliente
- **Gestão de expectativas** com prazos de retorno (até 2h)

### 🔄 Respostas Especiais
- Tratamento de termos específicos como "desformatação"
- Atendimento personalizado para clientes existentes
- Solução rápida para "preciso de ajuda"

## Benefícios do Sistema

### Para a Empresa
- **Redução da carga** da equipe de atendimento
- **Padronização** das informações fornecidas
- **Otimização do tempo** de resposta inicial
- **Escalabilidade** do atendimento

### Para o Cliente
- **Atendimento 24/7** para triagem inicial
- **Informações consistentes** e confiáveis
- **Encaminhamento preciso** para o setor correto
- **Transparência** em prazos e valores

## Tecnologia e Implementação

### Plataforma: n8n
- Workflows visuais para lógica complexa
- Integração com múltiplos canais de comunicação
- Automação de respostas e encaminhamentos

### Integrações
- **Google Drive** para documentação
- **Google Forms** para coleta de dados
- **Sistemas de mensageria** para comunicação

## Métricas de Sucesso
- **145.504** interações registradas
- Tempo médio de triagem reduzido
- Taxa de encaminhamento correto aumentada
- Satisfação do cliente medido através de notas (0-10)

O projeto Rebô representa uma solução inovadora no atendimento ao cliente do setor acadêmico, combinando eficiência operacional com experiência do usuário personalizada, mantendo o padrão de qualidade da Rebouças Consultoria Acadêmica.