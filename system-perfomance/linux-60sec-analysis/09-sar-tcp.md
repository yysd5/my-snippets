---
Title: 08-sar-tcp
Description: |
  TCP統計。接続のスピード、再送の確認。

  `sar -n TCP,ETCP`コマンドは、TCPおよび拡張TCPのネットワーク統計情報を表示する。
   TCP通信の健全性やパフォーマンスに関する詳細な洞察を得るのに役立つ。

  - **-n TCP,ETCP**: TCPおよび拡張TCPの統計情報を表示する。
  - **1**: 1秒間隔で情報を更新する。

  **出力例:**
  ```
  Linux 5.15.0-105-generic (hostname) 2025年10月29日 _x86_64_ (4 CPU)

  16時00分01秒 active/s passive/s iseg/s oseg/s
  16時00分02秒 0.00 0.00 12.00 10.00
  ...

  16時00分01秒 atmptf/s estres/s retrans/s isegerr/s odisc/s
  16時00分02秒 0.00 0.00 0.00 0.00 0.00
  ...
  ```

  **結果の見方:**

  - **active/s**: 毎秒アクティブに確立されたTCP接続の数。
  - **passive/s**: 毎秒パッシブに確立されたTCP接続の数。
  - **iseg/s**: 毎秒受信されたセグメントの総数。
  - **oseg/s**: 毎秒送信されたセグメントの総数。
  - **retrans/s**: 毎秒再送信されたセグメントの総数。この値が高い場合、ネットワークの問題や輻輳を示唆する。
  - **isegerr/s**: 毎秒エラーを伴って受信されたセグメントの総数。ネットワークの品質問題を示唆する。

  `retrans/s`や`isegerr/s`が高い場合、ネットワークの再送やエラーが多く発生しており、通信品質に問題がある可能性がある。
Tags:
  - linux
  - performance
  - network
  - tcp
---

```bash
sar -n TCP,ETCP 1
```
