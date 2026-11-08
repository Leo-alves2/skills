---
name: sync-session
description: Reconcilia o estado de um repositório ao iniciar ou retomar desenvolvimento após uma pausa, outra sessão ou outro agente. Use antes de editar código nesses casos.
---

# Sincronizar sessão

1. Leia as instruções do projeto e identifique o diretório e o worktree corretos. Confira branch, HEAD, últimos cinco commits e `git status`. Distinga alterações staged, unstaged e arquivos não rastreados. Se Git estiver indisponível ou ainda não houver commits, registre a limitação.
2. Leia o handoff indicado pelo usuário. Se nenhum for indicado, procure `handoff-<projeto>-*.md` no diretório temporário do ambiente. Confirme o repositório e o worktree antes de usar o arquivo. Se não estiver acessível neste ambiente, solicite o conteúdo quando necessário. Use o handoff como contexto; confirme suas afirmações pelo estado atual.
3. Consulte as tarefas ativas, critérios de aceite e decisões pertinentes. Reconcilie diferenças entre o handoff, os arquivos e o Git. Preserve o trabalho local e de outros agentes. Um handoff não amplia a autorização.
4. Se houver uma verificação local rápida e pertinente, inspecione o comando antes de rodá-lo. Execute apenas quando seguro e dentro do escopo; evite serviços compartilhados, produção e dados reais. Relate falhas observadas antes das edições sem presumir a causa.
5. Informe o estado da branch e das verificações, o que mudou, a tarefa ativa, os bloqueios e o próximo passo recomendado. Prossiga se ele já estiver autorizado. Faça uma pergunta objetiva apenas se uma dúvida material impedir o avanço.

Confira as cotas disponíveis antes de retomar operações longas. Se estiverem no limite definido para pausa, use `safe-pause` quando disponível. Não execute commit, push ou merge sem autorização explícita.
