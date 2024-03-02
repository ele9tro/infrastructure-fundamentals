# Advanced Infrastructure Architecture Design

インフラ構成のコード化（Terraform）を前提とした、モダンなクラウドネイティブアーキテクチャの設計記録。

## 1. CI/CD パイプラインの統合 (GitHub Actions)
2025年の主要な取り組みとして、手動による `terraform apply` を廃止し、プルリクエストベースの自動デプロイフローを確立。

### 実装されたワークフロー例
- **OIDC 連携**: AWS と GitHub Actions を `OpenID Connect` でセキュアに接続。
- **Plan Automation**: `terraform plan` の結果を PR のコメントに自動投稿。

## 2. コンテナ基盤の運用設計 (ECS on Fargate)
- **可観測性**: `awslogs` ドライバを用いた CloudWatch Logs への集約。
- **スケーリング**: CPU/メモリ使用率に基づいた Target Tracking Scaling の実装。
