Forked from [developit/preact-todomvc](https://github.com/developit/preact-todomvc)

## WebBundle

依存コンテンツを1つにまとめて配信する方法

署名を行いコンテンツの物理的なURLと論理的なURLを差し替えて表示できるようにするSigned HTTP Exchangesは単一のResponseに対する署名だが、WebBundleと合わせることで依存コンテンツ全てに対して有効にできる

Signed HTTP Exchanges（SXG） + WebBundle = WebPackaging

## WebPackaging

メリット

1. 任意のサーバーなどから、AMPのようにCacheから取得しながら任意のURLを表示できる
2. SXGにより内容が保証され、WebBundleによって配布が容易なミラーリングやスナップショットが可能になる
3. 依存関係を一度で取得できるため、JSをbundleすることなく、ES Modulesで記述したりできるようになるかも...？

## サンプルの使用方法

1. `go/bundle`をインストール

```command
go get -u github.com/WICG/webpackage/go/bundle/cmd/...
```

2. wbnファイルを生成

```command
yarn
yarn build
yarn bundle
```

3. chrome://flags/#web-bundlesを開く

> バージョン80以上のChromeかChrome Canaryを使用

4. Web Bundles flagを有効化

5. todomvc.wbnをChromeにドラッグアンドドロップ
