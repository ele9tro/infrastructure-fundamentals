# Infrastructure as Code (Terraform) 実践ログ

Terraform (HCL) を用いたAWSリソースの自動プロビジョニング and 構成管理の実装。

---

## 🛠 重点習得トピック
- **Provider & State Management**: Backend (S3/DynamoDB) を用いたStateロックとチーム開発環境の構築。
- **Modular Design**: 再利用性の高いModule構成の設計、Variables/Outputsによる環境依存値の分離。
- **Resource Orchestration**: VPC/Subnet, EC2, RDSの一括構築、および `terraform import` による既存環境のコード化。
- **CI/CD Integration**: GitHub Actionsと連携したPlan/Applyの自動化パイプラインの試作。
