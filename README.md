# painterly-oil-style

원본의 인물과 구도를 살리면서 얼굴은 부드럽게 회화적으로, 머리카락은 결을 따라 붓질이 보이게, 옷과 배경은 더 풍부한 질감으로 표현하는 Codex 스킬입니다.

## 예시

얼굴에는 은은한 색층과 부드러운 명암을, 머리카락에는 결을 따라 흐르는 붓질을 더했습니다. 옷감과 잔디에는 더 풍부한 유화 질감을 살렸습니다.

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

변환할 이미지를 첨부하고 Codex에서 다음처럼 요청하세요.

```text
$painterly-oil-style 이 사진을 부드럽고 풍부한 유화풍으로 바꿔줘.
```

스킬은 얼굴 특징과 표정을 보존하면서 피부에도 부드러운 색층을 넣어 회화감을 유지합니다. 머리카락에는 흐름을 따라 보이는 붓질을, 옷과 배경에는 더 풍부한 페인팅 질감을 적용합니다.

원하는 균형을 더 구체적으로 말할 수도 있습니다.

- “얼굴은 부드럽고 알아볼 수 있게, 머리카락 붓질은 조금 더 보이게 해줘.”
- “선처럼 긁힌 붓자국은 줄이되 유화 질감은 유지해줘.”
- “옷과 배경의 색층과 붓질을 더 풍부하게 해줘.”

이미지 편집 도구에 따라 얼굴이 원본과 조금 달라질 수 있습니다. 결과에서 얼굴과 표정을 확인하고, 차이가 보이면 얼굴 보존을 우선한 수정 요청을 덧붙이세요.

