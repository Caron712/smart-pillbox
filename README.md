#  요일별 스마트 서랍형 복약 관리 시스템
> **Smart Pill Box with BLE & IoT**

만성질환자 및 정기 복용자를 위한 ESP32 기반의 요일별 스마트 서랍형 복약 관리 시스템입니다.
요일별 LED 안내와 비접촉식 센서를 통해 사용자의 복약 여부를 자동으로 기록하고 스마트폰 앱으로 모니터링합니다.

---

## 📌 1. 프로젝트 개요 (Overview)
* **개발 배경**: 기존 플라스틱 약통의 망각으로 인한 중복 복용 위험 및 스마트폰 알림 무시 현상을 해결하고자 개발되었습니다.
* **핵심 컨셉**: 요일별 독립 서랍, 자동 요일 LED 안내, Hall 효과 센서 기반 비접촉식 개폐 감지, BLE 통신을 통한 앱 자동 기록 융합 시스템.

---

## 🚀 2. 주요 기능 (Key Features)
* **7개 독립 서랍 구조**: 월요일부터 일요일까지 7개의 물리적으로 분리된 서랍 제공
* **요일별 고유 LED 안내**: 오늘 날짜의 서랍에 지정된 고유 색상 LED가 점등/점멸하여 오복약 방지
* **비접촉식 개폐 실시간 감지**: 네오디뮴 자석과 Hall Effect 센서를 통해 서랍 열림/닫힘 정밀 감지 (30ms 디바운스 적용)
* **자동 복약 기록**: 복약 시간에 서랍을 열고 닫으면 스마트폰 앱에 복약 완료 시각 자동 저장
* **다중 알림 시스템**: 복약 시간 도달 시 LED 점멸 + 피에조 부저 알림음 + 스마트폰 푸시 알림
* **미복약 및 오개방 관리**: 30분 내 미개방 시 미복약 처리, 다른 요일 서랍 개방 시 경고 기록
* **가상 시뮬레이터 제공**: 하드웨어 없이도 테스트할 수 있는 앱 내 HW 시뮬레이터 탑재

---

## 🛠 3. 기술 스택 (Tech Stack)

### 하드웨어 (Hardware & Embedded)
* **MCU**: ESP32 Dev Module (NodeMCU-32S)
* **Sensors**: A3144 Hall Effect Sensor × 7, 네오디뮴 자석 × 7
* **Actuators & Display**: WS2812B Addressable RGB LED (NeoPixel) × 7, 5V Active Piezo Buzzer
* **Firmware**: C++ (Arduino Framework)

### 모바일 앱 (Mobile App)
* **Framework**: React Native (Expo SDK 57)
* **Language**: TypeScript
* **State Management**: React Context API (`PillBoxContext`)
* **Storage**: `@react-native-async-storage/async-storage`

### 무선 통신 (Communication)
* **Protocol**: BLE (Bluetooth Low Energy) GATT Server/Client Architecture
