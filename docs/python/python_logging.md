---
title: logging
parent: Python
layout: default
nav_enabled: true
nav_order: 4
---

# logging

[logging](https://docs.python.org/ja/3/library/logging.html)はアプリケーションやライブラリのための柔軟なエラーログ記録 (logging) システムを実装するためのモジュール

---

## モジュールの読み込み

```
import logging
```

## ログレベル

| level      | description            |
| ---------- | ---------------------- |
| `CRITICAL` | 致命的なエラー         |
| `ERROR`    | エラー発生             |
| `WARNING`  | 想定外だが処理継続可能 |
| `INFO`     | 通常の動作記録         |
| `DEBUG`    | デバッグ情報           |
| `NOTSET`   | レベル未設定           |

---

## Handler

| handler                                     | description                  |
| ------------------------------------------- | ---------------------------- |
| `logging.Handler`                           | 全Handlerの基底クラス        |
| `logging.StreamHandler`                     | 標準出力・標準エラー出力     |
| `logging.FileHandler`                       | ファイル出力                 |
| `logging.NullHandler`                       | ログ破棄                     |
| `logging.handlers.BaseRotatingHandler`      | ローテーション系の基底クラス |
| `logging.handlers.RotatingFileHandler`      | サイズベースのローテーション |
| `logging.handlers.TimedRotatingFileHandler` | 時間ベースのローテーション   |
| `logging.handlers.WatchedFileHandler`       | logrotate連携                |
| `logging.handlers.SocketHandler`            | TCP送信                      |
| `logging.handlers.DatagramHandler`          | UDP送信                      |
| `logging.handlers.SysLogHandler`            | Syslog送信                   |
| `logging.handlers.NTEventLogHandler`        | Windows Event Log            |
| `logging.handlers.SMTPHandler`              | メール送信                   |
| `logging.handlers.HTTPHandler`              | HTTP送信                     |
| `logging.handlers.MemoryHandler`            | メモリバッファ               |
| `logging.handlers.QueueHandler`             | Queueへ送信                  |
| `logging.handlers.QueueListener`            | Queue受信・処理              |
| `logging.handlers.BufferingHandler`         | バッファリング用基底クラス   |

---

## メソッド

| method                  | description                       |
| ----------------------- | --------------------------------- |
| `logging.basicConfig()` | ログの基本設定を行う              |
| `logging.getLogger()`   | Loggerオブジェクトを取得する      |
| `logger.setLevel()`     | Loggerのログレベルを設定する      |
| `logger.debug()`        | DEBUGレベルのログを出力する       |
| `logger.info()`         | INFOレベルのログを出力する        |
| `logger.warning()`      | WARNINGレベルのログを出力する     |
| `logger.error()`        | ERRORレベルのログを出力する       |
| `logger.exception()`    | 例外情報付きでERRORログを出力する |

---

## ロガーの使用例

以下のプロジェクトにおけるロガーの使用例を示す

```
project/
├── main.py
├── logging_config.py
└── app/
    ├── __init__.py
    └── service.py
```

### logging_config.py

```
import logging

def setup_logging() -> None:
    logging.basicConfig(
        level=logging.INFO,
        format=(
            "%(asctime)s "
            "%(levelname)-8s "
            "%(name)s "
            "%(message)s"
        ),
        datefmt="%Y-%m-%d %H:%M:%S",
    )
```

### service.py

```
import logging

logger = logging.getLogger(__name__)

def execute() -> None:
    logging.info("message")
```

### main.py

```
from logging_config import setup_logging

from app.service import execute

if __name__ == "__main__":
    setup_logging()
    execute()
```

---
