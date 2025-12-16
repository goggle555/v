<div align="center" style="display:grid;place-items:center;">
<p>
    <a href="https://vlang.io/" target="_blank"><img width="80" src="https://raw.githubusercontent.com/vlang/v-logo/master/dist/v-logo.svg?sanitize=true" alt="V logo"></a>
</p>
<h1>V プログラミング言語</h1>

[vlang.io](https://vlang.io)
| [ドキュメント](https://github.com/vlang/v/blob/master/doc/docs.md)
| [変更履歴](https://github.com/vlang/v/blob/master/CHANGELOG.md)
| [速度](https://fast.vlang.io/)
| [コントリビュート & コンパイラ設計](https://github.com/vlang/v/blob/master/CONTRIBUTING.md)

</div>
<div align="center" style="display:grid;place-items:center;">
<!--
[![Build Status][WorkflowBadge]][WorkflowUrl]
-->

[![Sponsor][SponsorBadge]][SponsorUrl]
[![Patreon][PatreonBadge]][PatreonUrl]
[![Discord][DiscordBadge]][DiscordUrl]
[![X][XBadge]][XUrl]
[![Modules][ModulesBadge]][ModulesUrl]

</div>

## V の主な特徴

- シンプルさ: 週末で習得できる言語
- 高速なコンパイル: Clangバックエンドで約110k行/秒、
  ネイティブおよびtccバックエンドで約500k行/秒 *(Intel i5-7500, SSD, 最適化なし)*
  ([デモ動画](https://www.youtube.com/watch?v=pvP6wmcl_Sc))
- 開発のしやすさ: V は1秒以内に自身をコンパイル可能
- パフォーマンス: C と同等の速度（V のメインバックエンドは人間が読める C コードを生成）
- 安全性: null なし、グローバル変数なし、未定義動作なし（開発中）、デフォルトでイミュータブル
- C から V への変換（[DOOM 変換デモ動画](https://www.youtube.com/watch?v=6oXrz3oRoEg)）
- ホットコードリロード
- [柔軟なメモリ管理](https://vlang.io/#memory)。デフォルトで GC、`v -gc none` で手動管理、
  `v -prealloc` でアリーナアロケーション、`v -autofree` で自動解放
  （[autofree デモ動画](https://www.youtube.com/watch?v=gmB8ea8uLsM)）
- [クロスプラットフォーム UI ライブラリ](https://github.com/vlang/ui)
- 組み込みグラフィックスライブラリ
- 簡単なクロスコンパイル
- REPL
- [組み込み ORM](https://github.com/vlang/v/blob/master/doc/docs.md#orm)
- [組み込み Web フレームワーク](https://github.com/vlang/v/blob/master/vlib/veb/README.md)
- C および JavaScript バックエンド
- 低レベルソフトウェアの記述に最適（[Vinix OS](https://github.com/vlang/vinix)）

## 安定性、今後の変更、1.0 後のフリーズについて

開発初期段階にあるものの、V 言語は比較的安定しており、頻繁に変更されることはありません。
ただし、1.0 までには変更があります。
構文の変更のほとんどは vfmt によって自動的に処理されます。

V のコア API（主に `os` モジュール）も V 1.0 で安定化されるまで、軽微な変更があります。
もちろん、1.0 以降も API は拡張されますが、既存のコードを壊すことはありません。

1.0 リリース後、V は「機能フリーズ」モードに入ります。つまり、言語に破壊的変更はなく、
バグ修正とパフォーマンス改善のみが行われます。Go と同様です。

V 2.0 はあるのでしょうか？1.0 から10年以内にはなく、おそらく永遠にないでしょう。

まとめると、他の多くの言語とは異なり、V は新機能の追加や既存機能の変更で常に変化し続けることはありません。
常に小さくシンプルな言語であり続け、現在の姿と非常に似た状態を維持します。

## ソースから V をインストール

--> **_（これが推奨される方法です）_**

### Linux、macOS、Windows、\*BSD、Solaris、WSL など

通常、すでに機能する `git` インストール環境がある場合、V のインストールは非常に簡単です。

注意: Windows では、CMD で `make` の代わりに `make.bat` を実行するか、PowerShell で `./make.bat` を実行してください。
注意: Ubuntu/Debian では、最初に `sudo apt install git build-essential make` を実行する必要があるかもしれません。

開始するには、ターミナル/シェルで以下を実行してください：
```bash
git clone --depth=1 https://github.com/vlang/v
cd v
make
```

これで完了で、V の実行ファイルは `[V リポジトリへのパス]/v` にあるはずです。
`[V リポジトリへのパス]` はどこでも構いません。

（上記の注意にあるように、Windows では `make` の代わりに `make.bat` を使用してください。）

次に `./v run examples/hello_world.v`（cmd シェルでは `v run examples/hello_world.v`）を実行してみてください。

- *問題がありますか？上記の注意事項と
  [インストールに関する問題](https://github.com/vlang/v/discussions/categories/installation-issues)
  へのリンクを参照してください。*

注意: V は常に更新されています。V を最新バージョンに更新するには、次を実行するだけです：

```bash
v up
```

> [!NOTE]
> 問題が発生した場合、または V がすぐにインストールまたは動作しない
> 異なるオペレーティングシステムや Linux ディストリビューションを使用している場合は、
> [インストールに関する問題](https://github.com/vlang/v/discussions/categories/installation-issues)
> を参照して、お使いの OS と問題を検索してください。
>
> 問題が見つからない場合は、お使いの OS に関する既存のディスカッションがあれば追加するか、
> まだメインのディスカッションがない場合は新しいものを作成してください。

### Void Linux

```bash
# xbps-install -Su base-devel
# xbps-install libatomic-devel
$ git clone --depth=1 https://github.com/vlang/v
$ cd v
$ make
```

### Docker

```bash
git clone --depth=1 https://github.com/vlang/v
cd v
docker build -t vlang .
docker run --rm -it vlang:latest
```

### Docker with Alpine/musl

```bash
git clone --depth=1 https://github.com/vlang/v
cd v
docker build -t vlang_alpine - < Dockerfile.alpine
alias with_alpine='docker run -u 1000:1000 --rm -it -v .:/src -w /src vlang_alpine:latest'
```

依存関係なしで、別の Linux ディストリビューションを実行しているサーバーにコピーできる
*静的*実行ファイルのコンパイル：
```bash
with_alpine v -skip-unused -prod -cc gcc -cflags -static -compress examples/http_server.v
with_alpine v -skip-unused -prod -cc gcc -cflags -static -compress -gc none examples/hello_world.v
ls -la examples/http_server examples/hello_world
file   examples/http_server examples/hello_world
examples/http_server: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, no section header
examples/hello_world: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, no section header
```

次のような出力が表示されるはずです：
```
-rwxr-xr-x 1 root root  16612 May 27 17:07 examples/hello_world
-rwxr-xr-x 1 root root 335308 May 27 17:07 examples/http_server
```

### FreeBSD

FreeBSD では、V は `boehm-gc-threaded` パッケージが事前にインストールされている必要があります。
インストール後、Linux/macOS と同じスクリプトを使用できます：

```bash
pkg install boehm-gc-threaded
git clone --depth=1 https://github.com/vlang/v
cd v
make
```

### OpenBSD

OpenBSD（リリース 7.8）では、V は `boehm-gc` と `openssl-3.5` パッケージが事前にインストールされている必要があります。
インストール後、GNU `make`（`gmake` パッケージでインストール）を使用して V をビルドします。

```bash
pkg_add boehm-gc openssl%3.5 gmake
git clone --depth=1 https://github.com/vlang/v
cd v
gmake
```

### Termux/Android

Termux では、V はいくつかのパッケージが事前にインストールされている必要があります -
動作する C コンパイラ、および `libexecinfo`、`libgc`、`libgc-static`。
インストール後、Linux/macOS と同じスクリプトを使用できます：

```bash
pkg install clang libexecinfo libgc libgc-static make git
pkg update
git clone --depth=1 https://github.com/vlang/v
cd v
make
./v symlink
```
注意: Termux では `sudo ./v symlink` は*不要*です（sudo はデフォルトでインストールされていません）。

### C コンパイラ

[Tiny C Compiler (tcc)](https://repo.or.cz/w/tinycc.git) は、システムに互換性のあるバージョンが
ある場合、`make` によって自動的にダウンロードされ、V の `thirdparty` ディレクトリにインストールされます。

このコンパイラは非常に高速ですが、ほとんど最適化を行いません。開発ビルドに最適です。

本番ビルド（V の `-prod` オプションを使用）には、clang、gcc、または
Microsoft Visual C++ の使用が推奨されます。開発を行っている場合は、
おそらくすでにこれらのいずれかがインストールされているでしょう。

そうでない場合は、以下の手順に従ってください：

- [Linux と macOS での C コンパイラのインストール](https://github.com/vlang/v/wiki/Installing-a-C-compiler-on-Linux-and-macOS)

- [Windows での C コンパイラのインストール](https://github.com/vlang/v/wiki/Installing-a-C-compiler-on-Windows)

### シンボリックリンク

> [!NOTE]
> V を PATH に追加することを*強く推奨*します。これにより、
> V 実行ファイルへのフルパスを毎回入力する手間が省けます。
> V は `v symlink` コマンドを提供しており、より簡単にこれを行えます。

Unix システムでは、実行ファイルへの `/usr/local/bin/v` シンボリックリンクを作成します。
これを行うには、次を実行します：

```bash
sudo ./v symlink
```

Windows では、管理者権限で新しいシェルを起動します。例えば、
<kbd>Windows キー</kbd>を押してから `cmd.exe` と入力し、メニューエントリを右クリックして
「管理者として実行」を選択します。新しい管理者シェルで、V をコンパイルしたパスに cd し、
次を入力します：

```bat
v symlink
```

（PowerShell では `.\v symlink`）

これにより、V が PATH に追加され、どこからでも使用できるようになります。
新しい PATH 変数を取得できるように、シェル/エディタを再起動してください。

> [!NOTE]
> `v symlink` を複数回実行する必要はありません - `v up`、再起動などの後も
> v は引き続き使用できます。V リポジトリフォルダを別の場所に移動する場合にのみ、
> 再度実行する必要があります。

## エディタ/IDE プラグイン

- [Atom](https://github.com/vlang/awesome-v#atom)
- [Emacs](https://github.com/vlang/awesome-v#emacs)
- [JetBrains](https://plugins.jetbrains.com/plugin/20287-vlang/docs/syntax-highlighting.html)
- [Sublime Text 3](https://github.com/vlang/awesome-v#sublime-text-3)
- [Vim](https://github.com/vlang/awesome-v#vim)
- [VS Code](https://marketplace.visualstudio.com/items?itemName=VOSCA.vscode-v-analyzer)
- [zed](https://github.com/lv37/zed-v)


エディタに V プログラミング言語の IDE 機能を追加するには、
[v-analyzer](https://github.com/vlang/v-analyzer) をチェックしてください。
言語サーバー機能を提供します。

## テストとサンプルの実行

V が自身をコンパイルできることを確認してください：

```bash
$ v self
$ v
V 0.3.x
終了するには Ctrl-C または `exit` を使用

>>> println('hello world')
hello world
>>>
```

```bash
cd examples
v hello_world.v && ./hello_world    # または単に
v run hello_world.v                 # これはプログラムをビルドしてすぐに実行します

v run word_counter/word_counter.v word_counter/cinderella.txt
v run news_fetcher.v
v run tetris/tetris.v
```


<img src='https://raw.githubusercontent.com/vlang/v/master/examples/tetris/screenshot.png' width=300 alt='テトリスのスクリーンショット'>

## Sokol と GG GUI アプリ/ゲーム：

テトリスや 2048（または `sokol` や `gg` グラフィックスモジュールを使用するその他のもの）を
ビルドするには、システム用の追加開発ライブラリをインストールする必要があります。

| システム             | インストール方法                                                                                    |
|---------------------|---------------------------------------------------------------------------------------------------|
| Debian/Ubuntu 系    | `sudo apt install libxi-dev libxcursor-dev libgl-dev libxrandr-dev libasound2-dev` を実行         |
| Fedora/RH/CentOS    | `sudo dnf install libXi-devel libXcursor-devel libX11-devel libXrandr-devel libglvnd-devel` を実行 |
|                     |                                                                                                   |
| NixOS               | `xorg.libX11.dev xorg.libXcursor.dev xorg.libXi.dev xorg.libXrandr.dev libGL.dev` を               |
|                     | `environment.systemPackages` に追加                                                               |

## V net.http、net.websocket、`v install`

net.http モジュール、net.websocket モジュール、および `v install` コマンドはすべて SSL を使用する場合があります。
V には mbedtls のバージョンが付属しており、すべてのシステムで動作するはずです。
代わりに OpenSSL を使用する必要がある場合は、システムにインストールされていることを確認してから、
コンパイル時に `-d use_openssl` スイッチを使用してください。

注意: Mbed-TLS は小さく、Windows でもインストールが簡単です（V に付属しています）。
ただし、HTTPS/SSL サーバーへの多くの http リクエストを行うプログラムを作成する場合、
ほとんどの場合、OpenSSL がインストールされているシステムで `-d use_openssl` を指定して
コンパイルするのが*最善*です（以下を参照）。Mbed-TLS は遅く、特に複数のホストへの
並列 http リクエスト（Web スクレイパー、REST API クライアント、RSS リーダーなど）を
行う場合に問題が発生する可能性があります。
Windows では、このようなプログラムは WSL2 で実行する方が良いでしょう。

非 Windows システムに OpenSSL をインストールするには：

| システム             | インストールコマンド                  |
|---------------------|-------------------------------------|
| macOS               | `brew install openssl`              |
| Debian/Ubuntu 系    | `sudo apt install libssl-dev`       |
| Arch/Manjaro        | openssl はデフォルトでインストール済み |
| Fedora/CentOS/RH    | `sudo dnf install openssl-devel`    |

Windows では、OpenSSL を正しく動作させるのは単純に困難です。
[こちら](https://tecadmin.net/install-openssl-on-windows/)の手順が役立つかもしれません（または役立たないかもしれません）。

## V sync

V の `sync` モジュールとチャンネル実装は libatomic を使用します。
おそらくシステムにすでにインストールされていますが、インストールされていない場合は、
次の手順でインストールできます：

| システム             | インストールコマンド                   |
|---------------------|--------------------------------------|
| macOS               | すでにインストール済み                  |
| Debian/Ubuntu 系    | `sudo apt install libatomic1`        |
| Fedora/CentOS/RH    | `sudo dnf install libatomic-static`  |

## V UI

<a href="https://github.com/vlang/ui">
<img src='https://raw.githubusercontent.com/vlang/ui/master/examples/screenshot.png' width=712 alt='V UI サンプルのスクリーンショット'>
</a>

https://github.com/vlang/ui

<!---
## JavaScript バックエンド

[examples/js_hello_world.v](examples/js_hello_world.v):

```v
fn main() {
	for i in 0 .. 3 {
		println('Hello from V.js')
	}
}
```

```bash
v -o hi.js examples/js_hello_world.v && node hi.js
Hello from V.js
Hello from V.js
Hello from V.js
```
-->

## Android グラフィカルアプリ

V の `vab` ツールを使用すると、Android 向けの V UI とグラフィカルアプリのビルドが
以下のように簡単になります：

```
./vab /path/to/v/examples/2048
```

[https://github.com/vlang/vab](https://github.com/vlang/vab).
<img src="https://user-images.githubusercontent.com/768942/107622846-c13f3900-6c58-11eb-8a66-55db12979b73.png" alt="vab サンプルのスクリーンショット">

## Web アプリケーションの開発

[シンプルな Web ブログの構築](https://github.com/vlang/v/blob/master/tutorials/building_a_simple_web_blog_with_veb/README.md)
チュートリアルと、GitHub/GitLab の軽量で高速な代替である Gitly をチェックしてください：

https://github.com/vlang/gitly

<img src="https://user-images.githubusercontent.com/687996/85933714-b195fe80-b8da-11ea-9ddd-09cadc2103e4.png" alt="gitly のスクリーンショット">

## Vinix、V で書かれた OS/カーネル

V はドライバやカーネルなどの低レベルソフトウェアを書くのに最適です。
Vinix は bash、GCC、V、nano を実行できる OS/カーネルです。

https://github.com/vlang/vinix

<img src="https://github.com/vlang/vinix/blob/main/screenshot0.png?raw=true" alt="vinix スクリーンショット 1">
<img src="https://github.com/vlang/vinix/blob/main/screenshot1.png?raw=true" alt="vinix スクリーンショット 2">

## 謝辞

### TCC

V は [TCC - Tiny C Compiler](https://bellard.org/tcc/) の元の作業について
Fabrice Bellard 氏に感謝します。
TCC の Web サイトは古いことに注意してください。現在の TCC リポジトリは
[こちら](https://repo.or.cz/w/tinycc.git)にあります。
V は [https://github.com/vlang/tccbin/](https://github.com/vlang/tccbin/) にある
事前ビルドされた TCC バイナリを使用しています。

### PVS-Studio

[PVS-Studio](https://pvs-studio.com/pvs-studio/?utm_source=website&utm_medium=github&utm_campaign=open_source) - C、C++、C#、Java コード用の静的アナライザー。

## トラブルシューティング

[Wiki ページ](https://github.com/vlang/v/wiki)の
[トラブルシューティング](https://github.com/vlang/v/wiki/Troubleshooting)
セクションを参照してください。

[WorkflowBadge]: https://github.com/vlang/v/workflows/CI/badge.svg
[DiscordBadge]: https://img.shields.io/discord/592103645835821068?label=Discord&logo=discord&logoColor=white
[PatreonBadge]: https://img.shields.io/endpoint.svg?url=https%3A%2F%2Fshieldsio-patreon.vercel.app%2Fapi%3Fusername%3Dvlang%26type%3Dpatrons&style=flat
[SponsorBadge]: https://img.shields.io/github/sponsors/medvednikov?style=flat&logo=github&logoColor=white
[XBadge]: https://img.shields.io/badge/follow-%40v__language-1DA1F2?logo=x&style=flat&logoColor=white
[ModulesBadge]: https://img.shields.io/badge/modules-reference-027d9c?logo=v&logoColor=white&logoWidth=10

[WorkflowUrl]: https://github.com/vlang/v/commits/master
[DiscordUrl]: https://discord.gg/vlang
[PatreonUrl]: https://patreon.com/vlang
[SponsorUrl]: https://github.com/sponsors/medvednikov
[XUrl]: https://x.com/v_language
[ModulesUrl]: https://modules.vlang.io

