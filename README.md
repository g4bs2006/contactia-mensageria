# Mensageria

Central de trabalho de uma equipe que atende muitas clínicas pelo WhatsApp. Cada
clínica tem um grupo, e a Mensageria junta em um lugar só as conversas, a jornada
de cada cliente, as tarefas, a agenda e as informações da conta.

> Este repositório é uma vitrine: mostra as telas e o desenho do sistema. O código
> é privado. Todos os dados dos prints são fictícios, de uma conta de demonstração.

![Conversas, com um grupo aberto](telas/02-conversas.png)

## O que ela resolve

A equipe acompanhava dezenas de grupos direto no aplicativo de mensagens. Pedido
se perdia no meio da conversa, ninguém sabia em que fase cada clínica estava, e o
combinado de uma reunião ficava só na memória de quem participou.

- **Conversas:** todos os grupos e contatos da equipe, com filtros e etiquetas.
- **Quadro:** a jornada de cada clínica, da implantação ao acompanhamento.
- **Tarefas:** o que foi combinado vira tarefa, ligada ao grupo de onde saiu.
- **Agenda:** reuniões, prazos e mensagens agendadas na mesma grade.

## Telas

### Entrada

![Tela de entrada](telas/01-entrar.png)

### Quadro das clínicas

Cada coluna é uma fase da jornada. O card mostra a última mensagem, as etiquetas,
quanto tempo o grupo espera resposta e as tarefas em aberto. O grupo abre ao lado,
sem sair do quadro.

| Quadro | Grupo aberto no quadro |
|---|---|
| ![Quadro](telas/04-quadro.png) | ![Grupo aberto](telas/05-quadro-grupo-aberto.png) |

`Ctrl K` troca de grupo ou de área de qualquer lugar.

![Trocar de grupo](telas/19-trocar-de-grupo.png)

### Tarefas

Quadro de tarefas da equipe, com prioridade, prazo, responsável, subtarefas e o
vínculo com o grupo ou com a etapa da jornada.

![Tarefas](telas/06-tarefas.png)

| Tarefa aberta | Nova tarefa |
|---|---|
| ![Tarefa aberta](telas/07-tarefa-aberta.png) | ![Nova tarefa](telas/08-nova-tarefa.png) |

### Agenda

Reuniões com as clínicas, prazos de tarefas e envios agendados, em mês, semana,
dia ou lista. A reunião marcada aqui vai para a agenda do Google de quem participa.

![Agenda do mês](telas/09-agenda-mes.png)

| Semana | Lista |
|---|---|
| ![Agenda da semana](telas/10-agenda-semana.png) | ![Agenda em lista](telas/11-agenda-lista.png) |

![Marcar reunião](telas/12-marcar-reuniao.png)

### Mensagens agendadas e mensagens prontas

Uma mensagem pode sair na hora marcada, para um ou vários grupos, uma vez ou com
repetição. As mensagens prontas guardam os textos que a equipe mais usa, com
atalho e variáveis.

| Agendamentos | Agendar mensagem |
|---|---|
| ![Agendamentos](telas/13-agendamentos.png) | ![Agendar mensagem](telas/14-agendar-mensagem.png) |

![Mensagens prontas](telas/15-mensagens-prontas.png)

### Clientes

A ficha de cada cliente em formato de planilha: os grupos, quem cuida da conta e
colunas que a própria equipe cria (texto, número, escolha, sim ou não).

![Clientes](telas/16-clientes.png)

### Cofre

As senhas da equipe e das clínicas, guardadas cifradas. Revelar uma senha fica
registrado, e ela volta a se esconder sozinha.

![Cofre](telas/17-cofre.png)

### Desenvolvimento

O caminho dos projetos da equipe: um mapa de como os sistemas se ligam, o roadmap
com os marcos, os objetivos do trimestre e uma caixa de ideias.

![Mapa dos projetos](telas/21-desenvolvimento-mapa.png)

| Roadmap | Objetivos |
|---|---|
| ![Roadmap](telas/21-desenvolvimento-roadmap.png) | ![Objetivos](telas/21-desenvolvimento-objetivos.png) |

![Caixa de ideias](telas/21-desenvolvimento-ideias.png)

### Configurações

| Colunas do quadro | Etapas das tarefas |
|---|---|
| ![Colunas do quadro](telas/22-configuracoes-quadro.png) | ![Etapas das tarefas](telas/22-configuracoes-tarefas.png) |

| Etiquetas | Equipe |
|---|---|
| ![Etiquetas](telas/22-configuracoes-etiquetas.png) | ![Equipe](telas/22-configuracoes-equipe.png) |

### Tema escuro

![Conversas no tema escuro](telas/30-escuro-conversas.png)

| Quadro | Tarefas |
|---|---|
| ![Quadro no tema escuro](telas/31-escuro-quadro.png) | ![Tarefas no tema escuro](telas/32-escuro-tarefas.png) |

### No celular

Instalável como aplicativo, com avisos no aparelho.

<p>
  <img src="telas/40-celular-conversas.png" alt="Conversas no celular" width="19%">
  <img src="telas/41-celular-conversa-aberta.png" alt="Conversa aberta no celular" width="19%">
  <img src="telas/42-celular-tarefas.png" alt="Tarefas no celular" width="19%">
  <img src="telas/43-celular-agenda.png" alt="Agenda no celular" width="19%">
  <img src="telas/44-celular-mais.png" alt="Menu Mais no celular" width="19%">
</p>

## Principais funcionalidades

- Conversas de grupo e individuais em tempo real, com texto, áudio, imagem, vídeo,
  reações, respostas e apagar para todos.
- Cada pessoa da equipe com o próprio número, vendo só os grupos dele.
- Quadro da jornada das clínicas, com colunas, etiquetas e checklist por etapa.
- Tarefas com subtarefas, dependências, anotações e horário reservado na agenda.
- Agenda com reuniões, prazos e envios, sincronizada com o Google Agenda.
- Mensagens agendadas, com repetição, e mensagens prontas com atalho.
- Planilha de clientes com colunas criadas pela equipe e visão por cargo.
- Cofre de senhas cifrado.
- Mapa, roadmap e objetivos dos projetos da equipe.
- Assistente de IA que lê as conversas e as tarefas, responde perguntas e propõe
  ações, que só acontecem depois de confirmadas por uma pessoa.
- Aplicativo instalável (PWA), com avisos no celular e tema claro ou escuro.
- Atalhos de teclado em tudo.

## Como foi construída

Um app Next.js e um processo de tarefas em segundo plano, do mesmo código.

- **Clean Architecture por módulo:** domínio puro, casos de uso e adaptadores, com
  a regra de dependência verificada automaticamente.
- **Provedor de mensagens trocável:** a ligação com o WhatsApp fica atrás de uma
  porta, e mais de um provedor atende o mesmo canal.
- **API documentada:** mais de 240 operações com contrato OpenAPI, as mesmas que a
  tela e a assistente usam.
- **Decisões registradas** em registros de decisão de arquitetura (ADRs).

| Camada | Tecnologias |
|---|---|
| Telas | Next.js 16, React 19, Tailwind 4, TanStack Query, dnd-kit |
| API | Hono, zod, OpenAPI 3.1 |
| Dados | PostgreSQL, Drizzle, pg-boss |
| Avisos | Web Push, PWA |
| Qualidade | TypeScript, Vitest, ESLint, dependency-cruiser |
| Entrega | Docker, nginx, VPS |
