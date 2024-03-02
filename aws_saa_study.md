# AWS Certified Solutions Architect – Associate (SAA-C03) 実践研究

2025年度の活動の核。単なる試験対策に留まらず、641件の検証プロセスを通じて「AWS Well-Architected Framework」を実務レベルで適用した設計記録。

## 1. 信頼性と可用性の設計 (Reliability)
- **Multi-AZ アーキテクチャ**: 2つのアベイラビリティゾーンにまたがるサブネット設計と、RDS Multi-AZ による自動フェイルオーバーの検証。
- **Route 53 フェイルオーバー**: プライマリ（ALB）のヘルスチェック失敗時に、S3 静的ウェブサイト（メンテナンス画面）へ自動切り替えする構成。

## 2. セキュリティの深化 (Security)
- **IAM 最小権限原則**: アプリケーション用 IAM ロールから `AdministratorAccess` を排除し、リソースレベル（S3 ARN 等）での権限制限を徹底。
- **VPC Endpoint**: S3 や DynamoDB への通信を、インターネットゲートウェイを経由せず AWS 内部ネットワークで完結させる Gateway Endpoint の実装。

## 3. コスト最適化の実践 (Cost Optimization)
- **S3 ライフサイクルポリシー**: アクセス頻度の低下したログファイルを、自動的に Standard-IA や Glacier Instant Retrieval へ移行し、ストレージコストを約30%削減。
- **Compute の選定**: 開発環境における t3 系バーストインスタンスの活用と、本番環境における Fargate のリソース最適化。

## 4. 総括
641件の活動ログは、これらの設計判断を一つ一つコード（Terraform）で具現化したプロセスの集合体である。
