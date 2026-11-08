---
name: safe-pause
description: Encerra uma sessão de trabalho com segurança e prepara a retomada. Use quando o usuário pedir uma pausa, no encerramento planejado ou quando uma cota aplicável tiver 10% ou menos restantes.
---

# Pausar e preparar a retomada

Consulte cotas disponíveis antes de tarefas longas ou delegações e entre tarefas. Pause quando qualquer cota aplicável tiver **10% ou menos restantes**, ou **90% ou mais consumidos**. Use apenas janelas expostas pelo ambiente, incluindo a de 5 horas e a semanal quando existirem. Não confunda cotas com janela de contexto. Se não houver dados, informe a limitação sem estimar saldo ou renovação.

1. Pare novas tarefas e delegações. Coordene a parada de subagentes, se houver, e finalize apenas o necessário para manter o estado consistente. Preserve arquivos locais, staged e não rastreados. Registre operações pendentes, processos ativos e a última etapa de interfaces visuais, se aplicável.
2. Se estiver em um repositório Git, confira worktree, branch, HEAD e status. Atualize o acompanhamento existente quando pertinente. Registre no changelog somente alterações realizadas e verificadas. Não faça commit, push ou merge sem autorização explícita.
3. Informe as cotas e os horários de renovação conhecidos no fuso do usuário. Estime separadamente **implementação, validação e documentação**, com base no escopo, no plano e nos critérios de aceite. Explique o cálculo ou informe que a base é insuficiente.
4. Grave `handoff-<projeto>-<data>.md` no diretório temporário do ambiente, sem sobrescrever um handoff anterior. Inclua caminho do projeto, estado do Git, tarefas concluídas e pendentes, verificações e resultados, bloqueios, decisões, processos ativos, escopo autorizado e próximo passo. Inclua **Suggested Skills** com `sync-session` e outras skills pertinentes. Remova ou mascare segredos. Se não puder gravar arquivos, entregue o handoff no chat.
5. Forneça um prompt de retomada pronto para copiar. Inclua o caminho absoluto do handoff ou seu conteúdo se ele não puder ser lido na próxima sessão. Instrua o próximo agente a aplicar `sync-session`, conferir o Git e consultar as cotas antes de retomar o escopo autorizado.

Encerre a sessão após entregar o handoff. Não agende retomada automática. A próxima sessão deve respeitar a renovação real das cotas.
