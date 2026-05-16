# Backend Engineer (Go) — net/http-first, raw SQL, build-time architecture enforcement

Web バックエンドを中心に開発しています。Go は業務で2年、個人開発を含めて約3年です。少人数でも継続開発できる状態を、属人的なレビューではなく仕組みとして整えることに関心があります。素の `net/http` を基本に、`database/sql` で生 SQL を書き、層の依存方向はビルド時に強制し、将来の担当者が背景を推測せずに保守できる状態を重視します。

## Tech

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Google Cloud](https://img.shields.io/badge/Google%20Cloud-4285F4?style=flat-square&logo=googlecloud&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

- **Languages**: Go (main), TypeScript
- **Backend**: net/http, OpenAPI 駆動 (huma), database/sql（生 SQL・ORM 不使用）
- **DB**: PostgreSQL, MySQL, BigQuery
- **Cloud**: GCP (Cloud Run, Cloud SQL, Cloud Build, Cloud Tasks, Vertex AI)
- **Quality**: depguard, forbidigo, golangci-lint, lefthook, golden test, testcontainers-go
- **Certification**: Google Cloud 認定 6種

## Selected Work

- **[clean-arch-todo-boundary](https://github.com/aranunara/clean-arch-todo-boundary)** — Clean Architecture の層境界を、依存方向の strict allow-list でビルド時に強制した最小サンプル。判断基準は `ARCHITECTURE.md` に言語化。保存先は in-memory ↔ PostgreSQL で差し替え可能。Go / net/http / depguard。
- **[deplicate-image-checker](https://github.com/aranunara/deplicate-image-checker)** — 画像の重複を Embedding ベクトル類似度で検出する Slack Bot。Go（net/http・フレームワーク不使用）/ Vertex AI Embedding / Firestore / Cloud Run / Terraform。
- **[go-coding-kit](https://github.com/aranunara/go-coding-kit)** — Go のデータ構造・アルゴリズムのユーティリティ集（標準ライブラリのみで動作）。

## Focus

- 品質を属人的なレビューではなく仕組みで担保する（依存方向のビルド時強制、commit 前の自動ゲート）
- 素の net/http で境界を保ち、フレームワークは文脈に応じて選定する
- 長期保守 — 将来の担当者が背景を推測しなくて済む状態を残す
