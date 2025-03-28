# Sistema de Gestão de Obrigações Tributárias

## Capa
**Título do Projeto:** Sistema de Gestão de Obrigações Tributárias  
**Nome do Estudante:** Edson Borges Polucena  
**Curso:** Engenharia de Software  
**Data de Entrega:** 29/11/2025  

## Resumo
Este documento apresenta a especificação do Sistema de Gestão de Obrigações Tributárias, uma solução para auxiliar escritórios contábeis e empresas no gerenciamento de impostos. O sistema permite o upload de documentos tributários, envio de notificações automáticas para clientes e escritórios, e exibe um calendário com prazos e valores a pagar. 

## 1. Introdução
### Contexto
A gestão tributária é uma atividade crítica para empresas e escritórios contábeis, pois envolve o cumprimento de diversas obrigações fiscais dentro de prazos estabelecidos pela legislação. A ausência de um controle eficiente pode gerar multas e penalidades. 

### Justificativa
Este projeto se destaca por implementar uma ferramenta digital que utiliza tecnologias modernas para facilitar o controle e organização das obrigações tributárias, promovendo maior segurança e eficiência nos processos contábeis.

### Objetivos
- Permitir o upload de documentos tributários pelos contadores.  
- Gerar alertas automáticos para clientes sobre vencimentos e novos documentos.  
- Exibir um calendário com os prazos de pagamento.  
- Disponibilizar um painel com totalizadores de impostos.  
- Fornecer relatórios gerenciais para análise financeira.
- Permitir o download de documentos pelos clientes.  

## 2. Descrição do Projeto
### Tema do Projeto
Desenvolvimento de um sistema web para o gerenciamento de obrigações tributárias, integrando funcionalidades de upload,download, controle de prazos e alertas automáticos.

### Problemas a Resolver
- Falta de organização e controle centralizado de impostos.  
- Esquecimento de prazos e perda de documentos importantes.  
- Dificuldade na comunicação entre o escritório contábil e os clientes.  

### Limitações
- O sistema não realizará pagamentos de impostos.  
- Não substituirá sistemas completos de contabilidade.  

## 3. Especificação Técnica
### 3.1. Requisitos de Software
**Requisitos Funcionais (RF):**  
- RF01: Permitir upload de documentos tributários em PDF.  
- RF02: Notificar clientes via e-mail e WhatsApp sobre novos documentos e prazos de vencimento.  
- RF03: Permitir o download e visualização de documentos pelo cliente.  
- RF04: Exibir um calendário com prazos de vencimento e valores totais a pagar.  
- RF05: Permitir o cadastro e atualização de e-mail e WhatsApp pelos clientes.  
- RF06: Permitir que usuários da contabilidade gerenciem prazos de entrega, organizados por empresas.  
- RF07: Exibir alertas para documentos pendentes de upload.
- RF08: Enviar alerta de documentos não visualizados para clientes.
- RF09: Enviar alerta de documentos não visualizados para usuários da contabilidade.
- RF10: Permitir o envio de aviso de documentos não visualizados.
- RF11: Permitir que usuários da contabilidade (permissão padrão) realizem upload, download e visualização de documentos.  
- RF12: Permitir que usuários da contabilidade (permissão especial) deletem documentos postados.  

**Requisitos Não Funcionais (RNF):**  
- RNF01: O sistema deve ser responsivo para diferentes tamanhos de tela em ambiente desktop.  
- RNF02: Utilizar autenticação segura com JWT.  
- RNF03: Implementar um sistema de permissões para controle de ações conforme o tipo de usuário.
  

### 3.2. Considerações de Design
**Visão Inicial da Arquitetura:**  
- O sistema será baseado na arquitetura MVC.  
- Utilizará uma API REST para comunicação entre frontend e backend.  

**Padrões de Arquitetura:**  
- Utilização do padrão MVC.  
- Implementação de autenticação JWT para segurança.  

**Modelos C4:**  
- **Contexto:** Usuários acessam via navegador.  
- **Contêineres:** Backend com Node.js e Express, frontend com React e banco de dados PostgreSQL.  
- **Componentes:** Upload de arquivos, notificações e relatórios gerenciais.  

### 3.3. Stack Tecnológica
- **Linguagens:** JavaScript (Node.js, React)  
- **Banco de Dados:** PostgreSQL  
- **Frameworks e Bibliotecas:** Express.js, React, Nodemailer  
- **Ferramentas:** Docker, CI/CD (GitHub Actions)  

### 3.4. Considerações de Segurança
- Criptografia para proteção de dados sensíveis.  
- Controle de permissões baseado em papéis (admin e cliente).  
- Logs de auditoria para rastrear ações críticas.  

## 4. Próximos Passos
- Implementação do backend e frontend inicial.  
- Desenvolvimento do módulo de upload de impostos.  
- Criação do sistema de notificações automáticas.  
- Integração com serviços de e-mail e WhatsApp para envio de alertas.  

## 5. Referências

## 6. Apêndices (Opcionais)

## 7. Avaliações de Professores
**Considerações Professor/a:**  
**Considerações Professor/a:**  
**Considerações Professor/a:**
