# Política de privacidade do Wondher Pulse

*Versão 0.4.0 · 4 de novembro de 2026*

O Wondher Pulse é feito pela **Wondher Digital LTDA**. Contato: `brianmendes@wondher.io`.

## Tudo fica no seu computador

O Pulse não tem servidor nem conta. O que você registra fica só no banco local do Pulse, no seu computador:
- as demandas, com descrição, e as sessões de tempo;
- as quick notes e os textos de checklist;
- o histórico, o registro de remoções e as configurações.

Desde a versão 0.2.4, o Pulse guarda também uma cópia do banco por dia, dos últimos 7 dias, na pasta "Wondher Pulse Backups", ao lado da pasta de dados. Essas cópias também ficam só no seu computador.

**Notas de voz** (no macOS): o microfone só grava quando você clica no botão de voz, e para no Stop ou no Cancel. O áudio vira texto neste computador, pelo Whisper, e é apagado em seguida. O áudio nunca é guardado nem enviado. Fica só o texto, na descrição ou na quick note, e ele segue as mesmas regras do que você digita. O modelo do Whisper fica na pasta "Wondher Pulse Models", ao lado da pasta de dados.

Chaves e senhas ficam no cofre do sistema (Keychain, Credential Manager ou Secret Service), nunca no banco nem no log:
- a chave de IA;
- o webhook do Bitrix24.

Até a versão 0.1.x havia uma função de equipe que enviava alguns campos para a nuvem. Ela foi retirada na 0.2.0: a atualização apaga do computador o que era só da equipe e a sessão antiga do cofre do sistema.

## O que sai do computador, e só se você ligar

- **Bitrix24:** o Pulse fala direto com o portal Bitrix24 da sua empresa, com o webhook que você mesmo cria. Lê as tarefas do filtro que você escolher, com a descrição delas, e registra nelas o tempo e o status, com o comentário que você escrever ao pausar, trocar de demanda ou concluir. Ao criar uma tarefa a partir de uma demanda local, envia o título, o prazo, a prioridade e a descrição; desde a versão 0.3.0, no portal da Maxipas, uma demanda de Suporte, Desenvolvimento ou Infraestrutura vai para o fluxo da TI correspondente, no formato do modelo dele. "Delete in Bitrix24" exclui no portal só uma tarefa que o próprio Pulse criou, e só depois da sua confirmação. Quick notes e checklists nunca vão para o Bitrix24.
- **Copilot:** usa o provedor de IA que você escolher, com a sua própria chave. Desde a versão 0.2.6, o Copilot lê tudo o que importa sobre as suas demandas, para julgar melhor o que priorizar: títulos, status, prazos, tempo, tipo, origem, descrições, checklists e as quick notes mais recentes. Para onde isso vai depende do provedor, e Settings › Copilot mostra isso para o que estiver escolhido:
  - **Local** (Ollama, ou um endpoint neste computador): nada sai do seu computador.
  - **Nuvem** (Anthropic, OpenAI, Google, ou um endpoint em outra máquina): cada pergunta e cada sugestão de passos envia esses dados ao provedor. A captura envia a linha que você digita; o "Draft with AI", quando você clica nele, envia também a descrição que estiver na captura. Quanto tempo o provedor guarda e como usa os dados segue os termos dele: Anthropic (https://www.anthropic.com/legal/privacy), OpenAI (https://openai.com/policies/privacy-policy/) e Google (https://ai.google.dev/gemini-api/terms).
  - **Desligado**, ou sem chave (as respostas vêm das regras do próprio Pulse): nada vai para uma IA.
- **Modelo de voz:** quando você clica em Download (Settings › Copilot › Voice notes), o Pulse baixa o modelo do Whisper do Hugging Face (`huggingface.co/ggerganov/whisper.cpp`) e confere o arquivo pelo hash. O download não envia dado seu além do que qualquer download envia, como o endereço IP. A transcrição em si nunca sai do computador.
- **Atualizações:** o Pulse instalado consulta o repositório público de versões do Pulse no GitHub (`wondher/wondher-pulse-releases`) para saber se há uma versão nova. A consulta não envia dado seu além do que qualquer download envia, como o endereço IP.

## Seus dados são seus

- Apagar a pasta de dados do Pulse e a pasta de cópias apaga tudo do computador. A pasta de modelos guarda só o modelo de voz, que também pode ser removido em Settings:
  - macOS: `~/Library/Application Support/Wondher Pulse`, `~/Library/Application Support/Wondher Pulse Backups` e `~/Library/Application Support/Wondher Pulse Models`;
  - Windows: `%LOCALAPPDATA%\Wondher Pulse`, `%LOCALAPPDATA%\Wondher Pulse Backups` e `%LOCALAPPDATA%\Wondher Pulse Models`;
  - Linux: `~/.local/share/Wondher Pulse`, `~/.local/share/Wondher Pulse Backups` e `~/.local/share/Wondher Pulse Models`.
- Desconectar o Bitrix24 ou desligar o Copilot em Settings interrompe o envio na hora.

---

Este texto descreve como o alfa funciona. Não é parecer jurídico e será revisado antes de uma versão pública.
