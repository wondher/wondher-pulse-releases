# Wondher Pulse — instaladores

O Wondher Pulse é um app desktop da Wondher Digital para capturar demandas, cronometrar sessões de trabalho e acompanhar a própria carga, com Copilot (traga a sua chave) e tarefas do Bitrix24. Tudo fica no seu computador (veja a [política de privacidade](PRIVACY.md)).

Este repositório guarda **só os instaladores e as atualizações**. O código é privado.

## Baixar

Os pacotes estão na [última release](https://github.com/wondher/wondher-pulse-releases/releases/latest):

| Sistema | Arquivo |
|---|---|
| macOS com Apple Silicon (M1 em diante) | `WondherPulse-osx-arm64-Setup.pkg` |
| macOS com Intel | `WondherPulse-osx-x64-Setup.pkg` |
| Windows 10 e 11 (64 bits) | `WondherPulse-win-Setup.exe` |
| Linux (x64) | o arquivo `.AppImage` |

Os arquivos `-Portable.zip`, `.nupkg` e `releases.*.json` servem às atualizações automáticas; não precisa baixá-los.

## Primeira abertura

No alfa os instaladores não são assinados, então o sistema avisa uma vez:

- **macOS:**
  - Se o `.pkg` não abrir com dois cliques, clique nele com o botão direito › Abrir › Abrir.
  - Se o app instalado for bloqueado, vá em Ajustes do Sistema › Privacidade e Segurança › "Abrir Mesmo Assim".
- **Windows:** o SmartScreen mostra "O Windows protegeu o computador". Clique em Mais informações › Executar assim mesmo. O Pulse se instala só para o seu usuário, sem pedir administrador.
- **Linux:**
  - Torne o AppImage executável e abra:
    ```bash
    chmod +x WondherPulse*.AppImage
    ./WondherPulse*.AppImage
    ```
  - Se o sistema pedir FUSE (Ubuntu 24.04):
    ```bash
    sudo apt install libfuse2t64
    ```

## Atalho global no Ubuntu (Wayland)

O Wayland não deixa um app registrar atalhos globais. Crie o atalho pelo sistema em Configurações › Teclado › Atalhos de teclado › Atalhos personalizados, com o comando:

```bash
/caminho/para/o-arquivo.AppImage --capture
```

Com o Pulse aberto, o atalho abre a captura flutuante. Do mesmo jeito, `--copilot` abre o Pulse com o Copilot. Numa sessão X11, os atalhos do próprio Pulse (Ctrl+Shift+Space e Ctrl+Shift+J) funcionam direto.

## Atualizações

O Pulse instalado procura uma versão nova 30 segundos depois de abrir e a cada 6 horas. Ela é baixada em segundo plano e instalada quando você sai do Pulse; o timer em andamento é pausado antes. Em Settings › Data › Version dá para ver a versão e usar "Restart to update".

## Onde ficam os dados

O banco, as configurações e o diagnóstico (`pulse.log`) ficam no seu computador:

| Sistema | Pasta |
|---|---|
| macOS | `~/Library/Application Support/Wondher Pulse` |
| Windows | `%LOCALAPPDATA%\Wondher Pulse` |
| Linux | `~/.local/share/Wondher Pulse` |

Chaves e senhas (IA e webhook do Bitrix24) ficam no cofre do sistema: Keychain, Credential Manager ou Secret Service. Elas nunca vão para o banco nem para o log.
