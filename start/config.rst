.. meta::
    :keywords: CONFIG

.. _doc-start-config:

설정방법
========

이 페이지는 "엔서" 사용자 환경 설정 방법을 정리한 곳입니다.

answer-cli.config example
-------------------------

``$HOME/.answer/answer-cli.config`` 위치에 다음 내용을 저장하면 됩니다.

- ANSWER_DB_PORT=5432
- ANSWER_DB_USER=bogo
- ANSWER_DB_PASSWORD=6090
- ANSWER_S3_PORT=9000
- ANSWER_S3_ID=minio
- ANSWER_S3_PW=minio123
- ANSWER_CORE_NODE=default
- ANSWER_CORE_BIND=0.0.0.0
- ANSWER_CORE_PORT=20002
- ANSWER_CORE_VERBOSE=0
- ANSWER_CORE_SYNC=0
- ANSWER_API_PORT=20001
- ANSWER_API_DB_URL=localhost
- ANSWER_API_S3_URL=localhost
- ANSWER_API_CORE_URL=localhost
- ANSWER_WEB_HOST=0.0.0.0
- ANSWER_WEB_PORT=20000
- ENABLE_GPU=1
- GPUS=all
- ENABLE_HOST_NETWORK=1
- DOCKER_LOGS_TAIL_NUMBER=10

default.json example
--------------------

``$HOME/.answer/core.storage/node/default.json`` 위치에 다음 내용을 저장하면 됩니다.

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

