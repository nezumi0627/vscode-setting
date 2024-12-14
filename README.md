<div align="center">
  <h1>🐍 VSCode Python Development Template</h1>
  <p>
    <img src="https://img.shields.io/badge/Python-3.10-blue.svg" alt="Python 3.10">
    <img src="https://img.shields.io/badge/Ruff-latest-orange.svg" alt="Ruff">
    <img src="https://img.shields.io/badge/mypy-latest-green.svg" alt="mypy">
  </p>
</div>

<div align="left">

このテンプレートは、VSCodeでのPython開発用設定ファイルです。
Codeの保存時にRuffを使用した高速な
リンティング、フォーマット、mypyによる厳格な型チェックを行えます。

<details>
<summary><h2>📋 主な機能</h2></summary>

- **⚡ 高速な静的解析とフォーマット**
  - Ruffによる高速なリンティングとフォーマット
  - 保存時の自動フォーマット適用
  - インポートの自動整理

- **🔍 厳格な型チェック**
  - mypyによる静的型チェック
  - 型ヒントの表示
  - 暗黙的な型を許可しない設定

- **✨ コード品質管理**
  - PEP 8準拠のコードスタイル
  - Googleスタイルのドキュメント規約
  - 最大行長79文字の強制
  - 複雑度チェック（最大値: 10）
</details>

<details>
<summary><h2>🚀 セットアップ手順</h2></summary>

1. **VSCode拡張機能のインストール**:
   - [Ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff)
     - リンティングとフォーマット用
   - [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
     - Python言語サポート全般

2. **依存パッケージのインストール**:
   ```bash
   pip install ruff mypy
   ```

3. **設定ファイルのコピー**:
   以下のファイルをプロジェクトのルートディレクトリにコピー:
   - `.vscode/settings.json` - VSCodeのワークスペース設定
   - `pyproject.toml` - Python開発ツールの設定
</details>

<details>
<summary><h2>⚙️ 詳細設定</h2></summary>

### 🛠 Ruffの設定 (pyproject.toml)

#### 基本設定
- Python 3.10をターゲット
- 行長制限: 79文字
- ダブルクォートを使用
- LF改行
- スペースによるインデント

#### リンティングルール
1. **コードスタイル**
   - `E`, `W`: PEP 8準拠のエラーと警告
   - `COM`: コンマの配置
   - `UP`: 最新のPython文法推奨

2. **コード品質**
   - `F`: PyFlakesによる基本的なエラーチェック
   - `B`: バグの可能性がある実装の検出
   - `S`: セキュリティの問題
   - `C`: 循環的複雑度（上限: 10）

3. **型チェック**
   - `ANN`: 型アノテーションの強制
   - `FBT`: ブール値の型チェック

4. **ドキュメント**
   - `D`: Googleスタイルのdocstring規約
   - docstringスタイルの競合を解消（D203, D213を無視）

5. **命名規則**
   - `N`: PEP 8命名規則
   - `A`: 変数名の規則

6. **その他**
   - `I`: インポート整理
   - `BLE`: 例外処理のベストプラクティス
   - `T20`: print文の使用制限
   - `RUF`: Ruff固有の追加ルール

### 🎨 VSCode設定 (settings.json)

#### エディタ設定
- 保存時の自動フォーマット有効化
- Ruffをデフォルトフォーマッタとして使用
- 79文字のルーラー表示
- 末尾の空白文字を自動削除
- ファイル末尾の改行を自動管理

#### Python固有の設定
- 厳格な型チェックモード
- 自動インポート補完
- 関数の戻り値型のヒント表示
- 変数の型ヒント表示
</details>

<details>
<summary><h2>💻 開発ワークフロー</h2></summary>

1. **コーディング**
   - VSCodeで通常通りコードを記述
   - リアルタイムで型ヒントと問題の表示

2. **自動チェック（保存時）**
   - コードフォーマットの適用
   - インポートの整理
   - 基本的な問題の自動修正

3. **問題の確認と修正**
   - エディタ上で警告やエラーを確認
   - 型チェックの結果を確認
   - 提案される修正を適用
</details>

<details>
<summary><h2>🔧 カスタマイズ</h2></summary>

### 設定の調整
- `pyproject.toml`でRuffのルールを調整可能
  ```toml
  [tool.ruff.lint]
  ignore = ["ルールコード"]  # 特定のルールを無視
  ```

- `.vscode/settings.json`でエディタの動作を調整可能
  ```json
  {
    "python.analysis.typeCheckingMode": "basic",  # 型チェックの厳格さを調整
  }
  ```
</details>

<details>
<summary><h2>❓ トラブルシューティング</h2></summary>

- **フォーマットが適用されない場合**
  - Ruff拡張機能が正しくインストールされているか確認
  - ワークスペース設定が正しく読み込まれているか確認

- **型チェックが動作しない場合**
  - mypyが正しくインストールされているか確認
  - `pyproject.toml`の型チェック設定を確認
</details>

<details>
<summary><h2>⚠️ 注意事項</h2></summary>

- プロジェクトの要件に応じて`pyproject.toml`の設定を調整してください
- 特定のルールを無視する必要がある場合は、`ruff.lint.ignore`に追加してください
- 大規模なプロジェクトでは、必要に応じてルールを緩和することを検討してください
</details>

</div>
