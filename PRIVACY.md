# Política de privacidade do Wondher Pulse

*Versão alfa · 22 de outubro de 2026*

O Wondher Pulse é feito pela **Wondher Digital LTDA**, que é a controladora dos dados tratados na nuvem da equipe, nos termos da LGPD (Lei 13.709/2018). Contato: `brianmendes@wondher.io`.

## O que fica só no seu computador

Tudo o que você registra fica no banco local do Pulse, no seu computador:
- as demandas e as sessões de tempo;
- as notas e os textos de checklist;
- o histórico e as configurações.

Sem equipe, nada disso sai daí.

Chaves e senhas ficam no cofre do sistema (Keychain, Credential Manager ou Secret Service), nunca no banco nem no log:
- a chave de IA;
- o webhook do Bitrix24;
- a sessão da equipe.

## O que vai para a nuvem, se você entrar numa equipe

A equipe usa o Supabase, num projeto na região de São Paulo (`sa-east-1`). Só vão para lá:

- **Seu perfil:** nome, cargo (se você preencher) e o número do seu usuário no Bitrix24, se você conectar o Bitrix24. O gestor entra com e-mail e código; o membro entra com nome e código de convite, sem e-mail.
- **As demandas compartilhadas,** que são as tarefas do Bitrix24, as tarefas que o gestor atribuiu e as demandas locais que você deixar como compartilhadas. De cada uma vão:
  - título, status, prioridade, tipo e prazo;
  - tempo registrado;
  - a **contagem** de passos do checklist (feitos e total);
  - o vínculo com o Bitrix24.
- **Sua presença:** se há um timer rodando e em qual demanda (para uma demanda privada, só que há um timer, sem dizer qual), o tempo de hoje e da semana e quantas demandas privadas você tem, só o número.
- **As tarefas atribuídas:** título, prioridade, tipo, prazo e o vínculo com o Bitrix24 do que o gestor atribui ou realoca.
- **O registro de remoções:** quando alguém apaga de vez uma demanda arquivada, ficam quem fez, quando, o título (vazio se a demanda era privada) e os totais de tempo.

**Nunca vão para a nuvem:**
- notas;
- textos de checklist;
- demandas privadas;
- conversas com o Copilot.

## O que o gestor vê

O gestor da sua equipe vê só os dados compartilhados acima, e a carga é calculada a partir deles. Os membros não veem os dados uns dos outros. Quando você sai da equipe ("Leave team"), o gestor deixa de ver os seus dados, e as suas demandas continuam no seu computador.

## Bitrix24 e IA

- **Bitrix24:** o Pulse fala direto com o portal Bitrix24 da sua empresa, com o webhook que você mesmo cria. Lê as suas tarefas e registra tempo e status nelas.
- **Copilot:** usa o provedor de IA que você escolher (Anthropic, OpenAI, Google, Ollama ou outro compatível), com a sua própria chave. O Pulse envia a esse provedor títulos, status, prazos e tempo das suas demandas, e, para o gestor, os dados compartilhados da equipe. Nunca envia notas. O tratamento desses dados segue os termos do provedor que você escolheu.

## Atualizações

O Pulse instalado consulta este repositório público no GitHub para saber se há uma versão nova. A consulta não envia dado seu além do que qualquer download envia, como o endereço IP.

## Seus direitos

Você pode pedir acesso, correção ou exclusão dos seus dados da nuvem da equipe pelo contato acima.

Os dados locais são seus:
- apagar a pasta de dados do Pulse apaga tudo do computador;
- sair da equipe interrompe o envio.

---

Este texto descreve como o alfa funciona. Não é parecer jurídico e será revisado antes de uma versão pública.
