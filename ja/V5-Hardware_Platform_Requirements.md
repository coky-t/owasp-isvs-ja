# V5: ハードウェアプラットフォーム要件

## 管理目標

## セキュリティ検証要件

### 設計

| # | 説明 | L1 | L2 | L3 |
| -- | ---------------------- | - | - | - |
| **5.1.1** | プラットフォームがデバッグインタフェース (JTAG, SWD など) へのアクセスの無効化または保護をサポートしていることを検証します。 | | ✓ | ✓ |
| **5.1.2** | プラットフォームがファーストステージブートローダーの真正性の妥当性確認をサポートしていることを検証します。 | | ✓ | ✓ |
| **5.1.3** | メインチップや外部セキュリティチップにより提供される専用機能を活用することなどにより、プラットフォームが暗号化機能を提供していることを検証します。 | | ✓ | ✓ |
| **5.1.4** | 専用のハードウェアセキュリティ機能を利用して、秘密鍵や証明書などの機密データを安全に保存できることを検証します。 | | ✓ | ✓ |
| **5.1.5** | プラットフォームがメモリおよび I/O 保護機能を提供し、特権プロセスのみが特定のリソースにアクセスできることを検証します。 | | ✓ | ✓ |
| **5.1.6** | OTP フューズを燃やすなどにより、プラットフォームのプラットフォームセキュリティ構成をロックできることを検証します。 | | ✓ | ✓ |
| **5.1.7** | デバッグヘッダが PCB から削除されていることを検証します。 | | ✓  | ✓ |
| **5.1.8** | 選択したハードウェアに、特定の機能を有効または無効にできる特別なピン構成など、非公式に文書化されたデバッグ機能がないことを検証します。 | | ✓ | ✓ |
| **5.1.9** | プラットフォームが物理的なディーキャプサレイション、サイドチャネル、グリッチ攻撃に対する保護を提供していることを検証します。 | | | ✓ |
| **5.1.10** | 説明的なシルクスクリーンが PCB から除去されていることを検証します。 | | | ✓ |

## 参考情報
詳細については、以下も参照してください。
- Common Weakness Enumeration (CWE) Hardware Design: <https://cwe.mitre.org/data/definitions/1194.html>
- IoT Security - Physical and Hardware Security: <https://www.embedded.com/iot-security-physical-and-hardware-security/>
- IETF RFC 8576 - IoT Security: State of the Art and Challenges (5.10 Reverse Engineering Considerations): <https://tools.ietf.org/html/rfc8576>
- ENISA - Baseline Security Recommendations for IoT: <https://www.enisa.europa.eu/publications/baseline-security-recommendations-for-iot/at_download/fullReport>
- GSMA - IoT Security Guidelines for Endpoint Systems <https://www.gsma.com/iot/wp-content/uploads/2017/10/CLP.13-v2.0.pdf>
- NSA Hardware and Firmware Security Guidance: <https://github.com/nsacyber/Hardware-and-Firmware-Security-Guidance>
