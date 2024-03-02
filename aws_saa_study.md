# AWS Certified Solutions Architect – Associate (SAA-C03) 実践研究

2025年度の活動の核。単なる機能理解ではなく、641件の検証ログに裏打ちされた「高可用性・低コスト・高セキュア」なアーキテクチャ設計の記録。

## 1. デザインパターンの実践検証
- **高可用性設計**: Multi-AZ配備のRDS/Aurora、およびALB+ASGによる自己修復機能を備えたスケーラブルな基盤構築。
- **データ移行とストレージ**: S3のストレージクラス（Intelligent-Tiering等）の最適化、およびEFSを用いた共有ファイルシステムの性能検証。
- **サーバーレス**: Lambda, API Gateway, DynamoDBを組み合わせた、スロットリングと再試行制御を含むイベント駆動型設計。

## 2. セキュリティとガバナンス
- **IAM**: 職務分掌に基づくIAM Roleの最小権限設定と、外部IDを用いた信頼関係の構築。
- **Network Security**: VPC Endpoint（Interface/Gateway）を活用した、パブリックインターネットを経由しないセキュアな通信経路の確立。
