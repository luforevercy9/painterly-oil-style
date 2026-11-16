# painterly-oil-style

이미지의 인물과 구도, 분위기를 유지하면서 층이 있는 색감과 은은한 붓질로 유화풍을 적용하는 Codex 스킬입니다. 사진에서는 얼굴의 정체성과 표정을 페인팅 질감보다 우선합니다. 얼굴과 피부는 매끄럽게 표현하고, 질감은 주로 머리카락·옷·배경에 더합니다.

## 예시

아래는 스킬을 적용한 예시입니다. 얼굴은 부드럽게 묘사하고, 옷과 배경에는 선처럼 튀지 않는 색층과 회화 질감을 남겼습니다.

![painterly-oil-style 적용 예시](example-painterly-oil-style.png)

## 설치

저장소를 내려받은 뒤, PowerShell에서 저장소 폴더 안에서 실행하세요.

```powershell
$skillDir = if ($env:CODEX_HOME) {
  Join-Path $env:CODEX_HOME 'skills\painterly-oil-style'
} else {
  Join-Path $HOME '.codex\skills\painterly-oil-style'
}

New-Item -ItemType Directory -Force -Path $skillDir | Out-Null
Copy-Item .\SKILL.md (Join-Path $skillDir 'SKILL.md') -Force
```

## 사용

Codex에서 변환할 이미지를 첨부하고 스킬을 호출하세요.

```text
$painterly-oil-style 이 사진을 부드러운 유화풍으로 바꿔줘.
```

기본적으로 인물 수, 얼굴의 특징과 표정, 포즈, 배치, 프레이밍, 원본 조명과 분위기를 유지하도록 합니다. 얼굴에는 눈에 띄는 붓자국과 캔버스 결을 거의 쓰지 않고, 회화 질감은 머리카락·옷·배경에 집중합니다.

## 표현 조절 예시

- **얼굴 보존 우선:** “인원수와 얼굴 특징·표정을 원본대로 유지하고, 피부에는 붓자국이 거의 보이지 않게 해줘.”
- **질감은 남기고 선 자국만 완화:** “유화 질감은 유지하되 선처럼 보이는 붓자국을 부드럽게 섞어줘.”
- **붓질을 조금 더 드러내기:** “옷과 배경의 붓질과 색층을 조금 더 표현적으로 해줘.”
- **더 부드러운 마감:** “전체 질감은 약간 줄이되 색층은 남겨줘.”

이미지 편집 도구에 따라 얼굴이 원본과 조금 달라질 수 있습니다. 결과에서 얼굴 특징과 표정을 확인하고, 차이가 보이면 얼굴 보존을 우선한 수정 요청을 덧붙이세요. 장면 안에서 의미가 있는 글자와 로고는 요청에 따라 보존할 수 있습니다. 워터마크나 URL은 따로 남겨달라는 요청이 없다면 생략될 수 있습니다.


