---
name: skill-installation
description: Instala, atualiza ou remove skills em um harness quando o usuário pede configuração ou reutilização de skills.
---

# Instalar skills em um harness

1. Identifique o harness, o escopo desejado (projeto ou usuário) e a origem da skill. Se algum desses pontos estiver ausente, consulte as configurações locais ou a documentação oficial; pergunte somente se a escolha mudar o destino ou puder substituir trabalho existente.
2. Inspecione a origem antes de instalar: leia o `SKILL.md`, confira arquivos auxiliares e scripts, identifique a licença e confirme que a origem e o escopo correspondem ao pedido.
3. Prefira o instalador oficial ou uma ferramenta compatível com o harness. Use apenas comandos e opções documentados para a versão disponível. Se não houver instalador, copie a pasta completa para o diretório de skills documentado pelo harness.
4. Antes de sobrescrever ou atualizar uma skill de mesmo nome, compare as versões e preserve personalizações. Instale somente as skills solicitadas; não acrescente outra configuração global sem autorização.
5. Confirme a instalação com a lista de skills do cliente. Se o harness carregar skills apenas ao iniciar uma sessão, informe se é preciso abrir uma nova sessão ou recarregar a lista.

Uma pasta Agent Skills não garante compatibilidade funcional: ferramentas, permissões e políticas mencionadas no conteúdo também precisam existir no harness de destino. Informe qualquer dependência ausente. Não contorne avisos de segurança do instalador sem autorização explícita.
