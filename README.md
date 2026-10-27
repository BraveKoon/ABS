# ABS 로봇 심판 (탁구공 추적 스트라이크/볼 판정)

카메라로 주황 탁구공을 추적해 스트라이크존 통과 여부를 자동 판정하는 웹앱입니다.
브라우저 단독 동작(서버 없음)이며 영상은 기기 밖으로 전송되지 않습니다.

## 바로 사용하기

GitHub Pages: https://bravekoon.github.io/ABS/

> 카메라(`getUserMedia`)는 HTTPS 에서만 동작합니다. GitHub Pages 주소는 HTTPS 이므로 그대로 사용할 수 있습니다.
> 로컬에서 파일을 직접 열면(`file://`) 카메라가 동작하지 않습니다.

## 사용법

1. 카메라를 포수 뒤(또는 타자 옆)에서 스트라이크존 쪽을 향하게 둡니다.
2. **카메라 시작** 을 눌러 권한을 허용합니다.
3. **🎨 공 색 찍기** 로 화면 속 공을 여러 번 탭해 색을 학습시킵니다.
4. **🎯 존 조정** 으로 주황 박스를 끌어 스트라이크존을 맞춥니다.
5. 공을 던지면 **판정 크기** 에 닿는 순간의 위치로 스트라이크/볼을 판정합니다.

설정(공 색, 존 위치, 옵션)은 브라우저에 자동 저장됩니다.

## 파일

| 파일 | 설명 |
| --- | --- |
| `index.html` | GitHub Pages 로 서비스되는 앱 본체 |
| `abs_system.html` | `index.html` 과 동일한 사본 |
| `worker.js` | Cloudflare Worker 단일 파일 배포용(같은 앱을 HTML 문자열로 포함) |

### Cloudflare Workers 로 배포하려면

Workers & Pages > Create > Worker > Edit code 에 `worker.js` 전체를 붙여넣고 Deploy 하면
`*.workers.dev` HTTPS 주소에서 동일하게 동작합니다.
