# OL:TC FastDL

Left 4 Dead 2 서버가 배포하는 커스텀 파일입니다.
게임 폴더와 **같은 구조**로 두었기 때문에, 이 저장소의 Pages 주소를
그대로 `sv_downloadurl` 에 넣으면 됩니다.

```
sv_allowdownload 1
sv_downloadurl "https://<USER>.github.io/<REPO>"
```

## 왜 웹서버인가

게임 서버가 직접 보내면 초당 20KB 안팎으로 묶여 있어, 4MB 짜리 모델
하나에 접속마다 3분이 넘게 걸립니다. 같은 파일을 웹에 올려두면 몇 초입니다.

## 파일 목록의 출처

`Core/CustomAssets.sp` 의 `AddFileToDownloadsTable` 선언이 유일한 출처입니다.
`tools/sync_downloads.py` 가 그 목록을 읽어 이 폴더를 채웁니다 —
목록을 두 군데 적으면 반드시 어긋나기 때문입니다.

## 포함된 것

| | |
|---|---|
| `models/oltc/w_m200.*` | M200 (CheyTac Intervention) 월드모델 |
| `materials/models/weapons/*/sr08/` | 그 모델이 참조하는 재질 |

원본: Steam 워크샵 **"WF M200"** (제작 Cele). 스킬이 소환하는 월드모델과
그것이 참조하는 재질만 담았습니다.

## .nojekyll

GitHub Pages 는 기본으로 Jekyll 을 돌리는데, 그러면 일부 폴더와 파일이
무시됩니다. 이 파일이 그걸 끕니다 — **지우지 마세요.**
