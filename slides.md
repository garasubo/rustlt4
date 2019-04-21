# Rustで始める低レイヤープログラミング
@garasubo

---

## 自己紹介
Twitter: https://twitter.com/garasubo

Github: https://github.com/garasubo

Medium: https://medium.com/@garasubo
---

## 低レイヤープログラミング
OSなしでのプログラミング
- OSそのもの
- ブートローダー
- 組込みシステム

C言語（or C++）とアセンブラで書くのが定番

---
## Rustでも低レイヤープログラミング
- ガベージコレクションがなく高速
- モダンな各種言語の機能
- アセンブラ・C言語との連携も可能

---
## 最近の動向
活発に低レイヤー向けのサポートが追加されている
- Embedded Devices ワーキンググループの発足
    - ドキュメント・ライブラリが充実しつつある
    - @japaric氏が中心
- コンパイラターゲットの追加
    - Arm、RISC-V、UEFIアプリケーションなど
    - stableでもコンパイル可能
- cargoのサポート
    - xargoはメンテナンスモードに

---
## Rust低レイヤープログラミング入門
- [The Embedded Rust Book](https://rust-embedded.github.io/book/)
    - Arm Cortex-M系がメインの組込みシステム
    - [日本語版](https://tomoyuki-nakabayashi.github.io/book/)もあるよ
- [Writing an OS in Rust](https://os.phil-opp.com/)
    - BIOSで起動するOSを書く
- [uefi-rs](https://github.com/rust-osdev/uefi-rs)
    - UEFIアプリケーションを書くためのライブラリ
- [rust-raspi3-OS-tutorials](https://github.com/rust-embedded/rust-raspi3-OS-tutorials)
    - Raspberry Pi 3で動くOSを書く

---
## 実際のプロダクト
- [Tock](https://www.tockos.org/)
    - Cortex-M向けの組込みOS
    - nightlyでビルドできる
- [Redox](https://gitlab.redox-os.org/redox-os/redox)
    - デスクトップOS
    - Rustコンパイラそのものに手を加えている
- [Firecracker](https://firecracker-microvm.github.io/)
    - Amazon製のVMM


---
## 注意点
- 基本的にstdライブラリは使えない
    - BoxとかArcが使えない！
    - Cellなどcoreライブラリは使える
    - 所有権の管理を考えた設計が必要
- 生のポインタの参照外し、グローバル変数の変更はunsafe    
    - 多用するとRustで書く意義が薄れる
    - 抽象化を適切にしてunsafeの範囲を限定したい

---
## 触ってみての感想
- Rustで低レイヤープログラミングは良さそう
- 設計は工夫しないと厳しい気持ちになる
- 更新が早いので最新情報は常にチェックしたい
