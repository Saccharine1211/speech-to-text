# Speech to Text

선택한 마이크로 한국어 음성을 듣고, `안녕`이라는 wake word가 인식되면 다음 문장 하나를 텍스트로 출력하는 Python 프로그램입니다.

## 동작 방식

1. 입력 채널이 있는 PyAudio 장치를 출력합니다.
2. 사용할 장치 인덱스를 입력받습니다.
3. 주변 소음을 보정합니다.
4. Google Speech Recognition을 `ko-KR`로 호출하며 계속 듣습니다.
5. 인식 결과에 `안녕`이 포함될 때까지 기다립니다.
6. 다음 음성을 한 번 더 인식하고 결과를 출력한 뒤 종료합니다.

## 요구 사항

- Python 3
- 작동하는 마이크와 마이크 권한
- 인터넷 연결
- `SpeechRecognition`
- `PyAudio`

```bash
pip install SpeechRecognition PyAudio
```

운영체제에 따라 `PyAudio` 설치에 추가 오디오 라이브러리가 필요할 수 있습니다.

## 실행

```bash
python speech_to_text.py
```

프로그램이 출력하는 장치 번호는 PyAudio의 실제 device index입니다. 화면에 표시된 순번과 연속적이지 않을 수 있으므로 출력된 번호를 그대로 입력하세요.

대기 중에는 `안녕`이 포함되지 않은 음성을 무시하고 계속 듣습니다. 성공하면 `인식된 문장:` 뒤에 결과를 출력합니다.

## 인식과 오류 처리

- 인식 언어는 `ko-KR`로 고정되어 있습니다.
- 인식 불가 음성(`UnknownValueError`)은 조용히 무시합니다.
- Google 요청 오류(`RequestError`)는 메시지를 출력하고 종료합니다.
- 잘못된 장치 번호, 권한 오류, 장치 초기화 실패, `Ctrl+C` 외 예외는 별도로 검증하지 않습니다.

## 제한 사항

- wake word `안녕`과 인식 언어를 명령줄에서 바꿀 수 없습니다.
- wake word 이후 한 문장만 처리합니다.
- 결과를 파일에 저장하지 않습니다.
- 시간 제한, phrase 길이 제한, 연속 자막 모드가 없습니다.
- Google 음성 인식 서비스에 의존하므로 네트워크가 필요합니다.
- `requirements.txt`, 테스트, 설정 파일, 라이선스가 없습니다.

## 구조

```text
speech_to_text.py
README.md
.gitattributes
```

중지하려면 실행 중 `Ctrl+C`를 누르세요.

## 라이선스

저장소에 라이선스가 명시되어 있지 않습니다.
