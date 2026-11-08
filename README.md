# Skills portáveis para agentes de IA

Este repositório reúne skills no formato aberto [Agent Skills](https://agentskills.io/specification). Cada skill fica em sua própria pasta e contém um `SKILL.md` com metadados `name` e `description`.

## Catálogo

| Skill | Quando usar |
| --- | --- |
| [sync-session](skills/sync-session/SKILL.md) | Ao iniciar ou retomar trabalho em um repositório após uma pausa ou outra sessão. |
| [safe-pause](skills/safe-pause/SKILL.md) | Ao pedir uma pausa, encerrar uma sessão ou chegar a 10% restantes de uma cota aplicável. |
| [orchestrate](skills/orchestrate/SKILL.md) | Para decidir se tarefas independentes se beneficiam de subagentes e integrar seus resultados. |
| [computer-use](skills/computer-use/SKILL.md) | Para operar uma interface gráfica quando o harness atual oferece ferramentas de controle visual. |
| [skill-authoring](skills/skill-authoring/SKILL.md) | Para criar ou revisar skills no formato Agent Skills. |
| [skill-installation](skills/skill-installation/SKILL.md) | Para instalar, atualizar ou remover skills em um harness compatível. |
| [harness-documentation](skills/harness-documentation/SKILL.md) | Para consultar documentação oficial atual sobre modelos, ferramentas e configuração de um harness. |

As skills de orquestração, computer use, autoria, instalação e consulta de documentação são adaptações portáveis das rotinas utilizadas no harness Codex. Não incluem comandos ou textos específicos de um fornecedor. `safe-pause` e `sync-session` são as skills de continuidade mantidas neste repositório. A skill `orchestrate` é uma reescrita independente, inspirada no caso de uso da [skill de Rafael Quintanilha](https://github.com/rafaelquintanilha/skills/tree/master/skills/orchestrate), que é voltada ao Codex e às ferramentas de colaboração dele.

As instruções não dependem de um modelo específico. A execução de ações depende das ferramentas, permissões e políticas oferecidas pelo harness: por exemplo, uma skill de orquestração não cria ferramentas de subagentes, e `computer-use` exige um recurso de controle visual.

## Instalar em clientes compatíveis

O [CLI `skills`](https://github.com/vercel-labs/skills) instala skills em vários agentes compatíveis. Ele exige Node.js e permite escolher os clientes de destino:

```sh
npx skills add Leo-alves2/skills --list
npx skills add Leo-alves2/skills --skill '*'
```

Rode o comando na raiz do projeto para instalar localmente ou acrescente `-g` para instalar no escopo do usuário. Consulte a lista atual de clientes aceitos pelo CLI; nem todo harness implementa todas as capacidades de cada skill. Se já existir uma cópia personalizada com o mesmo nome, revise as diferenças antes de substituí-la.

## Gemini CLI

O instalador nativo permite escolher cada skill e o escopo `user` ou `workspace`. Por exemplo:

```sh
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/sync-session --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/safe-pause --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/orchestrate --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/computer-use --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/skill-authoring --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/skill-installation --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/harness-documentation --scope user
gemini skills list
```

Use `--scope workspace` na raiz do projeto para restringir a instalação ao projeto. Em uma sessão aberta, recarregue as skills e confira a lista. Também é possível usar o CLI `skills` com `-a gemini-cli --copy`.

## Hermes Agent

O instalador nativo instala uma pasta por vez no perfil atual. Exemplo:

```sh
hermes skills install Leo-alves2/skills/skills/sync-session
hermes skills install Leo-alves2/skills/skills/safe-pause
hermes skills install Leo-alves2/skills/skills/orchestrate
hermes skills install Leo-alves2/skills/skills/computer-use
hermes skills install Leo-alves2/skills/skills/skill-authoring
hermes skills install Leo-alves2/skills/skills/skill-installation
hermes skills install Leo-alves2/skills/skills/harness-documentation
hermes skills list
```

## Instalação manual ou chat sem instalador

Em um cliente compatível, copie as pastas escolhidas para o diretório de skills documentado pelo harness, preservando a pasta e o arquivo `SKILL.md`. Em um chat sem suporte a skills, anexe ou cole as instruções necessárias. Nesse caso, o agente pode não ter acesso a Git, arquivos, cotas, subagentes ou controle visual.

## Uso como padrão

Configure o harness para descobrir e ativar as skills instaladas conforme suas descrições. Para continuidade em projetos, registre também esta preferência nas instruções persistentes do cliente ou do repositório:

> Aplique `sync-session` ao iniciar ou retomar trabalho no repositório, antes de editar arquivos. Aplique `safe-pause` quando eu pedir uma pausa, no encerramento planejado ou quando restarem 10% ou menos de uma cota que o ambiente consiga consultar. Use as demais skills quando a tarefa corresponder à descrição e o harness oferecer as capacidades necessárias. Preserve alterações locais e continue apenas dentro do escopo autorizado.

Essa regra orienta as sessões em que for carregada; não cria monitoramento ou execução em segundo plano.
