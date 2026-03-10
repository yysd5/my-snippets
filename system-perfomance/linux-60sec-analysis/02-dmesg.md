---
Title: 02-dmesg
Description: |
  OOM(メモリ不足)エラーなどのカーネルエラーの確認。

  `dmesg`はカーネルのリングバッファメッセージを表示するコマンド。
  カーネルやドライバに関する問題のトラブルシューティングに役立つ。

  - **-T**: タイムスタンプを人間が読みやすい形式で表示する。
  - **| tail**: 出力の末尾部分（デフォルトは10行）のみを表示する。これにより、最新のメッセージを素早く確認できる。

  **出力例:**
  ```
  [Wed Oct 29 16:01:35 2025] usb 1-1: New USB device found, idVendor=8087, idProduct=0029, bcdDevice= 0.00
  [Wed Oct 29 16:01:35 2025] usb 1-1: New USB device strings: Mfr=0, Product=0, SerialNumber=0
  [Wed Oct 29 16:01:35 2025] audit: type=1400 audit(1730265695.384:2): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/lxc-start" pid=289 comm="apparmor_parser"
  [Wed Oct 29 16:01:35 2025] audit: type=1400 audit(1730265695.384:3): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/lxc-start//lxc-instance" pid=289 comm="apparmor_parser"
  [Wed Oct 29 16:01:35 2025] audit: type=1400 audit(1730265695.384:4): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/lxc-start//lxc-instance//cgns" pid=289 comm="apparmor_parser"
  [Wed Oct 29 16:01:35 2025] audit: type=1400 audit(1730265695.384:5): apparmor="STATUS" operation="profile_load" profile="unconfined" name="/usr/bin/lxc-start//lxc-instance//pivot" pid=289 comm="apparmor_parser"
  [Wed Oct 29 16:01:35 2025] Out of memory: Killed process 12345 (example) total-vm:123456kB, anon-rss:12345kB, file-rss:0kB, shmem-rss:0kB
  ```

  **結果の見方:**

  出力の中に`Out of memory`や`OOM killer`といった文字列があれば、メモリ不足が原因でプロセスが強制終了されたことを示す。その他、ハードウェアのエラー(`error`など)やドライバの問題に関するメッセージが出力されることもある。
Tags:
  - linux
  - performance
  - kernel
  - error
---

```bash
dmesg -T | tail
```
