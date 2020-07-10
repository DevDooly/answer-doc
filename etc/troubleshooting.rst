.. meta::
    :keywords: TROUBLESHOOTING

.. _doc-etc-troubleshooting:

문제 해결
=========

문제 해결 가이드를 제공합니다.

Docker 실행시 libnvidia-tls.so 라이브러리를 찾을 수 없습니다
------------------------------------------------------------

Docker 실행시 다음과 같은 에러 메시지가 출력될 수 있습니다.

.. error::
    docker: Error response from daemon: OCI runtime create failed: container_linux.go:349: starting container process caused "process_linux.go:449: conatiner init caused \"process_linux.go:432: running prestart hook 0 caused \\\"error running hook: exit status 1, stdout: , stderr: nvidia-container-cli: detection error: open failed: /usr/lib/x86_64-linux-gnu/libnvidia-tls.so.450.36.06: no such file or directory

``libnvidia-tls.so`` 라이브러리를 찾을 수 없는 경우 발생됩니다.
:ref:`nvidia-docker <doc-start-install>` 를 다시 설치해야 합니다.

