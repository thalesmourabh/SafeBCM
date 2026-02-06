<p align="center">
  <img src="icon_256x256.png" width="128" alt="SafeBCM">
</p>

# SafeBCM (Ativador de Wi-Fi Broadcom)

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![macOS](https://img.shields.io/badge/macOS-Sonoma%20%7C%20Sequoia%20%7C%20Tahoe-brightgreen)](https://www.apple.com/macos/)
[![Platform](https://img.shields.io/badge/Platform-Intel%20%7C%20AMD-orange)](https://github.com/thalesmourabh/SafeBCM)

O SafeBCM é uma ferramenta **open-source** para ativar de forma segura o suporte a Wi-Fi Broadcom no macOS Tahoe (26), Sequoia (15) e Sonoma (14).

Funciona em Hackintoshes **Intel e AMD**, sem precisar de Xcode ou qualquer ferramenta de desenvolvimento instalada.

> ⚠️ **Projeto em Desenvolvimento**: Este é um projeto da comunidade. Use por sua conta e risco.

## Por que SafeBCM?

| Característica | OCLP-Mod | SafeBCM |
|----------------|----------|---------|
| API Remota | ✅ SimpleHacAPI | ❌ **100% Local** |
| Código Auditável | Parcial | ✅ **Totalmente Aberto** |
| Transparência | Limitada | ✅ **Plano antes de agir** |
| Xcode Necessário | Depende | ❌ **Não precisa** |

## Download

👉 **[Baixe a última versão aqui](https://github.com/thalesmourabh/SafeBCM/releases/latest)**

## Instalação

1. Baixe o arquivo `SafeBCM-vX.X.X-Intel-AMD.zip` da aba [Releases](https://github.com/thalesmourabh/SafeBCM/releases)
2. Extraia o `.zip`
3. Mova `SafeBCM.app` para `/Applications`
4. Na primeira vez que abrir:

**macOS Sonoma (14):**
- Botão direito no app → Abrir → Confirmar "Abrir"

**macOS Sequoia (15) / Tahoe (26):**
- Abra o Terminal e execute:
```bash
xattr -cr /Applications/SafeBCM.app
```
- Depois abra o SafeBCM normalmente

> 💡 **Alternativa para qualquer macOS:** Duplo-clique (vai bloquear) → Ajustes do Sistema → Privacidade e Segurança → "Abrir Mesmo Assim"

## Requisitos

- **macOS**: Sonoma (14), Sequoia (15), ou Tahoe (26)
- **Hardware**: Hackintosh Intel ou AMD
- **Placa WiFi**: Broadcom compatível (Fenvi T919, Dell DW1560, etc)
- **SIP**: Desabilitado (`csr-active-config=03080000`)
- **EFI**: Partição montada com OpenCore configurado

## O que o SafeBCM faz

```
┌─────────────────────────────────────────────────┐
│  1. ANÁLISE                                     │
│     - Detecta macOS e versão                    │
│     - Verifica SIP e configuração               │
│     - Localiza partição EFI                     │
│     - Identifica chipset Broadcom via PCI       │
├─────────────────────────────────────────────────┤
│  2. DIAGNÓSTICO                                 │
│     - Analisa config.plist do OpenCore          │
│     - Detecta kexts faltando ou mal configurados│
│     - Verifica boot-args necessários            │
├─────────────────────────────────────────────────┤
│  3. CORREÇÃO AUTOMÁTICA                         │
│     - Injeta kexts (AMFIPass, AirportBrcmFixup, │
│       IO80211FamilyLegacy, IOSkywalkFamily)     │
│     - Corrige config.plist automaticamente      │
├─────────────────────────────────────────────────┤
│  4. ROOT PATCHING                               │
│     - Aplica patches ModernWireless             │
│     - Restaura IO80211 e WiFiPeerToPeer         │
│     - Requer reinício após aplicar              │
└─────────────────────────────────────────────────┘
```

## Verificação de Integridade

Cada release inclui um arquivo `SHA256SUMS.txt` para verificação:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

## Segurança

- 🔒 **GPL-3.0**: Forks maliciosos são forçados a manter código aberto
- 📝 **Audit Log**: Todas as ações são registradas
- 🔄 **Recuperação**: Script automático se algo der errado
- 🚫 **Sem Telemetria**: Zero comunicação externa
- 📦 **100% Local**: Nenhuma API remota, tudo roda na sua máquina

## Licença

[GPL-3.0](LICENSE) - Código deve permanecer aberto.

---

**Feito com ❤️ para a comunidade Hackintosh brasileira**
