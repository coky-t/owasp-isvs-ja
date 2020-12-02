# V2: ユーザー空間アプリケーション要件

## 管理目標

## セキュリティ検証要件

### 同一性証明および認証

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **2.1.1** | IoT エコシステム内のすべての形式のユーザーを一意に識別できることを検証します。 | ✓ | ✓ | ✓ |
| **2.1.2** | クラウド、ハブ、およびその他のデバイス (センサー) を含め、IoT エコシステム内で接続されているすべてのデバイスを一意に識別できることを検証します。 | ✓ | ✓ | ✓ |
| **2.1.3** | 強力なユーザー認証とデバイス認証が IoT エコシステム全体に適用されていることを検証します。 | ✓ | ✓ | ✓ |
| **2.1.4** | ユーザー、サービス、およびデバイス認証スキームが IoT エコシステムで一元管理されている共通のフレームワークを共有していることを検証します。 | ✓ | ✓ | ✓ |
| **2.1.5** | IoT エコシステム内ではパスワードベースの認証よりも証明書ベースの認証が優先されることを検証します。 | ✓ | ✓ | ✓ |
| **2.1.6** | ハードコードされたパスワードや複数のデバイス間で重複した ID やパスワードをプロビジョニングすることを禁止することにより、IoT エコシステム全体に適切なパスワードポリシーが適用されていることを検証します。 | ✓ | ✓ | ✓ |


### 認可

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **2.2.1** | データ漏洩から保護するための暗号化と、不正な改変から保護するための完全性チェックを使用して、個人識別情報 (PII) や API キーなどの機密情報が安全に保存されていることを検証します。 | ✓ | ✓ | ✓ |
| **2.2.2** | ユーザー、サービス、デバイス全体の IoT システムアカウントが共通の認可フレームワークを共有していることを検証します。 | ✓ | ✓ | ✓ |
| **2.2.3** | ルートまたは管理者として実行されるアプリケーションとサービスを制限することにより、デバイスが最小権限の概念を実施していることを検証します。 | ✓ | ✓ | ✓ |
| **2.2.4** | 登録時、およびデバイスがアカウント間を移動する際 (デバイスの再販、リース、レンタルなど) の廃止措置の一環として、所有権が正しく妥当性確認されていることを検証します。 | ✓ | ✓ | ✓ |
| **2.2.5** | デバイスのデバッグ機能にアクセスできるのは許可されたスタッフ (サポートチームやエンジニアリングチームなど) のみであることを検証し、アクセスが監視/記録されていることを検証します。 | | ✓ | ✓ |


### データ保護

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **2.3.1** | デバイスで使用される個人識別情報 (PII) などの機密情報が安全に保存されていることを検証します。保護にはデータ漏洩に対する暗号化、および不正な改変に対するハッシュ化や完全性チェックが含まれます。 | ✓ | ✓ | ✓ |
| **2.3.2** | デバイスが廃棄される場合、または所有者が変更される場合に、PII データや資格情報などのすべての機密情報をデバイスから削除できることを検証します。 | ✓ | ✓ | ✓ |
| **2.3.3** | デバイスが廃棄される場合、または所有者が変更される場合に、エコシステムの一元管理されているデータベースで監査可能な目的でそのようにマークされることを検証します。 | ✓ | ✓ | ✓ |
| **2.3.4** | メモリに保持されている機密情報が不要になり次第すぐにゼロで上書きされていることを検証します。 | | ✓ | ✓ |


### 暗号化

| # | 説明 | L1 | L2 | L3 |
| --  | ---------------------- | - | - | - |
| **2.4.1** | 暗号化シークレットがデバイスごとに一意であることを検証します。 | ✓ | ✓ | ✓ |
| **2.4.2** | 暗号化の適切な使用を検証します。十分な鍵サイズと安全な実装を備えた、標準的で強力なアルゴリズムのみを使用する必要があります。 | ✓ | ✓ | ✓ |
| **2.4.3** | ンダム性の安全なソースがすべてのセキュリティニーズに対してオペレーティングシステムやハードウェアにより提供されていることを検証します。 | | ✓ | ✓ |
| **2.4.4** | 専用のセキュリティチップが提供する機能を利用して、デバイスで使用される暗号化シークレットが安全に保存されていることを検証します。 | | ✓ | ✓ |
| **2.4.5** | 使用されている暗号化ライブラリが FIPS 140-2 認定または同程度のものであることを検証します。 | | ✓ | ✓ |

## 参考情報