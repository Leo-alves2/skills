# Skills de continuidade para agentes de IA

| Skill | Quando usar |
| --- | --- |
| [sync-session](skills/sync-session/SKILL.md) | Ao iniciar ou retomar desenvolvimento em um repositório. |
| [safe-pause](skills/safe-pause/SKILL.md) | Ao encerrar, pedir uma pausa ou chegar a 10% restantes de uma cota aplicável. |

As duas seguem a [especificação Agent Skills](https://agentskills.io/specification) e não dependem de um modelo ou provedor específico. A instalação depende do aplicativo que executa o modelo. As verificações de Git, gravação de arquivos e consulta de cotas dependem das ferramentas e permissões que esse aplicativo oferece.

## Instalação em clientes compatíveis

Use o [CLI de skills](https://github.com/vercel-labs/skills) com Node.js 22.20 ou posterior:

```sh
npx skills add Leo-alves2/skills --list
npx skills add Leo-alves2/skills --skill sync-session --skill safe-pause
```

Selecione o cliente no instalador. Rode na raiz do projeto para instalação local ou acrescente `-g` para instalar no escopo de usuário dos clientes selecionados. Se já houver uma cópia local personalizada, revise as diferenças antes de substituí-la.

## Gemini CLI

Use o [instalador nativo do Gemini CLI](https://geminicli.com/docs/cli/skills/#from-the-terminal):

```sh
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/sync-session --scope user
gemini skills install https://github.com/Leo-alves2/skills.git --path skills/safe-pause --scope user
gemini skills list
```

Para limitar a instalação ao projeto atual, use `--scope workspace` na raiz do projeto. Em uma sessão aberta, use `/skills reload` e depois `/skills list`. Para orientar o uso por padrão, acrescente a regra da seção **Uso como padrão** ao `GEMINI.md` do projeto (ou a `~/.gemini/GEMINI.md` para todos os projetos do usuário).

## Hermes Agent

No perfil que você usa para desenvolvimento, utilize o [instalador nativo do Hermes](https://hermes-agent.nousresearch.com/docs/user-guide/features/skills#installing-individual-skills-directly-without-adding-a-tap):

```sh
hermes skills install Leo-alves2/skills/skills/sync-session
hermes skills install Leo-alves2/skills/skills/safe-pause
hermes skills list
```

## Instalação manual ou chat sem instalador

Em um cliente com suporte a Agent Skills, copie as duas pastas em `skills/` para o diretório de skills reconhecido pelo cliente, preservando o nome de cada pasta e o respectivo `SKILL.md`. Em um chat sem suporte a skills, anexe ou cole o conteúdo dos dois arquivos e peça ao agente para segui-los. Essa alternativa vale como instrução da sessão; o chat pode não ter acesso a Git, arquivos ou cotas.

## Uso como padrão

Após instalar, registre esta regra no arquivo de instruções do projeto ou nas preferências persistentes do cliente:

> Aplique `sync-session` ao iniciar ou retomar trabalho no repositório, antes de editar arquivos. Aplique `safe-pause` quando eu pedir uma pausa, no encerramento planejado ou quando restarem 10% ou menos de uma cota que o ambiente consiga consultar. Preserve alterações locais e continue apenas dentro do escopo autorizado.

No Hermes, você pode registrar essa preferência no perfil e abrir uma nova sessão. Use também `/sync-session` e `/safe-pause` quando a interface oferecer comandos de skill. A regra orienta a sessão ativa; ela não cria um monitor em segundo plano.
