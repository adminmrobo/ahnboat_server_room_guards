# 서버실 지킴이 (Server Room Guards)

ahnboat.xyz 서버실(Reon Ahn's Lab Server)을 지키는 조수 **하루**와 인턴 **시아(No.005)**·**모아(No.006)**의 픽셀아트 루프 영상 모음입니다.

- 미리보기: https://adminmrobo.github.io/ahnboat_server_room_guards/
- 캐릭터 원본: [fruitfly-lab-expressions](https://github.com/adminmrobo/fruitfly-lab-expressions)

## 폴더

| 폴더 | 내용 |
|---|---|
| `loops/` | 루프 영상 3편 — `SR_{haru,sia,moa}_loop.webm`(웹 권장) · `.mp4`(예비) · `_poster.jpg`(첫 화면) |
| `web/` | 페이지용으로 줄인 정지 그림 (576×1024) |
| `stills/` | 컷별 원본 정지 그림 17장 (1152×2048) |
| `docs/` | Genspark 제작 지침서 · 조립 설계도 · 제작 메모 |

## 규격

세로 9:16 · 720×1280 · 24fps · **세 편 모두 12초** · 무음 · 마지막 장면이 첫 장면 자세로 돌아오는 루프.

## 붙이는 법

```html
<video autoplay loop muted playsinline
       poster="https://adminmrobo.github.io/ahnboat_server_room_guards/loops/SR_sia_poster.jpg">
  <source src="https://adminmrobo.github.io/ahnboat_server_room_guards/loops/SR_sia_loop.webm" type="video/webm">
  <source src="https://adminmrobo.github.io/ahnboat_server_room_guards/loops/SR_sia_loop.mp4" type="video/mp4">
</video>
```

`muted`와 `playsinline`은 모바일 자동재생 조건이라 꼭 넣습니다.

## 고친 기록

- v2 (2026-11-14): 모아 루프를 13.38초 → 12초로 맞추고 끝 0.5초를 첫 장면으로 부드럽게 넘어가게 해 이음매 튐을 없앰. mp4·첫 화면 이미지 경량화(PNG → JPG).

---
글 · 안상선 ((주)M-Robo 대표)
