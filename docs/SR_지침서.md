# 서버실 지킴이 — 조수(하루)·시아·모아 루프 영상 Genspark 지침서

ahnboat.xyz 서버실(Reon Ahn's Lab Server)의 입구와 안쪽에 둘 세로 루프 영상 세트입니다.
콘셉트는 **"서버실을 지키는 조수와 인턴들"** 입니다. 하루의 기존 영상 두 편(2026-11-12·13 카카오톡 영상)을 템플릿으로 삼고, 시아·모아도 같은 방, 같은 화풍, 같은 길이로 만듭니다. 자세는 캐릭터 성격에 맞춰 더 다양하게 넣었습니다.

---

## 0. 규격 (세 캐릭터 공통)

| 항목 | 값 |
|---|---|
| 화면 | 세로 9:16 (템플릿 406×720 이상, 가능하면 720×1280) |
| 길이 | 편당 10~15초, 컷당 약 2~5초 |
| 소리 | 없음 (웹 자동재생용) |
| 루프 | **마지막 컷의 자세를 첫 컷과 같게** 끝냄 → 반복해도 끊김이 안 보임 |
| 화풍 | 템플릿과 같은 **정밀한 애니메이션풍 픽셀아트**, 따뜻한 호박색 조명, 디더링 음영 (치비 아님) |
| 배경 | 같은 서버실 한 곳 (아래 공통 토큰) — 캐릭터마다 자리만 다름 |
| 텍스트 | 화면 안 글자 없음 |

## 1. 템플릿 컷 구조 (하루 영상 분석)

| 박자 | 템플릿 장면 | 역할 |
|---|---|---|
| ① 도입 | 책상에서 모니터 보며 타이핑 (넓게 → 가깝게) | "일하는 중" |
| ② 주 자세 | 위에서 내려다본 구도, 의자에 앉아 올려다봄 | 시청자와 눈 맞춤 |
| ③ 표정 변화 | 쉿 제스처 → 눈 감고 미소 | 성격 한 방 |
| ④ 전환 | 눈 클로즈업 (화면 꽉 채움, 1.5초) | 시그니처 컷 |
| ⑤ 마무리 | 손 흔들며 웃음 → 다시 ②의 자세 | 인사 + 루프 연결 |

시아·모아도 이 다섯 박자를 그대로 따르되, ①·③에 들어갈 동작을 각자 성격에 맞게 바꿉니다.

## 2. 공통 토큰 (모든 프롬프트에 이미 들어 있음)

```yaml
SERVER_ROOM_EN: "a cozy small server room at night, rows of dark server racks with tiny blinking green and amber LED lights, neatly bundled cables, a warm amber pendant lamp, a wooden desk with a monitor showing a teal line graph, a small round wooden stool, dark wooden floor"
STYLE_EN: "detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal monitor glow, same art style and lighting as the attached template frame, vertical 9:16, no text, no letters, no logo, no watermark"
NEGATIVE_EN: "chibi, blurry, smooth vector art, 3D render, photorealistic, off-model, extra characters, text, letters, watermark, white robot"
```

## 3. 만드는 순서

1. **첫 프레임(정지 그림)부터** — 컷마다 이미지 프롬프트로 정지 그림을 먼저 만듭니다.
   - 첨부: ① 그 캐릭터의 설정 시트 (`refs/original/sia_sheet.png` · `moa_sheet.png` · `haru_sheet.png`) ② 그 캐릭터의 `E13_neutral.png` ③ 구도가 같은 템플릿 프레임 (`T1~T5`, 이 지침서와 함께 드림)
   - 앞에 붙일 한국어 한 줄: *"첫 두 그림의 캐릭터와 똑같은 얼굴·머리·옷·색으로, 세 번째 그림과 같은 구도와 화풍으로, 아래 영어 프롬프트대로 그려 줘."*
   - **각 캐릭터의 ② 주 자세 컷을 가장 먼저** 만들고, 마음에 드는 결과를 나머지 컷의 참고 그림으로 함께 넣습니다 (배경·조명이 맞춰짐).
2. **정지 그림 → 영상** — 그 그림을 첫 프레임으로 넣고 아래 "움직임" 프롬프트를 씁니다.
3. **이어 붙이기** — 컷 영상들을 Claude에게 주시면 순서대로 잇고, 웹용(mp4·webm, 0.5MB 안팎)으로 줄이고, 첫 화면 이미지를 함께 만들어 드립니다.

파일 이름: `SR_시트번호_컷.png / .mp4` (예: `SR_S2_topdown.png`, `SR_M4_eye.mp4`)

---

## 4. 시아 — "조용히 기록하는 야간 당직" (SR-S1 ~ SR-S6)

성격: 조용하고 꼼꼼함, 말수 적음, 집중이 끊기면 하품. **머리 장식 없음**(생기면 실패).

```yaml
SIA_EN: "Sia, a calm anime girl maid intern, long straight jet-black hair reaching the waist with side-swept bangs and two thin strands framing the face, calm gray eyes with slightly lowered lids, small silver drop earrings, light peach skin, long-sleeved charcoal-black maid dress with puffed shoulders and white lace cuffs, white high collar with a large soft gray bow, long white frilled apron, no headdress, no glasses"
```

### SR-S1 · 도입 · 랙 앞에서 점검표 체크 (3초) — 첨부 T1
```
Sia, a calm anime girl maid intern, long straight jet-black hair reaching the waist with side-swept bangs and two thin strands framing the face, calm gray eyes with slightly lowered lids, small silver drop earrings, light peach skin, long-sleeved charcoal-black maid dress with puffed shoulders and white lace cuffs, white high collar with a large soft gray bow, long white frilled apron, no headdress, no glasses, standing in the aisle between server racks, holding a clipboard in one hand and a pen in the other, looking at the blinking LEDs with a serious calm expression, three-quarter view, medium shot, in a cozy small server room at night, rows of dark server racks with tiny blinking green and amber LED lights, neatly bundled cables, a warm amber pendant lamp, dark wooden floor, detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal monitor glow, same art style and lighting as the attached template frame, vertical 9:16, no text, no letters, no logo, no watermark
```
움직임: `she ticks a box on the clipboard with small precise pen strokes, glances up at the rack, server LEDs blink, static camera, subtle motion, pixel art style preserved, character identity unchanged`

### SR-S2 · 주 자세 · 위에서 내려다본 구도, 스툴에 앉아 올려다봄 (4초) — 첨부 T2 · **가장 먼저 제작**
```
Sia, a calm anime girl maid intern, long straight jet-black hair reaching the waist with side-swept bangs and two thin strands framing the face, calm gray eyes with slightly lowered lids, small silver drop earrings, light peach skin, long-sleeved charcoal-black maid dress with puffed shoulders and white lace cuffs, white high collar with a large soft gray bow, long white frilled apron, no headdress, no glasses, sitting on a small round wooden stool next to a server rack, hands resting neatly on her lap on the apron, looking straight up at the viewer with a quiet small smile, high-angle top-down view, full body, a clipboard leaning against the stool, in a cozy small server room at night, rows of dark server racks with tiny blinking green and amber LED lights, neatly bundled cables, a warm amber pendant lamp at the top of the frame, dark wooden floor, detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal monitor glow, same art style and lighting as the attached template frame, vertical 9:16, no text, no letters, no logo, no watermark
```
움직임: `gentle breathing, slow blink, hair strands sway slightly, server LEDs blink, lamp glow flickers softly, static camera, pixel art style preserved, character identity unchanged`

### SR-S3 · 표정 변화 · 하품하다가 들킴 (3초) — 첨부 SR-S2 결과
```
(SR-S2 프롬프트에서 "looking straight up at the viewer with a quiet small smile" 를 아래로 교체)
covering a big yawn with one hand, eyes squeezed shut with a tiny tear at the corner
```
움직임: `she yawns behind her hand, then notices the viewer, opens her eyes wide and quickly straightens her posture with a faint blush, static camera, pixel art style preserved, character identity unchanged`

### SR-S4 · 전환 · 회색 눈 클로즈업 (1.5초) — 첨부 T4
```
Extreme close-up of one calm gray anime eye with slightly lowered lid, long dark lashes, jet-black hair strands crossing the frame, light peach skin, tiny green and amber server LED lights reflected in the iris, detailed anime pixel art illustration, crisp pixels, dithering shading, same art style as the attached template frame, vertical 9:16, no text
```
움직임: `one slow blink, the reflected LED lights twinkle, very slight push-in, pixel art style preserved`

### SR-S5 · 마무리 · 조용한 인사 (3초) — 첨부 T5 + SR-S2 결과
```
(SR-S2 프롬프트에서 손·표정 부분을 아래로 교체)
giving a small polite wave with one hand raised to shoulder height, the other hand on her lap, a soft gentle smile, slight head tilt
```
움직임: `a small gentle wave of two or three motions, then her hand returns to her lap and she settles back into the starting pose, static camera, pixel art style preserved, character identity unchanged`

### SR-S6 (대체 컷) · 책상에 엎드려 졸다가 깜짝 (3초)
③을 이 컷으로 바꿔도 됩니다. 시아의 원본 일러스트(06_Sleeping)와 이어지는 장면입니다.
```
Sia, a calm anime girl maid intern, long straight jet-black hair reaching the waist with side-swept bangs, small silver drop earrings, long-sleeved charcoal-black maid dress with white lace cuffs, large soft gray bow, white frilled apron, no headdress, no glasses, dozing with her head resting on her folded arms on the server-room desk, a peaceful sleeping smile, the monitor glowing teal beside her, a clipboard under her arm, in a cozy small server room at night, blinking server rack LEDs, warm amber pendant lamp, detailed anime pixel art illustration, crisp pixels, dithering shading, same art style and lighting as the attached template frame, vertical 9:16, no text
```
움직임: `she sleeps with gentle breathing, then a rack LED turns amber and blinks fast, she jolts awake and sits up straight, static camera, pixel art style preserved`

---

## 5. 모아 — "차와 화분을 챙기는 응원 담당" (SR-M1 ~ SR-M6)

성격: 상냥하고 잘 웃음, 화분과 차 담당, 응원할 때 가장 신남. **흰 프릴 머리띠 필수, 포니테일 금지**(정장일 때만).

```yaml
MOA_EN: "Moa, a gentle cheerful anime girl maid intern, long ash-beige hair reaching the waist with soft wavy ends and neat bangs, white frilled maid headband with a thin white ribbon over the left ear, big round amber-brown eyes, light peach skin with soft blush, white shirt with a red and navy plaid bow tie, camel knit cardigan with ribbed cuffs, white frilled apron with ruffled shoulder straps, black skirt, white socks, brown loafers, no glasses"
```

### SR-M1 · 도입 · 랙 위 작은 화분에 물 주기 (3초) — 첨부 T1
```
Moa, a gentle cheerful anime girl maid intern, long ash-beige hair reaching the waist with soft wavy ends and neat bangs, white frilled maid headband with a thin white ribbon over the left ear, big round amber-brown eyes, light peach skin with soft blush, white shirt with a red and navy plaid bow tie, camel knit cardigan with ribbed cuffs, white frilled apron with ruffled shoulder straps, black skirt, no glasses, standing on tiptoe beside a server rack, watering a small green potted plant on top of the rack with a small tin watering can, a happy caring smile, three-quarter view, medium shot, in a cozy small server room at night, rows of dark server racks with tiny blinking green and amber LED lights, neatly bundled cables, a warm amber pendant lamp, dark wooden floor, detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal monitor glow, same art style and lighting as the attached template frame, vertical 9:16, no text, no letters, no logo, no watermark
```
움직임: `a few drops of water fall into the pot, the plant leaves bounce slightly, she smiles and lowers her heels, server LEDs blink, static camera, pixel art style preserved, character identity unchanged`

### SR-M2 · 주 자세 · 위에서 내려다본 구도, 찻잔 들고 올려다봄 (4초) — 첨부 T2 · **가장 먼저 제작**
```
Moa, a gentle cheerful anime girl maid intern, long ash-beige hair reaching the waist with soft wavy ends and neat bangs, white frilled maid headband with a thin white ribbon over the left ear, big round amber-brown eyes, light peach skin with soft blush, white shirt with a red and navy plaid bow tie, camel knit cardigan with ribbed cuffs, white frilled apron with ruffled shoulder straps, black skirt, white socks, brown loafers, no glasses, sitting on a small round wooden stool next to a server rack, holding a pink teacup with both hands on her lap, looking straight up at the viewer with a bright warm smile, high-angle top-down view, full body, a small potted plant on the floor beside her, in a cozy small server room at night, rows of dark server racks with tiny blinking green and amber LED lights, neatly bundled cables, a warm amber pendant lamp at the top of the frame, dark wooden floor, detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal monitor glow, same art style and lighting as the attached template frame, vertical 9:16, no text, no letters, no logo, no watermark
```
움직임: `gentle breathing, slow happy blink, a thin wisp of steam rises from the teacup, hair ends sway slightly, server LEDs blink, static camera, pixel art style preserved, character identity unchanged`

### SR-M3 · 표정 변화 · 두 주먹 응원 "파이팅" (3초) — 첨부 SR-M2 결과
```
(SR-M2 프롬프트에서 "holding a pink teacup with both hands on her lap, looking straight up at the viewer with a bright warm smile" 를 아래로 교체, 찻잔은 옆 바닥에 내려둠)
both small fists raised in front of her chest in a cheerful fighting pose, eyes closed in a big happy smile, the pink teacup set on the floor beside her
```
움직임: `she pumps both fists up and down twice with an energetic bounce, her headband ribbon flutters, static camera, pixel art style preserved, character identity unchanged`

### SR-M4 · 전환 · 호박색 눈 클로즈업 + 윙크 (1.5초) — 첨부 T4
```
Extreme close-up of one big round amber-brown anime eye, warm sparkle highlights, soft blush on light peach skin, wavy ash-beige hair strands and the edge of a white frilled headband crossing the frame, tiny green and amber server LED lights reflected in the iris, detailed anime pixel art illustration, crisp pixels, dithering shading, same art style as the attached template frame, vertical 9:16, no text
```
움직임: `a quick playful wink, the highlights sparkle, very slight push-in, pixel art style preserved`

### SR-M5 · 마무리 · 두 손 크게 흔들기 (3초) — 첨부 T5 + SR-M2 결과
```
(SR-M2 프롬프트에서 손·표정 부분을 아래로 교체)
waving enthusiastically with both hands raised above her shoulders, mouth open in a big cheerful smile, the pink teacup set on the floor beside her
```
움직임: `she waves both hands energetically three times, then picks up the teacup again and settles back into the starting pose, static camera, pixel art style preserved, character identity unchanged`

### SR-M6 (대체 컷) · 랙 뒤에서 빼꼼 (2초)
①이나 ③을 이 컷으로 바꿔도 됩니다.
```
Moa, a gentle cheerful anime girl maid intern, long ash-beige hair with wavy ends, white frilled maid headband with a thin white ribbon over the left ear, big amber-brown eyes, soft blush, white shirt with a red and navy plaid bow tie, camel knit cardigan, no glasses, peeking out from behind the side of a tall server rack, only her head, shoulders and one hand gripping the rack edge visible, a curious playful smile, in a cozy small server room at night, blinking server rack LEDs, warm amber pendant lamp, detailed anime pixel art illustration, crisp pixels, dithering shading, same art style and lighting as the attached template frame, vertical 9:16, no text
```
움직임: `she slowly leans out from behind the rack, smiles, then ducks back halfway, static camera, pixel art style preserved`

---

## 6. 조수(하루) — 서버실판 다시 찍기 (선택, SR-H1 ~ SR-H3)

기존 템플릿은 연구실 배경입니다. 세 편을 나란히 둘 때 배경이 같아야 하면, 하루도 같은 서버실에서 아래 세 컷만 새로 만들고 나머지(쉿·눈 클로즈업·손 흔들기)는 템플릿 구도를 그대로 따릅니다. 기존 영상을 그대로 쓸 거라면 이 장은 건너뜁니다.

```yaml
HARU_EN: "Haru, a cute anime girl lab assistant, long straight pink hair with navy blue streaks including a thick navy streak down the center of the bangs, two round messy hair buns on top of the head, a small ahoge, big bright blue eyes, light peach skin, wearing a lavender hoodie with white drawstrings over a white t-shirt, under an open white knee-length lab coat, blue jeans, lavender sneakers"
```

### SR-H1 · 주 자세 · 서버실 스툴에 앉아 올려다봄 (4초) — 첨부 T2 · **가장 먼저 제작**
```
Haru, a cute anime girl lab assistant, long straight pink hair with navy blue streaks including a thick navy streak down the center of the bangs, two round messy hair buns on top of the head, a small ahoge, big bright blue eyes, light peach skin, wearing a lavender hoodie with white drawstrings over a white t-shirt, under an open white knee-length lab coat, blue jeans, lavender sneakers, sitting on a small round wooden stool next to a server rack, hands resting on her knees, looking straight up at the viewer with a gentle smile, high-angle top-down view, full body, in a cozy small server room at night, rows of dark server racks with tiny blinking green and amber LED lights, neatly bundled cables, a warm amber pendant lamp at the top of the frame, dark wooden floor, detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal monitor glow, same art style and lighting as the attached template frame, vertical 9:16, no text, no letters, no logo, no watermark
```
움직임: `gentle breathing, slow blink, ahoge bobs slightly, server LEDs blink, static camera, pixel art style preserved, character identity unchanged`

### SR-H2 · 새 자세 · 랙 LED를 손가락으로 짚으며 점검 (3초)
```
(SR-H1 프롬프트에서 앉은 자세 부분을 아래로 교체, 구도는 three-quarter view, medium shot)
standing in front of an open server rack, pointing at a row of LED lights with one finger, the other hand holding a small tablet, a focused confident expression
```
움직임: `her finger moves along the LED row, one LED changes from amber to green, she nods with satisfaction, static camera, pixel art style preserved`

### SR-H3 · 새 자세 · "서버실 이상 무" 경례 (2초)
```
(SR-H1 프롬프트에서 앉은 자세 부분을 아래로 교체, 구도는 front view, medium shot)
standing straight between two server racks, giving a playful salute with her right hand at her brow, a bright confident grin, one eye winking
```
움직임: `she snaps into the salute with a little bounce, her hair buns and lab coat hem bounce, static camera, pixel art style preserved`

---

## 7. 단체 컷 — 서버실 입구 표지 (정지 그림 1장 + 선택 영상)

서버실 입구의 첫 화면·대표 이미지용입니다. 가운데 하루, 왼쪽 시아, 오른쪽 모아.

```
Three anime girls standing side by side in front of a server room door as its guardians, center: Haru, a cute lab assistant with long straight pink hair with navy blue streaks and two round messy hair buns, bright blue eyes, lavender hoodie under an open white lab coat, blue jeans; left: Sia, a calm maid intern with long straight jet-black hair, gray eyes, no headdress, charcoal-black long-sleeved maid dress with a large gray bow and long white frilled apron; right: Moa, a cheerful maid intern with long wavy ash-beige hair, white frilled maid headband with a white ribbon over the left ear, amber-brown eyes, camel cardigan with a red and navy plaid bow tie and white frilled apron; Haru with hands on hips smiling proudly, Sia holding a clipboard with a quiet smile, Moa waving with a teacup in her other hand, full body, slightly low angle, behind them rows of server racks with blinking green and amber LEDs and a warm amber pendant lamp, detailed anime pixel art illustration, crisp pixels, dithering shading, warm amber and deep brown palette with teal glow, vertical 9:16, no text, no letters, no logo, no watermark
```
첨부: 세 캐릭터의 설정 시트 + SR-H1·SR-S2·SR-M2 결과.
움직임(선택): `all three breathe gently and blink at different times, Moa waves twice, server LEDs blink, static camera, pixel art style preserved`

> 미공개 X1~X3는 이 세트에 넣지 않습니다. 넣는다면 문틈의 검은 실루엣 '누군가'로만 씁니다.

---

## 8. 실패 기준 (나오면 다시 생성)

- 시아에게 머리띠·머리 장식이 생김 / 머리색이 검정이 아님
- 모아의 흰 프릴 머리띠가 빠짐 / 포니테일로 묶임 / 체크 리본이 사라짐
- 하루의 머리 번 두 개 또는 앞머리 가운데 남색 줄이 사라짐
- 치비 비율로 그려짐 (템플릿은 등신 비율)
- 컷마다 서버실 배경·조명 색이 크게 달라짐
- 화면에 글자·로고가 나타남, 다른 인물이 끼어듦
- 마지막 컷이 첫 컷 자세로 돌아오지 않음 (루프가 끊겨 보임)
