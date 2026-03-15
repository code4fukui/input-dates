# input-dates タグ

日付範囲選択コンポーネントです。[サンプルアプリ](https://code4fukui.github.io/input-dates/)で確認できます。

## デモ
[サンプルアプリ](https://code4fukui.github.io/input-dates/)で日付の選択と表示ができます。

## 機能
- 複数の日付を選択可能
- 選択した日付のハイライト表示
- 土日や祝日の表示
- 特定の日付の選択を制限できる

## 使い方

HTMLに以下のコードを追加するだけで使えます。

```html
<script type="module" src="https://code4fukui.github.io/input-dates/input-dates.js"></script>
<input-dates id="inputdates"></input-dates>

<script type="module">
inputdates.value = "2021-06-19,2021-06-18";
inputdates.onchange = () => {
  console.log(inputdates.value);
};
</script>
```

## ライセンス
MIT License