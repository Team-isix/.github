<div align="center">

<img src="https://raw.githubusercontent.com/Team-isix/.github/main/banner-closr-white.svg" width="100%" />

</div>

<br />

## 👥 팀원 소개

<div align="center">

<table>
  <tr>
    <td align="center" width="120"><br/><br/><br/>구나영<br/><br/></td>
    <td align="center" width="120"><a href="https://github.com/copepb"><img src="https://github.com/copepb.png" width="100"/><br/>김민호</a></td>
    <td align="center" width="120"><a href="https://github.com/ryudayeong"><img src="https://github.com/ryudayeong.png" width="100"/><br/>류다영</a></td>
    <td align="center" width="120"><br/><br/><br/>성현서<br/><br/></td>
    <td align="center" width="120"><a href="https://github.com/ckrhkdwls"><img src="https://github.com/ckrhkdwls.png" width="100"/><br/>차광진</a></td>
    <td align="center" width="120"><br/><br/><br/>황연준<br/><br/></td>
  </tr>
</table>

</div>

## 🎯 프로젝트 소개

> **내 몸 위의 3D 가상 아틀리에**

한 장의 사진으로 3D 아바타를 생성하고, 물리 시뮬레이션 기반으로 의류 사이즈를 추천하는 가상 피팅 플랫폼입니다.

기존 가상 피팅은 대부분 2D 이미지 합성으로, 옷과 몸의 공간 관계를 계산하지 않습니다.
**CLOSER는 합성이 아니라 물리 연산을 합니다.**

<br />

## ✨ 핵심 기능

| | 기능 | 내용 |
|:---:|---|---|
| **①** | **신체 비율 판단** | 전신 사진 1장 + 키·몸무게로 3D 아바타 생성, 12개 부위 치수 자동 계측 |
| **②** | **체형 유형 진단** | 역삼각형·직사각형·모래시계형 등 체형 타입 판정 |
| **③** | **가상 피팅** | 아바타에 의류 착용 · 360° 회전 · 핏 히트맵 · 사이즈 추천 |
| **④** | **피팅 저장** | 아바타와 피팅 결과를 계정에 저장, 재방문 시 복원 |

<br />

## 🏗 AI 아키텍처

**[사전 계산 · GPU]** 표준 마네킹 → 패턴 18개 → 체형 12구간 드레이핑 → GLB 216개

**[실시간 · CPU]** 사진 → β → 3D 메시 → 치수 12개 → 최근접 GLB 조회

의류 시뮬레이션은 1벌당 30초~2분 소요 → 런타임 실행 불가.
의류 6종 × 사이즈 3 × 체형 12구간 = **216개 사전 계산**, 실시간엔 최근접 결과 조회.

<br />

## 🚀 로컬 실행

```bash
# 1. 레포 클론
git clone https://github.com/Team-isix/CLOSER-AI.git
git clone https://github.com/Team-isix/CLOSER-BE.git
git clone https://github.com/Team-isix/CLOSER-FE.git

# 2. AI 서버
cd CLOSER-AI && pip install -r requirements.txt && python main.py

# 3. BE 서버 (Java 17+, Gradle)
cd CLOSER-BE && ./gradlew bootRun

# 4. FE
cd CLOSER-FE && npm install && npm run dev
```

> `.env` 파일 설정 필요

<br />

<div align="center">

<img src="https://raw.githubusercontent.com/Team-isix/.github/main/footer.svg" width="100%" />

</div>
