---
name: computer-use
description: Usa uma interface gráfica visível quando APIs, ferramentas de linha de comando ou acesso a arquivos não atendem à tarefa e o harness oferece controle visual.
---

# Operar uma interface gráfica

Esta skill descreve um fluxo de trabalho; ela não fornece ferramentas de mouse, teclado ou navegador. Use somente os recursos de computer use documentados e disponíveis no harness atual.

1. Prefira APIs, CLIs e operações de arquivo quando forem suficientes. Use a interface gráfica para estados ou ações que dependam de uma janela visível.
2. Identifique a aplicação, a janela e o estado atual antes de agir. Leia as instruções da ferramenta visual do harness e use seus métodos suportados; não invente comandos, seletores ou estados ocultos.
3. Faça uma ação por vez em fluxos ambíguos e confira o resultado observado antes de prosseguir. Se uma tela ou estado não puder ser inspecionado, informe a limitação em vez de presumir sucesso.
4. Mantenha as ações dentro do escopo pedido. Antes de publicar, enviar, comprar, excluir ou alterar dados externos, confirme que essa ação foi autorizada pelo usuário para esta tarefa.
5. Não revele nem transcreva credenciais ou dados sensíveis desnecessariamente. Se um segredo aparecer na tela, não o inclua em logs, handoffs ou respostas.
6. Ao encerrar ou transferir a tarefa, registre a aplicação, a tela alcançada, as ações concluídas e o próximo passo necessário, sem guardar informação sensível.

Se não houver ferramenta visual, explique brevemente a limitação e ofereça um caminho baseado em API, CLI ou instruções para o usuário.
