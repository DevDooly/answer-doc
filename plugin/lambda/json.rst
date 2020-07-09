람다 플러그인 JSON
==================

Example
-------

.. code-block:: json
    :linenos:

    {
        "info": {
            "name": "cv2_videocapture_mp",
            "version": "1.0.0",
            "category": "cv2",
            "keywords": ["cv2"],
            "homepage": "https://answer.bogonets.com/",
            "bugs": "https://answer.bogonets.com/",
            "license": "Bogonet License",
            "author": "zer0",
            "dependencies": [
                {"type": "pip", "src": "numpy"},
                {"type": "pip", "src": "opencv-python"}
            ],
            "engines": ">=1.0.2",
            "environment": {
                "type": "pyenv",
                "name": "cv2"
            },
            "titles": {
                "en": "cv2.videocapture.mp",
                "ko": "cv2.videocapture.mp"
            },
            "descriptions": {
                "en": "Class for video capturing from video files, image sequences or cameras.",
                "ko": "비디오 파일, 이미지 시퀀스 또는 카메라에서 비디오를 캡처한다."
            },
            "documentation_mime": "text",
            "documentations": {
            },
            "meta": {}
        },
        "controls": {
            "input": [
            ],
            "output": [
                {
                    "name": "frame",
                    "mimes": ["image/jpeg", "image/png"]
                }
            ]
        },
        "props": [
            {
                "rule": "initialize_only",
                "name": "filename",
                "default_value": "",
                "type": "str",
                "required": true,
                "valid": {},
                "title": {
                    "en": "Filename",
                    "ko": "Filename"
                },
                "help": {
                    "en": "Name of file to be loaded.",
                    "ko": "읽어올 파일 이름."
                }
            },
            {
                "rule": "initialize_only",
                "name": "api_preference",
                "default_value": "default",
                "type": "str",
                "required": true,
                "valid": {
                    "list": "default;ffmpeg;images;dshow"
                },
                "title": {
                    "en": "API Preference",
                    "ko": "API Preference"
                },
                "help": {
                    "en": "Preferred Capture API backends to use.",
                    "ko": "사용할 백엔드 API."
                }
            },
            {
                "rule": "initialize_only",
                "name": "sleep",
                "default_value": 0,
                "type": "int",
                "required": true,
                "valid": {},
                "title": {
                    "en": "Sleep for the next iteration.",
                    "ko": "다음 반복을 위한 대기시간."
                },
                "help": {
                    "en": "Sleep after reading the frame. (milliseconds)",
                    "ko": "프레임을 읽은 후 잠시 대기한다. (밀리초)"
                }
            },
            {
                "rule": "initialize_only",
                "name": "reopen",
                "default_value": true,
                "type": "bool",
                "required": false,
                "valid": {},
                "title": {
                    "en": "Reopen Flag",
                    "ko": "재연결 플래그"
                },
                "help": {
                    "en": "If video frame acquisition fails, reconnect.",
                    "ko": "비디오 프레임 획득에 실패하면 재연결한다."
                }
            },
            {
                "rule": "initialize_only",
                "name": "max_queue_size",
                "default_value": 4,
                "type": "int",
                "required": true,
                "valid": {},
                "title": {
                    "en": "Max queue size",
                    "ko": "Max queue size"
                },
                "help": {
                    "en": "The upper limit on the number of items that can be queued.",
                    "ko": "대기열에 넣을 수있는 항목 수의 상한 값."
                }
            },
            {
                "rule": "initialize_only",
                "name": "exit_timeout_seconds",
                "default_value": 4.0,
                "type": "float",
                "required": true,
                "valid": {},
                "title": {
                    "en": "Exit timeout",
                    "ko": "종료 타임아웃"
                },
                "help": {
                    "en": "Maximum waiting time when destroying lambdas. (seconds)",
                    "ko": "람다 파괴시 최대 대기 시간. (초)"
                }
            }
        ]
    }

info
----

람다의 상세 정보를 포함합니다.

+--------------------+--------------+------------------------------------------------+
| Name               | Type         | Description                                    |
+====================+==============+================================================+
| name               | string       | **[필수]** 람다의 이름                         |
+--------------------+--------------+------------------------------------------------+
| version            | string       | 람다의 버전 정보 (``major.minor.patch``)       |
+--------------------+--------------+------------------------------------------------+
| category           | string       | 람다의 상위 분류                               |
+--------------------+--------------+------------------------------------------------+
| keywords           | string array | 키워드. 검색 및 분류에 사용                    |
+--------------------+--------------+------------------------------------------------+
| homepage           | string       | 홈페이지 주소                                  |
+--------------------+--------------+------------------------------------------------+
| bugs               | string       | 버그 발생시 리포팅할 주소                      |
+--------------------+--------------+------------------------------------------------+
| license            | string       | 라이선스 이름                                  |
+--------------------+--------------+------------------------------------------------+
| author             | string       | 작성자                                         |
+--------------------+--------------+------------------------------------------------+
| dependencies       | object array | 종속성 목록                                    |
+--------------------+--------------+------------------------------------------------+
| engines            | string       | 실행가능한 CORE 엔진 버전                      |
+--------------------+--------------+------------------------------------------------+
| environment        | object       | 람다를 작동시킬 구성 환경                      |
+--------------------+--------------+------------------------------------------------+
| titles             | object       | 화면에 출력할 타이틀명                         |
+--------------------+--------------+------------------------------------------------+
| descriptions       | object       | 화면에 출력할 람다의 간략한 정보               |
+--------------------+--------------+------------------------------------------------+
| documentation_mime | string       | 상세 문서를 작성할 경우 문서의 ``MIME`` 종류   |
+--------------------+--------------+------------------------------------------------+
| documentations     | object       | 문서의 본문                                    |
+--------------------+--------------+------------------------------------------------+
| meta               | object       | ``API`` 또는 ``WEB`` 과 상호작용 위한 정보     |
+--------------------+--------------+------------------------------------------------+

**dependencies** 객체는 아래의 속성을 포함합니다.

+----------+--------------+---------------+
| Name     | Type         | Description   |
+==========+==============+===============+
| type     | string       | 종속성의 종류 |
+----------+--------------+---------------+
| src      | string       | 패키지 이름   |
+----------+--------------+---------------+
| extra    | string array | 확장 명령 목록|
+----------+--------------+---------------+

**environment** 객체는 아래의 속성을 포함합니다.

+----------+--------------+-------------+
| Name     | Type         | Description |
+==========+==============+=============+
| type     | string       | 환경의 종류 |
+----------+--------------+-------------+
| name     | string       | 환경의 이름 |
+----------+--------------+-------------+

**titles**, **descriptions**, **documentations** 객체는
언어 코드에 해당하는 ``Key`` 와 내용에 해당하는 ``Value`` 를 내포합니다.

controls
--------

람다의 입출력 슬롯을 정의합니다.

**controls** 객체는 ``input`` 과 ``output`` 키를 갖고 있습니다.

**input**, **output** 객체는 아래의 속성을 포함합니다.

+----------+--------------+-------------+
| Name     | Type         | Description |
+==========+==============+=============+
| list     | object array | 슬롯 목록 |
+----------+--------------+-------------+
| dynamic  | bool         | 동적 슬롯 지원 여부 |
+----------+--------------+-------------+
| method   | string       | ``native``, ``numpy``, ``string`` 세 가지 방법 제공 |
+----------+--------------+-------------+

**list**, 객체는 아래의 속성을 포함합니다.

+----------+--------------+-------------+
| Name     | Type         | Description |
+==========+==============+=============+
| name     | string       | 슬롯의 이름 |
+----------+--------------+-------------+
| mimes    | string array | ``MIME`` 목록 |
+----------+--------------+-------------+

props
-----

람다의 속성 목록을 정의합니다.

**props** 객체는 아래의 속성을 포함합니다.

+----------+--------------+-------------+
| Name     | Type         | Description |
+==========+==============+=============+
| rule     | string       | ``initialize_only``, ``read_only``, ``read_and_write`` |
+----------+--------------+-------------+
| name     | string       | 속성 이름 |
+----------+--------------+-------------+
| default_value   | any       | 속성의 기본 값 |
+----------+--------------+-------------+
| type   | string       | str, bool, int, unsigned, size, float, double, json, csv, color, duration, byte, time, box_json |
+----------+--------------+-------------+
| required   | bool       | 필수 여부 |
+----------+--------------+-------------+
| valid   | object       | Validation 목록 |
+----------+--------------+-------------+
| title   | object       | 화면에 출력할 타이틀  |
+----------+--------------+-------------+
| help   | object       | 화면에 출력할 도움말 |
+----------+--------------+-------------+

- ``initialize_only``, ``read_only``, ``read_and_write`` 은 각각 ``init``, ``r``, ``rw`` 와 동일합니다.

**valid** 객체는 아래의 속성을 포함합니다.

+----------+--------------+-------------+
| Name     | Type         | Description |
+==========+==============+=============+
| list     | string       | 선택 목록 ``;`` 으로 구분합니다 |
+----------+--------------+-------------+
| hint     | string       | 힌트 목록 ``;`` 으로 구분합니다  |
+----------+--------------+-------------+
| min     | string       | 최소 값   |
+----------+--------------+-------------+
| max     | string       | 최대 값   |
+----------+--------------+-------------+
| dyhint   | string       | 유동적 힌트   |
+----------+--------------+-------------+
| password   | string       | 암호문 처리 |
+----------+--------------+-------------+

