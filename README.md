# DiscordStickerJson
디스코드 공개 스티커 Json 데이터 입니다.

디스코드 api v9에서 작동하는 공개 스티커 데이터 입니다.

정확하지는 않지만 제가 확인한 결과로는 디스코드 스티커는 공개 스티커팩와 비공개 스티커팩으로 나누어집니다.

## 스티커팩 데이터 구조
```json
{"sticker_packs": [{"id": "스티커팩 id", "name": "스티커팩 이름", "sku_id": "아이템 id", "cover_sticker_id": "미리보기 스티커 id", "description": "스티커 설명", "banner_asset_id": "스티커 미리보기 배경 id", "sticker": ["스티커 데이터들..."]}]}
```

## 스티커 데이터 구조
```json
{"id": "스티커 id", "name": "스티커 이름", "tags": "스티커 태그들", "type": "스티커 타입", "format_type": "스티커 이미지 타입", "description": "스티커 설명", "asset": "", "pack_id": "스티커팩 id", "sort_value": ""}
``` 

## 라우터

**DM에서 손 흔들기 (봇 사용 불가, 유저 토큰 인증 필요)**

POST ``https://discord.com/api/v9/channels/{유저 id}/greet``

```json
{"sticker_ids":["스티커id"]}
```

**비공개, 공개 스티커팩 정보 가져오기 (봇 사용 불가, 유저 토큰 인증 필요)**

GET ``https://discord.com/api/v9/sticker-packs/{스티커팩 id}``

**비공개, 공개 스티커 정보 가져오기 (인증 불필요)**

GET ``https://discord.com/stickers/{스티커 id}.json``


**공개 스티커팩 리스트 가져오기 (인증 불필요)**
GET ``https://discord.com/api/v9/sticker-packs/``

