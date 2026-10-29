# Política de privacidade do Wondher Pulse

*Versão 0.2.5 · 29 de outubro de 2026*

O Wondher Pulse é feito pela **Wondher Digital LTDA**. Contato: `brianmendes@wondher.io`.

## Tudo fica no seu computador

O Pulse não tem servidor nem conta. O que você registra fica só no banco local do Pulse, no seu computador:
- as demandas e as sessões de tempo;
- as notas e os textos de checklist;
- o histórico, o registro de remoções e as configurações.

Desde a versão 0.2.4, o Pulse guarda também uma cópia do banco por dia, dos últimos 7 dias, na pasta "Wondher Pulse Backups", ao lado da pasta de dados. Essas cópias também ficam só no seu computador.

Chaves e senhas ficam no cofre do sistema (Keychain, Credential Manager ou Secret Service), nunca no banco nem no log:
- a chave de IA;
- o webhook do Bitrix24.

Até a versão 0.1.x havia uma função de equipe que enviava alguns campos para a nuvem. Ela foi retirada na 0.2.0: a atualização apaga do computador o que era só da equipe e a sessão antiga do cofre do sistema.

## O que sai do computador, e só se você ligar

- **Bitrix24:** o Pulse fala direto com o portal Bitrix24 da sua empresa, com o webhook que você mesmo cria. Lê as tarefas do filtro que você escolher e registra nelas o tempo e o status.
- **Copilot:** usa o provedor de IA que você escolher (Anthropic, OpenAI, Google, Ollama ou outro compatível), com a sua própria chave. O Pulse envia a esse provedor títulos, status, prazos e tempo das suas demandas. Nunca envia notas. O tratamento desses dados segue os termos do provedor que você escolheu.
- **Atualizações:** o Pulse instalado consulta o repositório público de versões do Pulse no GitHub (`wondher/wondher-pulse-releases`) para saber se há uma versão nova. A consulta não envia dado seu além do que qualquer download envia, como o endereço IP.

## Seus dados são seus

- Apagar a pasta de dados do Pulse e a pasta de cópias apaga tudo do computador:
  - macOS: `~/Library/Application Support/Wondher Pulse` e `~/Library/Application Support/Wondher Pulse Backups`;
  - Windows: `%LOCALAPPDATA%\Wondher Pulse` e `%LOCALAPPDATA%\Wondher Pulse Backups`;
  - Linux: `~/.local/share/Wondher Pulse` e `~/.local/share/Wondher Pulse Backups`.
- Desconectar o Bitrix24 ou desligar o Copilot em Settings interrompe o envio na hora.

---

Este texto descreve como o alfa funciona. Não é parecer jurídico e será revisado antes de uma versão pública.
