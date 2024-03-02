# Infrastructure as Code (Terraform / AWS) 実践管理記録

2024年度後半の主要テーマ。LinuCで取得したOSレイヤの設計思想をクラウド基盤へ拡張し、AWSリソースの完全コード化（IaC）を完遂した記録。

## 1. プロジェクト構成と設計思想
- **Directory Structure**: 環境（Dev/Stg/Prod）ごとのディレクトリ分離ではなく、`Terraform Cloud` の Workspace を活用したブランチ戦略ベースの環境分離。
- **Version Constraint**: プロバイダーおよびTerraform本体の厳密なバージョンロック（`required_version`, `required_providers`）による、実行環境間の差異の排除。

## 2. ネットワーク・セキュリティ基盤 (VPC/Networking)
526件の検証実績に基づき、ベストプラクティスに準拠した多層防御構成を構築。
- **Subnet Design**: Public/Private/Database の3レイヤー分離。NAT Gatewayの冗長化による単一障害点の排除。
- **Security Group Strategy**: リソース間の疎通を最小権限（Least Privilege）で制御。Ingress/Egressともに CIDR ではなく Security Group ID による参照を徹底。

## 3. 冗長化コンピュート基盤 (EC2/Auto Scaling)
- **Auto Scaling Group (ASG)**: 
  - `Launch Templates` によるOS起動設定の共通化。
  - Cloud-Init（User Data）を用いた、起動時のパッケージ一括更新およびミドルウェア（Nginx等）の自動セットアップ。
- **Application Load Balancer (ALB)**: パスベースルーティングおよび SSL/TLS証明書（ACM）の統合管理。

## 4. データベースとステート管理
- **Amazon RDS**: Multi-AZ構成による可用性確保。Terraformによる `Snapshot` からの復元手順のコード化。
- **Backend Management**: S3バケットでの `tfstate` 保存と、DynamoDBによる `State Locking` の実装。誤削除防止のためのバケットバージョニング有効化。

## 5. 品質・ガバナンスの自動化
- **Static Analysis**: 
  - `tfsec`: セキュリティの脆弱性（暗号化の有無、不要なポート開放等）を自動検知。
  - `tflint`: 命名規則や非推奨の構文を CI/CD パイプライン内でチェック。
- **Refactoring**: `import` ブロック（Terraform 1.5+）を活用した、既存手動リソースのコード管理下へのスムーズな移行プロセス。

## 6. 総括
2024年を通じて、OS管理（LinuC）からクラウド管理（Terraform）へのスキルスタックの統合を完了。
本記録は、GitHub上の526件の活動ログと密接に連動しており、インフラエンジニアとしての実務遂行能力を証明するものである。
