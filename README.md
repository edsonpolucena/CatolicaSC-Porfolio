# Sistema de Gestão de Obrigações Tributárias

## Capa
**Título do Projeto:** Sistema de Gestão de Obrigações Tributárias  
**Nome do Estudante:** Edson Borges Polucena  
**Curso:** Engenharia de Software  
**Data de Entrega:** 29/11/2025  

## 🧾 Resumo

Este documento apresenta a especificação do Sistema de Gestão de Obrigações Tributárias, uma solução digital desenvolvida para auxiliar escritórios contábeis e empresas no controle e organização de documentos fiscais, garantindo o cumprimento de prazos legais. Considerando que 27% das micro e pequenas empresas apresentavam dívidas em atraso em janeiro de 2023, e que 63% dos MEI comprometeram ao menos 30% de seus custos mensais com dívidas, o desenvolvimento de uma ferramenta que previna atrasos e multas torna-se essencial para reduzir perdas financeiras e melhorar a saúde fiscal das empresas.
O sistema permite o upload de documentos tributários, envio de notificações automáticas por e-mail, visualização de um calendário com prazos e valores a pagar, geração de relatórios e visualização de indicadores em painéis gerenciais. Em janeiro de 2024, 6,7 milhões de CNPJs encontravam-se em situação de inadimplência, totalizando R$ 127,8 bilhões em débitos, com ticket médio de R$ 2.705,20 e 7,1 contas atrasadas por empresa. O objetivo é modernizar e centralizar o processo de gerenciamento tributário, promovendo maior segurança, eficiência e rastreabilidade, minimizando a incidência de multas que chegam a 0,33% ao dia, limitadas a 20% do tributo devido.


---
---

## 1. Introdução

### Contexto

A gestão tributária é uma atividade crítica para empresas e escritórios contábeis, pois envolve o cumprimento de diversas obrigações fiscais dentro de prazos estabelecidos pela legislação. A ausência de um controle eficiente pode gerar multas moratórias de até 20% do valor do tributo e juros de 0,33% ao dia, além de danos à credibilidade e à saúde financeira do cliente.
Segundo levantamento do Sebrae em parceria com o IBGE, 27% das micro e pequenas empresas apresentavam dívidas em aberto em janeiro de 2023, ante 24% em agosto de 2022. Dentre os MEI, 63% reportaram comprometer ao menos 30% de seus custos mensais no pagamento de contas em atraso.


### Justificativa

Este projeto se destaca por implementar uma ferramenta digital que utiliza tecnologias modernas para facilitar o controle e organização das obrigações tributárias, promovendo maior segurança, automação e eficiência nos processos contábeis.
-	Redução de multas no Simples Nacional: multas de ofício podem atingir 2% do valor devido por competência, limitadas a 20% do total, e juros de 1% ao mês.
-	Mitigação de penalidades administrativas: as sanções previstas na Lei Anticorrupção variam de 0,1% a 20% do faturamento bruto anual, com limite mínimo de R$ 6.000.
-	Negociação de débitos: por meio de programas como o RELP, é possível obter até 90% de desconto em multas e juros em parcelamentos de até 180 meses.

Esses dados evidenciam que uma solução automatizada de alertas e acompanhamento de prazos pode prevenir acréscimos que, em média, custam milhares de reais por cliente e preservar a relação fiduciária entre escritórios contábeis e empresas.


### Objetivos

#### Objetivo Geral

Desenvolver um sistema web para gerenciamento e controle digital das obrigações tributárias de empresas do Simples Nacional.

#### Objetivos Específicos

-	Gerar alertas de vencimento;
    -	Enviar notificações por e-mail com pelo menos 3 dias de antecedência para 100% dos prazos cadastrados.
- Permitir upload de documentos;
  - Processar e armazenar cada arquivo em menos de 5 segundos em 95% das requisições.
- Assegurar alta disponibilidade das notificações;
  - Garantir SLA de 99% de sucesso no envio de e-mails dentro do prazo configurado.
-	Exibir calendário de prazos;
    -	Apresentar um calendário interativo com marcação de todos os vencimentos, carregado em menos de 2 segundos.
-	Disponibilizar painel de KPIs;
    -	Exibir em dashboard, em tempo real, os seguintes indicadores:
        -	% de prazos cumpridos
        -	% de alertas enviados com sucesso
        -	% de documentos processados em <5 s
-	Gerar relatórios gerenciais;
    -	Produzir relatórios mensais (PDF/CSV) que quantifiquem a redução média de multas (R$ e %) por cliente, disponíveis em até 1 minuto após o fechamento do mês.
-	Permitir download de documentos;
    -	Disponibilizar download de arquivos com tempo de resposta de até 3 segundos em 95% dos acessos.
-	Registrar logs de auditoria;
    -	Armazenar registros de todas as ações críticas (upload, alerta, download, login) com retenção mínima de 1 ano e consulta em menos de 5 segundos.


---
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

---
---

## 3. Especificação Técnica

### 3.1 Requisitos de Software

#### Requisitos Funcionais (RF)

- RF01: Permitir o cadastro e atualização de e-mail para usuários da contabilidade.
- RF02: Notificar clientes via e-mail sobre novos documentos e prazos de vencimento.
- RF03: Permitir o download e visualização de documentos pelo cliente.
- RF04: Exibir um calendário com prazos de vencimento e valores totais a pagar.
- RF05: Permitir o cadastro e atualização de e-mail pelos clientes.
- RF06: Permitir que usuários da contabilidade gerenciem prazos de entrega, organizados por empresas.
- RF07: Exibir alertas para documentos pendentes de upload.
- RF08: Enviar alerta de documentos não visualizados para clientes.
- RF09: Enviar alerta de documentos não visualizados para usuários da contabilidade.
- RF10: Permitir o envio manual de lembretes sobre documentos não visualizados.
- RF11: Permitir que usuários da contabilidade realizem upload, download e visualização de documentos.
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

### 3.1.2 Representação dos Requisitos
Nesta seção, apresentamos a representação dos Requisitos Funcionais (RF) do Sistema de Gestão de Obrigações Tributárias (SGOT) por meio de Diagramas de Casos de Uso (UML), organizados em três perfis de ator: Contador (acesso normal), Contador (acesso especial) e Cliente.

---

#### 3.1.2.1 Diagrama de Caso de Uso - Contador (Acesso Normal)
![Diagrama de Caso de Uso](diagrams/contadornormal.png)
*Figura 1: Casos de Uso para Contador (acesso normal)*

A Figura 1 apresenta as funcionalidades disponíveis ao ator **Contador (Acesso Normal)**.

- **Upload/Visualizar/baixar Documento:** permite o acesso aos documentos armazenados, e o envio de arquivos tributários em PDF (RF11).
- **Consultar Calendário:** exibe prazos e valores a pagar (RF04).
- **Filtrar Documentos:** busca por período, status, empresa e tipo (RF14).
- **Enviar Alerta Manual:** dispara lembretes manuais de documentos não visualizados (RF10).
- **Atualizar E-mail de Cliente:** gerencia informações de contato (RF05).

---

#### 3.1.2.2 Diagrama de Caso de Uso - Contador (Acesso Especial)
![Diagrama de Caso de Uso](diagrams/contadorespecial.png)
*Figura 2: Casos de Uso para Contador (acesso especial)*

A Figura 2 apresenta as funcionalidades disponíveis ao ator **Contador (Acesso Especial)**, inclui todas as funcionalidades do Contador (acesso normal), incluindo a funcionalidade abaixo.

- **Excluir Documento:** permite remoção de arquivos postados (RF12).

---

#### 3.1.2.3 Diagrama de Caso de Uso - Cliente
![Diagrama de Caso de Uso](diagrams/cliente.png)
*Figura 3: Casos de Uso para Cliente*

A Figura 3 apresenta as funcionalidades disponíveis ao ator **Cliente**.

- **Visualizar/Baixar Documento:** acesso aos arquivos compartilhados (RF03).

- **Consultar Calendário:** verifica prazos e valores (RF04).

- **Receber Notificações:** alerta sobre novos documentos e vencimentos (RF02, RF08).

- **Atualizar E-mail:** altera dados de contato (RF05).

---
---
## 3.2 Arquitetura do Sistema (C4 Model)

A seguir apresentamos a visão arquitetural do projeto utilizando o C4 Model, em dois níveis de detalhe:

### 3.2.1 Diagrama de Contexto  
Este diagrama mostra o SGOT como “caixa-preta”, os atores externos que interagem com ele e as integrações com sistemas externos (e-mail, armazenamento e monitoramento).

![Diagrama de Contexto](diagrams/diagrama-contexto-v3.png)
*Figura 4: Diagrama de Contexto do Sistema de Gestão de Obrigações Tributárias*

 **Descrição:**  
 **Contador** e **Cliente‐Empresa** interagem via HTTP/HTTPS com o sistema principal (SGOT).

**Sistema de Gestão de Obrigações Tributárias (SGOT)**  Plataforma web que centraliza todo o fluxo de documentos:
- Recebe uploads de arquivos PDF.  
- Gera e exibe calendário de prazos e valores.  
- Dispara notificações automáticas por e-mail.  
- Registra logs de auditoria e falhas.

**Serviço de E-mail (SMTP)**  
Servidor SMTP responsável pelo envio efetivo das mensagens agendadas pelo SGOT (notificações de novos documentos e lembretes de vencimento).

**Serviço de Armazenamento (S3/HTTPS)**  
Bucket S3 que guarda de forma segura e durável todos os PDFs tributários, atendendo a operações de upload e download via HTTPS.

**Sentry**  
Plataforma de monitoramento e captura de erros/exceções em tempo real; recebe relatórios de falhas do SGOT para análise e correção ágil.

---

### 3.2.2 Diagrama de Contêineres  
Neste diagrama, detalhamos todos os **contêineres** que compõem o SGOT: front-end, back-end, banco de dados, workers e serviços externos.

![Diagrama de Contêineres](diagrams/diagrama%20de%20conteiners%20v2.png)
*Figura 5: Diagrama de Contêineres do Sistema de Gestão de Obrigações Tributárias*

 **Descrição:**  
 - **Front-end (React.js):** Interface Single-Page Application responsiva, consumindo a API por REST/JSON.  
 - **API Backend (Node.js / Express + JWT):** Contém a lógica de negócios, roteamento e controle de acesso.  
- **Banco de Dados (PostgreSQL):** Armazena usuários, metadados de documentos, prazos e logs de auditoria.  
 - **Serviço de Notificações (Node.js):** Enfileira alertas e dispara e-mails a partir de uma fila de mensagens.  
- **Serviço de Logs/Auditoria (Node.js):** Registra todas as ações críticas para rastreabilidade.  
 - **Armazenamento (S3):** Bucket que guarda os PDFs tributários.  
 - **SMTP (Servidor de e-mail):** Responsável pelo envio efetivo das mensagens.  
 - **Sentry:** Plataforma de monitoramento de erros e exceções.

---

<!-- ### 3.2.3 Diagrama de Componentes (Backend)  
Aqui aprofundamos no **API Backend**, mostrando seus principais componentes (controllers e services) e como eles se interligam.

![Diagrama de Componentes](diagrams/diagrama%20de%20conteiners%20do%20backend%20v2.png)
*Figura 6: Diagrama de Componentes do API Backend*

**Descrição:**

- **ControladorAutenticacao**  
  Responsável pelo fluxo de autenticação: recebe credenciais, valida usuário, gera e retorna o token JWT.  
  **Interface:** autenticar(credenciais): JWT

- **ControladorDocumento**  
  Gerencia operações de documentos: upload de PDFs no S3, download via URL pré-assinada e consulta de metadados.  
  **Interfaces:**  
  - enviarDocumento(arquivo): URL  
  - baixarDocumento(id): Stream  
  - obterMetadados(id): Metadados

- **ControladorCalendario**  
  Expõe endpoint para listar prazos e valores associados a uma empresa.  
  **Interface:** listarPrazos(empresaId): Prazo[]

- **MiddlewarePermissao**  
  Intercepta requisições antes dos controllers para verificar papéis e escopos de acesso.  
  **Interface:** verificarPermissao(usuario, acao): boolean

- **ServicoRelatorio**  
  Gera relatórios e dashboards a partir dos dados armazenados e oferece exportação em PDF ou CSV.  
  **Interfaces:**  
  - gerarRelatorio(parametros): PDF  
  - exportarCSV(parametros): CSV

- **ServicoLogAuditoria**  
  Registra em banco de dados cada ação crítica (login, upload, download, consulta de prazos, exportação).  
  **Interface:** registrarAcao(acao, usuario, detalhes): void

- **ServicoNotificacao**  
  Publica eventos de alerta em uma fila e dispara notificações por e-mail ou webhook.  
  **Interfaces:**  
  - enfileirarEmail(alerta): void 
  - enfileirarWebhook(evento): void

- **RepositorioUsuario**  
  Camada de persistência para operações com entidade usuário (busca, criação e atualização).  
  **Interfaces:**  
  - buscarPorId(id): Usuario  
  - salvar(usuario): void

- **RepositorioDocumento**  
  Abstrai o acesso ao PostgreSQL para salvar, buscar e excluir metadados de documentos.  
  **Interfaces:**  
  - salvarDocumento(metadados): void  
  - buscarDocumento(id): Documento 
  - excluirDocumento(id): void

- **AdaptadorS3**  
  Encapsula a lógica de integração com o bucket S3: upload de arquivos e geração de URLs pré-assinadas.  
  **Interfaces:**  
  - enviar(arquivo, chave): URL  
  - gerarUrlAssinada(chave): URL

- **AdaptadorEmail**  
  Cliente SMTP para envio de e-mails gerados pelo ServicoNotificacao.  
  **Interface:** enviarEmail(opcoes): void

- **AdaptadorSentry**  
  Conecta-se ao Sentry para capturar e reportar exceções lançadas pelo backend.  
  **Interface:** capturarExcecao(erro): void

- **ServicoConfiguracao**  
  Centraliza o carregamento de variáveis de ambiente e outras configurações de aplicação.  
  **Interface:** obter(chave): string

- **TratadorErros**  
  Middleware global que intercepta exceções, formata respostas de erro e aciona o AdaptadorSentry.  
  **Interface:** tratar(erro, req, res, next): void -->


### 3.3 Stack Tecnológica

#### React.js
Cria a interface do sistema com o conceito de SPA (Single Page Application), ou seja, sem recarregar a página constantemente. Proporciona uma experiência moderna, rápida e interativa ao usuário, facilitando a navegação entre páginas e funcionalidades.

#### Prisma ORM (opcional)
É uma ferramenta que facilita a conexão entre o sistema e o banco de dados. Ao invés de escrever comandos SQL complexos, o desenvolvedor usa uma linguagem mais simples e segura, reduzindo erros e acelerando o desenvolvimento.

#### Sentry
Ferramenta que monitora automaticamente o sistema. Sempre que um erro acontece (ex: falha de carregamento, bug em formulário), ele é capturado e enviado para análise da equipe, com detalhes do problema. Isso ajuda a corrigir bugs rapidamente e melhorar a estabilidade do sistema.

#### ESLint + Prettier
Conjunto de ferramentas usadas durante o desenvolvimento para garantir que o código seja padronizado, legível e com boa qualidade. Evita erros comuns, ajuda na colaboração entre desenvolvedores e mantém o estilo do projeto consistente.

---

### 3.4. Considerações de Segurança
- Criptografia para proteção de dados sensíveis.  
- Controle de permissões baseado em papéis (admin e cliente).  
- Logs de auditoria para rastrear ações críticas.  

---
---
## 4. Próximos Passos
- Implementação do backend e frontend inicial.  
- Desenvolvimento do módulo de upload de impostos.  
- Criação do sistema de notificações automáticas.  


## 5. Referências

## 6. Apêndices (Opcionais)

## 7. Avaliações de Professores
**Considerações Professor/a:**  
**Considerações Professor/a:**  
**Considerações Professor/a:**
