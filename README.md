﻿# Sistema de Gestão de Obrigações Tributárias

## Capa
**Título do Projeto:** Sistema de Gestão de Obrigações Tributárias  
**Nome do Estudante:** Edson Borges Polucena  
**Curso:** Engenharia de Software  
**Data de Entrega:** 29/11/2025  

## 🧾 Resumo

Este documento apresenta a especificação do Sistema de Gestão de Obrigações Tributárias, uma solução digital desenvolvida para auxiliar escritórios contábeis e empresas no controle e organização de documentos fiscais, garantindo o cumprimento de prazos legais. O sistema permite o upload de documentos tributários, envio de notificações automáticas por e-mail, visualização de um calendário com prazos e valores a pagar, geração de relatórios e visualização de indicadores em painéis gerenciais. O objetivo é modernizar e centralizar o processo de gerenciamento tributário, promovendo maior segurança, eficiência e rastreabilidade.

---

## 1. Introdução

### Contexto

A gestão tributária é uma atividade crítica para empresas e escritórios contábeis, pois envolve o cumprimento de diversas obrigações fiscais dentro de prazos estabelecidos pela legislação. A ausência de um controle eficiente pode gerar multas, penalidades e comprometimento da credibilidade profissional.

### Justificativa

Este projeto se destaca por implementar uma ferramenta digital que utiliza tecnologias modernas para facilitar o controle e organização das obrigações tributárias, promovendo maior segurança, automação e eficiência nos processos contábeis, reduzindo falhas humanas e atrasos.

### Objetivos

#### Objetivo Geral

Desenvolver um sistema web para gerenciamento e controle digital das obrigações tributárias de empresas do Simples Nacional.

#### Objetivos Específicos

- Permitir o upload de documentos tributários pelos contadores.
- Gerar alertas automáticos para clientes sobre vencimentos e novos documentos.
- Exibir um calendário com os prazos de pagamento.
- Disponibilizar um painel com totalizadores e KPIs de impostos.
- Fornecer relatórios gerenciais e exportação de dados.
- Permitir o download de documentos pelos clientes.
- Implementar notificações multicanal (e-mail).
- Registrar logs de ações para auditoria.

---

## 2. Descrição do Projeto

### Tema do Projeto

Desenvolvimento de um sistema web para o gerenciamento de obrigações tributárias, integrando funcionalidades de upload, download, controle de prazos, notificações automáticas e relatórios gerenciais.

### Problemas a Resolver

- Falta de organização e controle centralizado de impostos.
- Esquecimento de prazos e perda de documentos importantes.
- Dificuldade na comunicação entre o escritório contábil e os clientes.
- Falta de visibilidade e rastreabilidade sobre ações realizadas.
- Falta de dados analíticos para tomada de decisão.

### Limitações

- O sistema não realiza pagamentos de impostos.
- Não substitui sistemas completos de contabilidade.
- Não realiza escrituração fiscal ou contábil.
- Inicialmente, não possui aplicativo mobile nativo.

## 3. Especificação Técnica

### 3.1 Requisitos de Software

#### Requisitos Funcionais (RF)

- RF01: Permitir upload de documentos tributários em PDF.
- RF02: Notificar clientes via e-mail sobre novos documentos e prazos de vencimento.
- RF03: Permitir o download e visualização de documentos pelo cliente.
- RF04: Exibir um calendário com prazos de vencimento e valores totais a pagar.
- RF05: Permitir o cadastro e atualização de e-mail pelos clientes.
- RF06: Permitir que usuários da contabilidade gerenciem prazos de entrega, organizados por empresas.
- RF07: Exibir alertas para documentos pendentes de upload.
- RF08: Enviar alerta de documentos não visualizados para clientes.
- RF09: Enviar alerta de documentos não visualizados para usuários da contabilidade.
- RF10: Permitir o envio manual de lembretes sobre documentos não visualizados.
- RF11: Permitir que usuários da contabilidade (permissão padrão) realizem upload, download e visualização de documentos.
- RF12: Permitir que usuários da contabilidade (permissão especial) deletem documentos postados.
- RF13: Exportar relatórios e dashboards em PDF/CSV.
- RF14: Permitir filtro de documentos por período, status, empresa e tipo.
- RF15: Registrar logs de ações (visualização, envio, download).
- RF16: Permitir comentários e anotações internas em documentos.

#### Requisitos Não Funcionais (RNF)

- RNF01: O sistema deve ser responsivo.
- RNF02: Utilizar autenticação JWT.
- RNF03: Sistema de permissões baseado em papéis.
- RNF04: Criptografia de dados sensíveis.
- RNF05: Backup automático.
- RNF06: Logs de auditoria.
- RNF07: Monitoramento de falhas com Sentry.
- RNF08: Escalabilidade com Docker e CI/CD.

---

### 3.3 Stack Tecnológica

#### React.js
Cria a interface do sistema com o conceito de SPA (Single Page Application), ou seja, sem recarregar a página constantemente. Proporciona uma experiência moderna, rápida e interativa ao usuário, facilitando a navegação entre páginas e funcionalidades.

#### Prisma ORM (opcional)
É uma ferramenta que facilita a conexão entre o sistema e o banco de dados. Ao invés de escrever comandos SQL complexos, o desenvolvedor usa uma linguagem mais simples e segura, reduzindo erros e acelerando o desenvolvimento.

#### Sentry
Ferramenta que monitora automaticamente o sistema. Sempre que um erro acontece (ex: falha de carregamento, bug em formulário), ele é capturado e enviado para análise da equipe, com detalhes do problema. Isso ajuda a corrigir bugs rapidamente e melhorar a estabilidade do sistema.

#### ESLint + Prettier
Conjunto de ferramentas usadas durante o desenvolvimento para garantir que o código seja padronizado, legível e com boa qualidade. Evita erros comuns, ajuda na colaboração entre desenvolvedores e mantém o estilo do projeto consistente.

### 3.4. Considerações de Segurança
- Criptografia para proteção de dados sensíveis.  
- Controle de permissões baseado em papéis (admin e cliente).  
- Logs de auditoria para rastrear ações críticas.  

## 4. Próximos Passos
- Implementação do backend e frontend inicial.  
- Desenvolvimento do módulo de upload de impostos.  
- Criação do sistema de notificações automáticas.  
- Integração com serviços de e-mail para envio de alertas.  

## 5. Referências

## 6. Apêndices (Opcionais)

## 7. Avaliações de Professores
**Considerações Professor/a:**  
**Considerações Professor/a:**  
**Considerações Professor/a:**
