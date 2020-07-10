.. meta::
    :keywords: CONFIG

.. _doc-start-config:

설정방법
========

이 페이지는 "엔서" 사용자 환경 설정 방법을 정리한 곳입니다.

CORE
----




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

