# V4: 通信要件

## 管理目標

デバイスはネットワーク通信を使用してエコシステム内でデータを交換し、コマンドを受信します。さまざまな関係者が通信の内容を信頼できるように、関係者を保護し、関係者の真正性、悪意のある変更に対する完全性、情報漏洩に対する機密性を確保する必要があります。実際には、これは最新の通信プロトコルを展開し、暗号化を含むそれらのセキュリティ機能を構成することを意味します。セキュアな TLS, Bluetooth, および Wi-Fi に関する業界ガイドラインは頻繁に変更されるため、通信セキュリティが常に効果的であることを確保するために、構成を定期的にレビューする必要があります。

- 送信されるデータの機密性に関係なく、常に TLS または同等の強力な暗号化と認証を使用します。
- その他のセキュリティプラクティスにはピンニングと相互認証を備える証明書ベースの認証が含まれます。
- 最新の構成を使用して、通信に使用されるアルゴリズムと暗号の優先順序を有効にして設定します。
- 非推奨または既知のセキュアではないアルゴリズムと暗号を無効にします。
- 有線および無線通信プロトコルで利用可能な最も強力なセキュリティ設定を使用します。

## セキュリティ検証要件

### 一般

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **4.1.1** | IoT エコシステムの他のコンポーネント (センサー、ゲートウェイ、サポートクラウドなど) との通信が、データの機密性と完全性が保証され、通信プロトコルにリプレイ攻撃に対する保護が組み込まれている安全なチャネルを介して行われることを検証します。 | ✓ | ✓ | ✓ |
| **4.1.2** | TLS を使用する場合は、FIPS 準拠の暗号スイート (または同等のもの) のみを使用するように構成されていることを検証します。 | ✓ | ✓ | ✓ |
| **4.1.3** | TLS を使用する場合は、デバイスが X.509 証明書を暗号学的に検証することを検証します。 | ✓ | ✓ | ✓ |
| **4.1.4** | 可用性が重要なアプリケーションについて、妨害からの保護または検出が提供されていることを検証します。 | | ✓ | ✓ |
| **4.1.6** | デバイスの TLS 実装が独自の証明書ストアを使用し、エンドポイントの証明書または公開鍵にピン留めし、信頼できる CA により署名されている場合でも異なる証明書または鍵を持つエンドポイントへの接続を許可しないことを検証します。 | | ✓ | ✓ |
| **4.1.7** | チップ間通信が暗号化されていることを検証します。 (メインボードからドーターボードへの通信など) | | | ✓ |

### マシン間

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **4.2.1** | 暗号化されていない通信が機密性の低いデータと命令に限定されていることを検証します。 | ✓ | ✓ | ✓ |
| **4.2.2** | MQTT ブローカーが認可された IoT デバイスのみにメッセージトピックのサブスクライブおよびパブリッシュを許可していることを検証します。 | ✓ | ✓ | ✓ |
| **4.2.3** | MQTT トランザクションを認証するために、証明書がネイティブのユーザー名とパスワードよりも優先されることを検証します。 | ✓ | ✓ | ✓ |

### Bluetooth

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **4.3.1** | 必要な場合を除いて Bluetooth デバイスでペアリングと検出がブロックされていることを検証します。 | ✓ | ✓ | ✓ |
| **4.3.2** | PIN または PassKey コードが簡単に推測できないことを検証します。 (たとえば 0000 や 1234 を使用してはいけません) | ✓ | ✓ | ✓ |
| **4.3.3** | シンプルモードの認証を用いる古いバージョンの Bluetooth を使用しているデバイスでは、ペアリングに PIN が必要であることを検証します。 | ✓ | ✓ | ✓ |
| **4.3.4** | 最新バージョンの Bluetooth の場合、"Just Works" を除くすべてのバージョンで Secure Simple Pairing (SSP) 認証に少なくとも 6 桁が必要であることを検証します。 | ✓ | ✓ | ✓ |
| **4.3.5** | 暗号化鍵がデバイスがサポートする最大サイズであり、このサイズが Bluetooth 接続を介して送信される情報を適切に保護するのに十分であるを検証します。 | ✓ | ✓ | ✓ |
| **4.3.6** | 利用可能な最も安全な Bluetooth ペアリング手法が使用されていることを検証します。通信デバイスの機能に応じて Out Of Band (OOB), Numeric Comparison, Passkey Entry ペアリング手法が使用されていることを検証します。 | ✓ | ✓ | ✓ |
| **4.3.7** | デバイスでサポートされている最強の Bluetooth セキュリティモードとレベルが使用されていることを検証します。たとえば、Bluetooth 4.1 デバイスの場合、セキュリティモード 4、レベル 4 を使用して、認証されたペアリングと暗号化を提供する必要があります。 | ✓ | ✓ | ✓ |

### Wi-Fi

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **4.4.1** | デバイス機能の一部として必要な場合を除き、Wi-Fi 接続が無効であることを検証します。ネットワーク接続を必要としないデバイスや、Ethernet など他のタイプのネットワーク接続をサポートするデバイスでは、Wi-Fi インタフェースを無効にする必要があります。 | ✓ | ✓ | ✓ |
| **4.4.2** | Wi-Fi 通信を保護するために WPA2 以降が使用されていることを検証します。 | ✓ | ✓ | ✓ |
| **4.4.3** | WPA が使用されている場合は、AES 暗号化 (CCMP モード) で使用されていることを検証します。 | ✓ | ✓ | ✓ |
| **4.4.4** | Wi-Fi Protected Setup (WPS) がデバイス間の Wi-Fi 接続を確立するために使用されていないことを検証します。 | ✓ | ✓ | ✓ |


## 参考情報
詳細については、以下も参照してください。

- OWASP Transport Layer Protection Cheat Sheet: <https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Protection_Cheat_Sheet.html>
- NIST SP800-52r2 - Guidelines for the Selection, Configuration, and Use of TLS Implementations: <https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-52r2.pdf>
- IETF RFC 7525 - Recommendations for Secure Use of TLS and DTLS: <https://tools.ietf.org/html/rfc7525>
- NIST SP800-121r2 - Guide to Bluetooth Security: <https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-121r2.pdf>
- NIST SP800-97 - Establishing Wireless Robust Security Networks: <https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-97.pdf>
