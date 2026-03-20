# multi-tokens
multicamp design token hand-off

## 프로젝트 구조

```
multi-tokens/
└── data/
    └── tokens.json    # 디자인 토큰 정의 파일
```

## 사용 방법

이 저장소는 [Tokens Studio for Figma](https://tokens.studio/) 플러그인과 연동하여 디자인 토큰을 관리합니다.

### 1. Tokens Studio에서 불러오기

1. Figma에서 **Tokens Studio** 플러그인을 실행합니다.
2. 설정(Settings)에서 **Sync Providers** > **GitHub**를 선택합니다.
3. 이 저장소의 URL, 브랜치, 토큰 파일 경로(`data/tokens.json`)를 입력합니다.
4. 연동이 완료되면 토큰을 Figma에서 바로 사용할 수 있습니다.

### 2. 토큰 구조

`data/tokens.json` 파일은 4개의 토큰 세트로 구성되어 있습니다:

| 토큰 세트 | 설명 |
|-----------|------|
| **core** | 기본 토큰 (색상, 타이포그래피, 간격, 그림자 등) |
| **light** | 라이트 테마 시맨틱 토큰 |
| **dark** | 다크 테마 시맨틱 토큰 |
| **theme** | 컴포넌트 레벨 토큰 (버튼, 카드 등) |

### 3. 주요 토큰 종류

- **Colors**: gray, red, orange, yellow, green, teal, blue, indigo, purple, pink (100~900 단계)
- **Typography**: Heading, Label, Paragraph 스타일 (Pretendard Variable, Inter, Roboto 폰트)
- **Dimension / Spacing**: xs, sm, md, lg, xl (scale 기반 자동 계산)
- **Border Radius**: sm(4), lg(8), xl(16)
- **Box Shadow**: innerShadow + dropShadow 조합
- **Opacity**: low(10%), md(50%), high(90%)

### 4. 개발자를 위한 활용

[Style Dictionary](https://amzn.github.io/style-dictionary/)나 [Token Transformer](https://www.npmjs.com/package/token-transformer) 등의 도구를 사용하여 `tokens.json`을 CSS 변수, SCSS, JavaScript 등 원하는 형식으로 변환할 수 있습니다.

```bash
# 예시: token-transformer 사용
npx token-transformer data/tokens.json output/tokens.json core,light,theme core

# 예시: Style Dictionary로 CSS 변수 생성
npx style-dictionary build
```
