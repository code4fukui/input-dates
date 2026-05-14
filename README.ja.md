# input-dates

カレンダービューから単一または複数の日付を選択するための、軽量で依存関係のないWebコンポーネントです。

## デモ

[ライブデモを試す](https://code4fukui.github.io/input-dates/)

<img src="https://user-images.githubusercontent.com/1715217/122636184-cd656680-d122-11eb-8ca3-a4808ca5398a.png" width="300" alt="input-dates カレンダーコンポーネントのスクリーンショット">

## 機能

- **複数日付選択**: 複数の個別日付を選択できます。
- **単一日付モード**: 選択を単一日付に制限できます。
- **日付のハイライト**: 週末と日本の祝日を自動的にハイライトします。
- **利用可能日付の制御**: プログラムで選択可能な日付を定義できます。
- **依存関係ゼロ**: ESモジュールとして直接インポート可能なスタンドアロンなWebコンポーネントです。
- **シンプルなAPI**: 標準のプロパティとイベントを使用してコンポーネントを操作できます。

## 使い方

HTMLファイルにスクリプトタグを追加します。ビルドステップやインストールは必要ありません。

```html
<script type="module" src="https://code4fukui.github.io/input-dates/input-dates.js"></script>

<input-dates id="my-calendar"></input-dates>

<script type="module">
  const calendar = document.getElementById('my-calendar');

  // 初期選択日付を設定
  calendar.value = "2021-06-19,2021-06-18";

  // 変更を監視
  calendar.onchange = () => {
    console.log('Selected dates:', calendar.value);
  };
</script>
```

## APIリファレンス

### 属性

- `single`
  - このブール属性が存在する場合、コンポーネントは単一日付選択モードで動作します。
  - **例**: `<input-dates single></input-dates>`

### プロパティ

- `.value`
  - **型**: `String`
  - **説明**: 選択された日付のゲッター/セッターです。値は`YYYY-MM-DD`形式の日付をカンマで区切った文字列です。
  - **例**: `calendar.value = "2023-10-26,2023-10-31";`

### メソッド

- `.setAvailable(dates)`
  - **説明**: ユーザーが選択できる日付を制限します。他のすべての日付は無効になります。
  - **パラメーター**:
    - `dates`: `String` | `Array<String|Day>` - カンマ区切りの日付文字列、または日付文字列や`day-es`ライブラリの`Day`オブジェクトの配列。
  - **例**:
    ```javascript
    // カンマ区切りの文字列を使用
    calendar.setAvailable("2023-12-24,2023-12-25,2023-12-31");

    // 文字列の配列を使用
    calendar.setAvailable(["2024-01-01", "2024-01-02"]);
    ```

- `.clear()`
  - **説明**: 現在選択されているすべての日付の選択を解除します。

### イベント

- `onchange`
  - **説明**: ユーザーが選択を変更したときに発火するハンドラです。
  - **例**: `calendar.onchange = () => { /* ... */ };`

## 依存関係

- このコンポーネントは、日付計算と日本の祝日検出に[day-es](https://github.com/code4fukui/day-es/)ライブラリを使用します。動的に読み込まれるため、別途インストールする必要はありません。

## ライセンス

MIT License
