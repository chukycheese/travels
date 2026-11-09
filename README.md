# Travels · 교영 & 주영의 여행 노트

여행 계획과 실전 가이드를 모아 두는 정적 사이트입니다. Cloudflare Workers(Assets)로 배포합니다.

- 사이트: <https://travels.inkstone.workers.dev/>
- 오로라 가이드: <https://travels.inkstone.workers.dev/aurora/>

## 구조

```
public/
  index.html          여행 노트 허브
  aurora/index.html   핀란드 오로라 & 에스토니아 탈린 가이드
wrangler.jsonc        Cloudflare Workers 설정
```

## 로컬 실행

```bash
npm install
npm run dev
```

## 배포

```bash
npm run deploy
```

`main` 브랜치에 푸시하면 GitHub Actions가 자동 배포합니다. 저장소 시크릿에
`CLOUDFLARE_API_TOKEN`, `CLOUDFLARE_ACCOUNT_ID`가 필요하며, 없으면 배포 단계를 건너뜁니다.

## 새 여행 추가

1. `public/<slug>/index.html`에 가이드 페이지를 만듭니다.
2. `public/index.html`의 `trips` 목록에 카드를 추가하고 `href="/<slug>/"`로 연결합니다.
