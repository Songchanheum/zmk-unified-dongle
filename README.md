# ZMK Unified Dongle

Corne 스플릿 키보드(왼쪽/오른쪽)와 Adept BLE 마우스를 하나의 USB 동글로 연결하는 ZMK 펌웨어입니다.

## 구성

- **동글 (Central)**: nice!nano v2 (USB로 PC 연결, BLE로 주변기기 수신)
- **Corne 왼쪽 키보드**: Eyelash Corne 보드 + nice!view display
- **Corne 오른쪽 키보드**: Eyelash Corne 보드 + nice!view display
- **Adept 마우스**: Seeeduino XIAO BLE 보드

## 동글 모드 작동 방식

1. **동글**이 PC USB 포트에 연결
2. **동글**이 BLE를 통해 3개 주변기기 수신:
   - Corne 왼쪽 키보드
   - Corne 오른쪽 키보드
   - Adept 마우스
3. **동글**이 모든 입력을 USB HID로 PC에 전달

## 빌드

GitHub Actions가 자동으로 4개의 펌웨어를 빌드합니다:

- `dongle_central.uf2` - 동글용 펌웨어
- `corne_left_peripheral.uf2` - 왼쪽 키보드용 펌웨어
- `corne_right_peripheral.uf2` - 오른쪽 키보드용 펌웨어
- `adept_peripheral.uf2` - 마우스용 펌웨어

## 플래싱 방법

1. **동글**: nice!nano v2를 부트로더 모드로 진입 후 `dongle_central.uf2` 복사
2. **왼쪽 키보드**: `corne_left_peripheral.uf2` 플래시
3. **오른쪽 키보드**: `corne_right_peripheral.uf2` 플래시
4. **마우스**: `adept_peripheral.uf2` 플래시

## 사용법

1. 동글을 PC USB에 연결
2. 왼쪽 키보드, 오른쪽 키보드, 마우스를 각각 켜기
3. 자동으로 페어링되며 PC에서는 하나의 HID 장치로 인식

## 키맵 커스터마이징

`config/eyelash_corne.keymap` 파일을 수정하여 키 배치를 변경할 수 있습니다.

## 원본 저장소

- [zmk-new_corne](https://github.com/Songchanheum/zmk-new_corne) - Eyelash Corne 설정
- [mouse-test](https://github.com/Songchanheum/mouse-test) - Adept BLE 마우스 설정

## 라이선스

MIT License

