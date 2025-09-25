# 🏋️‍♂️ AI Posture Coach (실시간 자세 교정 AI 코치)

`AI Posture Coach`는 웹캠을 통해 사용자의 자세를 실시간으로 분석하고, 나쁜 자세일 경우 즉각적인 피드백을 제공하여 바른 자세를 유지하도록 돕는 데스크톱 애플리케이션입니다. 이 프로젝트는 장시간 앉아서 생활하는 현대인들의 고질적인 문제인 거북목과 굽은 허리를 예방하는 것을 목표로 합니다.

<br>
&lt;p align=&quot;center&quot;&gt;
  &lt;img src=&quot;https_placehold.co/700x400?text=Project+Demo+GIF&quot; alt=&quot;Project Demo GIF&quot;&gt;
&lt;/p&gt;
<br>

## ✨ 주요 기능 (Features)

  * [cite\_start]**실시간 자세 분석**: 웹캠 영상 위에서 사용자의 신체 주요 부위를 실시간으로 추적합니다. [cite: 9]
  * [cite\_start]**2가지 핵심 자세 감지**: 거북목(Forward Head Posture)과 굽은 허리(Slumped Posture)를 중점적으로 탐지합니다. [cite: 5]
  * [cite\_start]**즉각적인 시각적 피드백**: 자세가 올바를 때는 화면 테두리가 **녹색**으로, 나빠졌을 때는 **빨간색**으로 변하여 사용자에게 즉각적인 신호를 줍니다. [cite: 32]
  * [cite\_start]**알림 기능 (구현 예정)**: 나쁜 자세가 일정 시간 이상 지속되면 소리나 텍스트 팝업으로 사용자에게 경고합니다. [cite: 37]

## 🤔 어떻게 작동하나요? (How It Works)

[cite\_start]이 프로그램은 `MediaPipe Pose` 라이브러리를 사용하여 웹캠 영상에서 사용자의 주요 신체 부위(귀, 어깨, 고관절, 무릎)를 식별합니다. [cite: 9] 식별된 좌표를 바탕으로 두 가지 핵심 각도를 계산하여 자세를 판단합니다.

1.  **거북목 (Forward Head Posture) 판단**
      * [cite\_start]**기준**: '귀-어깨' 선과 '어깨-고관절' 선 사이의 각도(CVA)를 측정합니다. [cite: 10]
      * [cite\_start]**경고**: 이 각도가 `50도 미만`일 경우 거북목으로 판단합니다. [cite: 12]
2.  **굽은 허리 (Slumped Posture) 판단**
      * [cite\_start]**기준**: '어깨-고관절-무릎' 사이의 각도를 측정합니다. [cite: 13]
      * [cite\_start]**경고**: 이 각도가 `90도 미만`일 경우 굽은 허리로 판단합니다. [cite: 15]

## 🛠️ 기술 스택 (Tech Stack)

  * [cite\_start]**Python**: 메인 프로그래밍 언어 [cite: 24]
  * [cite\_start]**OpenCV**: 웹캠 영상 처리 및 화면 출력 [cite: 24]
  * [cite\_start]**MediaPipe**: 구글의 오픈소스 ML 솔루션으로, 신체 랜드마크를 추정하는 데 사용 [cite: 24]
  * [cite\_start]**(Optional) Tkinter**: 시작/종료 버튼 등 간단한 GUI 구현 [cite: 39]

## 🚀 시작하기 (Getting Started)

### 사전 요구 사항 (Prerequisites)

  * Python 3.7 이상
  * 웹캠

### 설치 및 실행 (Installation & Usage)

1.  **저장소 복제 (Clone)**

    ```bash
    git clone https://github.com/YOUR_USERNAME/ai-posture-coach.git
    cd ai-posture-coach
    ```

2.  **가상 환경 생성 및 활성화**

    ```bash
    # Windows
    python -m venv venv
    venv\Scripts\activate

    # macOS / Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **필요 라이브러리 설치**

    ```bash
    pip install -r requirements.txt
    ```

4.  **프로그램 실행**

    ```bash
    python src/main.py
    ```

-----

**`requirements.txt` 파일 내용:**

```txt
opencv-python
mediapipe
```

-----

## 🗺️ 프로젝트 로드맵 (Roadmap)

[cite\_start]이 프로젝트는 효율적인 단독 개발을 위해 단계별 실행 계획에 따라 진행되었습니다. [cite: 2, 20]

  * [cite\_start][✔️] **1단계: 핵심 기술 검증** [cite: 21]

      * [cite\_start][✔️] 웹캠 영상 위에 MediaPipe 랜드마크 표시 [cite: 26]
      * [cite\_start][✔️] 2가지 핵심 자세(거북목, 굽은 허리) 각도 계산 및 출력 [cite: 27]

  * [cite\_start][✔️] **2단계: 최소 기능 제품(MVP) 완성** [cite: 28]

      * [cite\_start][✔️] 각도에 따른 '좋은/나쁜' 자세 판별 로직 구현 [cite: 31]
      * [cite\_start][✔️] 자세 상태에 따른 화면 테두리 색상 변경 (시각적 피드백) [cite: 32]

  * [cite\_start][🚧] **3단계: 기능 확장 및 고도화** [cite: 34]

      * [cite\_start][🚧] 나쁜 자세 지속 시 소리/텍스트 알림 기능 [cite: 37]
      * [cite\_start][ ] 시작/종료 버튼을 포함한 기본 UI 제작 [cite: 39]
      * [cite\_start][ ] 캘리브레이션(자세 교정) 기능 추가 [cite: 33]

  * [cite\_start][ ] **4단계: 최종 테스트 및 문서화** [cite: 41]

      * [cite\_start][ ] 다양한 환경에서의 테스트 및 버그 수정 [cite: 44]
      * [cite\_start][ ] 최종 보고서 및 발표 자료 작성 [cite: 46]

## 📄 라이선스 (License)

이 프로젝트는 MIT 라이선스를 따릅니다. 자세한 내용은 `LICENSE` 파일을 참고하세요.
