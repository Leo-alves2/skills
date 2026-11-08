---
name: skill-authoring
description: Cria ou revisa skills portáveis no formato Agent Skills, ajustando instruções ao propósito e às capacidades reais do harness de destino.
---

# Criar ou revisar uma skill

1. Defina o resultado que a skill deve melhorar e os pedidos que devem ativá-la. Se faltar uma informação que mude materialmente o escopo, pergunte; resolva detalhes rotineiros com bom senso.
2. Mantenha a skill focada. Inclua apenas orientações que alterem decisões ou tornem o procedimento mais confiável. Não transforme casos isolados em regras gerais.
3. Use uma pasta com nome curto em minúsculas e hífens e um `SKILL.md` com frontmatter YAML que contenha `name` e `description`. Faça o nome coincidir com a pasta. Use recursos adicionais apenas quando forem úteis à execução.
4. Escreva a descrição para indicar o que a skill faz e quando aplicá-la. No corpo, descreva objetivo, limites relevantes, ferramentas realmente disponíveis e fluxo necessário. Separe claramente requisitos de sugestões.
5. Prefira instruções compatíveis com vários harnesses. Identifique comandos, diretórios, nomes de ferramentas e políticas que sejam específicos de um produto; só os inclua quando o escopo for explicitamente esse produto, e marque essa dependência.
6. Preserve a intenção do autor e os limites de autorização. Não inclua segredos, dados pessoais, material de terceiros sem licença ou scripts que façam alterações externas sem descrever sua finalidade e efeitos.
7. Revise o frontmatter, os caminhos referenciados, o gatilho e a clareza das instruções. Quando a compatibilidade for importante, valide a estrutura com o instalador ou validador destinado ao harness escolhido e relate o que não pôde ser confirmado.

Evite arquivos auxiliares, scripts, exemplos e regras de invocação explícita sem uma necessidade concreta. Uma skill deve complementar as capacidades do agente, não prometer ferramentas ou permissões que ele não possui.
