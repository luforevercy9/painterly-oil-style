# painterly-oil-style

이미지의 인물과 구도, 분위기를 유지하면서 은은한 붓질과 색층이 살아 있는 유화풍으로 변환하는 Codex 스킬입니다. 기본 표현은 피부와 주요 형태를 부드럽게 묘사하고, 옷·머리카락·배경에는 선처럼 튀지 않는 회화 질감을 더합니다.

## 예시

아래 이미지는 스킬을 적용한 결과입니다. 다섯 인물의 배치와 창가의 차분한 분위기를 유지하면서, 색층과 붓질을 유화풍으로 표현했습니다.

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
$painterly-oil-style 이 사진을 부드럽고 질감 있는 유화풍으로 바꿔줘.
```

특별히 지정하지 않으면 스킬은 원본의 인물 수, 정체성, 표정, 포즈, 배치, 프레이밍, 조명과 분위기를 유지하려고 합니다. 이미지 종류에 맞춰 사진·일러스트·풍경·사물의 형태를 살리고, 붓질은 색과 명암에 자연스럽게 섞이도록 합니다.

## 결과 조절 예시

원하는 표현을 요청에 덧붙여 강도를 조절할 수 있습니다.

- **질감은 유지하고 선 자국만 부드럽게:** “유화 질감은 남기되 선처럼 보이는 붓자국을 더 은은하게 해줘.”
- **붓질을 더 드러내기:** “붓질과 색층을 조금 더 표현적으로 해줘.”
- **더 부드러운 마감:** “표면 질감을 줄이고 색 경계를 부드럽게 섞어줘.”
- **원본 세부 요소 유지:** “인원수, 구도, 표정, 의상과 조명을 최대한 유지해줘.”

장면 안에서 의미가 있는 글자와 로고는 요청에 따라 보존할 수 있습니다. 워터마크나 URL은 별도로 남겨달라는 요청이 없다면 결과에서 생략될 수 있습니다.
