# 💰 나의 가계부 (Household Ledger)

Supabase를 백엔드 DB로 사용하는 단순하고 가벼운 가계부 웹 앱입니다.
빌드 과정 없이 `index.html` 하나만 열면 바로 동작합니다.

## 기능
- 📅 월별 수입 / 지출 / 잔액 요약 (월 이동)
- ✍️ 수입·지출 입력 (카테고리, 금액, 메모, 날짜)
- 📋 내역 목록 조회 및 삭제
- ☁️ 모든 데이터는 Supabase(PostgreSQL)에 실시간 저장

## 기술 스택
- 프론트엔드: 순수 HTML / CSS / JavaScript (단일 파일)
- 백엔드/DB: [Supabase](https://supabase.com) (PostgreSQL + RLS)
- Supabase JS Client (CDN)

## 사용법
1. `index.html` 을 브라우저로 엽니다.
2. 금액과 카테고리를 입력하고 **추가하기** 를 누릅니다.
3. 데이터는 Supabase DB에 저장되어 어느 기기에서 열어도 동일하게 보입니다.

## DB 스키마
- `transactions` — 거래 내역 (type, amount, category, memo, occurred_on)
- `categories` — 카테고리 (name, type, emoji, sort_order)

## 보안 참고
`index.html` 에 포함된 키는 Supabase **publishable(공개용) 키** 로, 클라이언트 노출을 전제로 한 키이므로 공개 저장소에 있어도 안전합니다.
현재는 개인용 도구를 가정해 RLS 정책을 열어둔 상태이므로, 다중 사용자 또는 외부 공개 운영 시에는 Supabase Auth(로그인) 도입을 권장합니다.
