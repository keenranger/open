# Open

딥링크를 웹에서 열어주는 리다이렉터.

## Usage

### Generic
```
https://keenranger.github.io/open/?url=kakaomap://route?sp=37.5,127.0%26ep=37.4,127.1
```

### Presets
| Path | Destination |
|------|-------------|
| `/home` | 집 (수서) |
| `/work` | 회사 (에이슬립, 저스트코타워) |
| `/home-to-work` | 집 → 회사 |
| `/station` | 청량리역 |
| `/wedding` | 아만티호텔 (3/28 결혼식) |

### Features
- 모바일: 앱 딥링크로 이동
- PC: 웹 폴백 (User-Agent 감지)
- 단축 URL = 커밋으로 추가 (DB 없음!)

## Add New Preset

```bash
mkdir new-place
cat > new-place/index.html << 'EOF'
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <script>
    window.location.href = 'kakaomap://route?ep=위도,경도&by=publictransit';
  </script>
</head>
<body><a href="...">Click here</a></body>
</html>
EOF
git add . && git commit -m "Add new-place" && git push
```
