.. meta::
    :keywords: CONFIG

.. _doc-start-config:

설정방법
========

이 페이지는 "엔서" 사용자 환경 설정 방법을 정리한 곳입니다.

CORE
----

.. code-block:: javascript
    :linenos:

    {
      "logger": {
        "name": "default.logger",
        "sink": "console",
        "arguments": "stdout",
        "generator": "default_color",
        "line_feed": "auto",
        "severity": "debug",
        "auto_flush": true,
        "thread": true
      },
      "socket": {
        "recv_timeout": "4sec",
        "send_timeout": "1sec",
        "recv_number_of_messages": 16,
        "send_number_of_messages": 16,
        "recv_buffer_byte": "32m",
        "send_buffer_byte": "32m",
        "reconnect_time_min": 10,
        "reconnect_time_max": 10
      },
      "inits": [
        {
          "type": "git",
          "arguments": "https://github.com/bogonets/answer-lambda-cv2",
          "branch": "master",
          "auto_update": true,
          "destination": "${STORAGE_PYTHON}/answer-lambda-cv2"
        },
        {
          "type": "git",
          "arguments": "https://github.com/bogonets/answer-lambda-numpy",
          "branch": "master",
          "auto_update": true,
          "destination": "${STORAGE_PYTHON}/answer-lambda-numpy"
        },
        {
          "type": "git",
          "arguments": "https://github.com/bogonets/answer-lambda-preview",
          "branch": "master",
          "auto_update": true,
          "destination": "${STORAGE_PYTHON}/answer-lambda-preview"
        },
        {
          "type": "git",
          "arguments": "https://github.com/bogonets/answer-lambda-rtc",
          "branch": "master",
          "auto_update": true,
          "destination": "${STORAGE_PYTHON}/answer-lambda-rtc"
        }
      ],
      "plugin": {
        "script": "${STORAGE_PYTHON}/npp.py",
        "event_create": "on_create",
        "event_loop_begin": "on_loop_begin",
        "event_loop_end": "on_loop_end",
        "event_destroy": "on_destroy"
      },
      "immutable": true
    }





API
---

CORE_URL
CORE_PORT

DB_URL
DB_PORT

DB_USER
DB_PASSWORD

MINIO_URL
MINIO_PORT
MINIO_ACCESS_TOKEN
MINIO_SECRET_TOKEN

WEB
---

--port=NUMBER - select port to use, default: PORT env var or 8080
--host=ADDRESS - select host address to bind to, default: IP env var or 0.0.0.0 ("any address")
--no-browser - suppress automatic web browser launching
--browser=BROWSER - specify browser to use instead of system default
--quiet | -q - suppress logging
--verbose | -V - more logging (logs all requests, shows all listening IPv4 interfaces, etc.)

