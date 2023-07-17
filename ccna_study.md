# CCNA (Cisco Certified Network Associate) 学習ログ

2023年3月から6月にかけて習得したネットワーク技術の詳細。
理論学習に加え、Packet Tracerによる大規模トポロジの構築を継続的に実施。

---

## 🛠 重点習得トピック & 検証ログ

### 1. L2 Switching & Loop Avoidance
- **STP/RSTP**:
  - ルートブリッジ選出プロセスの検証。`priority` 値の調整による最適ルートの固定化。
  - PortFast, BPDU Guard の設定によるエッジポートのセキュリティと収束高速化。
- **VLAN/Trunking**:
  - VTPによる管理効率化と、DTPの無効化（`switchport nonegotiate`）によるセキュリティ向上。
  - Native VLAN不一致時の挙動確認。

### 2. IP Routing & Infrastructure
- **OSPFv2 (Deep Dive)**:
  - Neighbor/Adjacency確立のトラブルシューティング（Hello/Dead Timer, Area ID, Subnetの一致確認）。
  - Wildcard Maskを用いた詳細なネットワーク広告。
  - パッシブインターフェースの設定による不要なLSA配布の抑制。
- **FHRP (HSRP)**:
  - `preempt` 設定によるアクティブルータ切り戻し動作の確認。
  - IP SLAを用いたトラッキングによる上位回線障害時の自動切り替え。

### 3. Network Security & IP Services
- **ACL (Access Control List)**:
  - 名前付き拡張ACLを用いた、特定のポート（HTTP/SSH等）のみを許可するステートフルに近い制御。
- **NAT/PAT**:
  - `ip nat inside source list` を用いた多対一変換のデバッグ（`show ip nat translations`）。

---

## 📈 学習の推移
- **2023.03 - 04**: OSI参照モデルの徹底理解とL2基礎。
- **2023.05**: ルーティングプロトコルの詳細検証。複雑なトポロジでの疎通確認。
- **2023.06**: セキュリティ、自動化、管理サービスの総仕上げと模擬試験の反復。

**Final Assessment:** Passed CCNA (2023.07)
