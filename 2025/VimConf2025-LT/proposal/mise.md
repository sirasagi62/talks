- Title: Why Don't You Use mise for Managing Your Neovim?
- Status: Not Accepted
- Slide Language: English
- Speech Language: English


## Abstract
LSP server, linter, そしてneovim本体。neovimには管理しなければ依存関係が山ほどあります。miseを使えば、導入もアップデートも1つのファイルで完結できるんです！PCを変えてもコマンド1つで環境を再現できます。あなたもmise使いませんか？

## Pitch
YouCompleteMeの頃からvim/neovimを使い続けて、最も頭を悩ませていたのが依存する外部コマンドの管理です(YCMのときはclangdを使うためだけに別でビルドして入れていました)。最近はLSPとlinterが色々な言語で出てきていて依存関係はますます増えています。そもそもneovim自体、コンパイル済みバイナリを入れようとするとOS標準のパッケージマネージャだと古いし、appimageだとアップデートが面倒で大変です。

miseはこの問題を全部解決できます。aqua/npm/go/cargo...あらゆるパッケージマネージャのフロントエンドとなり、シングルバイナリなら大体なんでも導入できます。nvimだって、stable版なら一発で入ります。

導入したいtomlに入れたいパッケージを書き連ねてコマンドを叩くだけでどのパッケージのどのバージョンを入れたかを管理できるので、新しいPCに引っ越したりサブ機と開発環境を共有するのも簡単です。

Nixと比較すると、細かい管理ができない代わりに、tomlで管理できるのと導入に管理者権限を要しないという点で簡単に使えます。Nixとも違うmiseの素晴らしさ、伝えさせてください。

