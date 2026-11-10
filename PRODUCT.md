# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

- **북구 주민**: look up what has been asked about issues in their own 동, check the answers, send 제보 for new questions, and send replies they received themselves so they can be added as records.
- **SNS 유입 (YouTube·Facebook)**: arrive on phones from 박재진's YouTube and Facebook links, usually landing on one record or the map.
- **행정기관·의원**: check what was asked, what the agency answered, and how the follow-up is going.

## Product Purpose

울산 북구 residents, including 박재진, ask administrative agencies about local issues through 국민신문고, 정보공개청구 and 면담. 박재진 collects those questions and the answers received and publishes them as records. The site is the public record of what 북구 residents have asked: where each issue is on the map, who asked, which agency answered, what it said, and what comes next. Success means anyone can check, from a phone, what was asked and what came back, without having to take anyone's word for it.

## Positioning

The site is a record of questions and answers, not a list of accomplishments. Each record keeps who asked, the question, the agency's reply as received, 박재진's own assessment, and his relationship to the case in separate fields, with the original reply documents attached where available. A campaign page or news summary can't copy that structure honestly.

## Operating Context

- Channels: 국민신문고, 정보공개청구 (with receipt numbers), 면담.
- Record lifecycle (`STATUS`): 질의 중 → 답변 받음 / 정보 없음 회신 / 이의신청 / 답 없음 → 해결.
- Who asked (`asker`): empty means 박재진. Resident records use "주민", or the resident's name only with their consent. Resident records are published only with the resident's consent and after the original reply has been checked; 박재진 organizes and publishes them. Residents who have a problem but no reply yet are handled by 박재진 asking the agency himself.
- Records are placed by coordinates, and the 행정동 is detected automatically from the 북구 boundary data (vuski/admdongkor). Issues that cover all of 북구, or have no fixed location, are listed outside the map.
- Categories (`CATEGORY`): 교통·주차, 교육·보육, 주거·생활, 상권·경제, 산업·노동, 환경·공원, 안전, 행정·예산.
- 박재진 maintains the site by editing the data block in `index.html` (`SITE`, `RECORDS`), either himself or by having Claude edit and push to GitHub directly. Opening the page with `?coords` lets him pick coordinates by clicking the map. Updates are published with `git push` to GitHub Pages; pull before editing the local clone.
- 제보 goes to email (and phone, once filled in). The 제보 box asks residents to attach the original reply (screenshot) when they have one. YouTube and Facebook are linked from the header.

## Capabilities and Constraints

- Static site on **GitHub Pages**. No server and no build step today; CDN dependencies are Leaflet 1.9.4 and Pretendard.
- **Mobile first**: most visitors arrive on phones from social links.
- **Mind the election law (공직선거법)**: 박재진 is a party member and may run for office in about four years. Copy must contain no promotional or campaign language: no promises, no 업적 framing, no calls to support him. Write in a neutral, fact-first record tone.
- Agency replies and 박재진's assessment always stay in separate fields (`answer` and `opinion`) and are never blended in copy or layout.
- Personal details of the requester and agency staff are masked in attached original documents.
- An unknown value is shown as "입력 전" and never filled with a guess.
- `index-old.html` is an earlier alternate version (formerly `index .html`); whether to keep it is undecided.

## Brand Commitments

- Site name: 「울산 북구 주민이 물어 본 기록」. 박재진 is shown as the one who organizes the records (기록 정리: 박재진).
- Voice: first person (제가, 저와의 관계), plain and factual, the language of a record rather than an advocate.
- Published rules, shown on the site, that future work must keep:
  - 기록마다 누가 물었는지 밝힙니다. 제가 요청자·당사자인 사안도 항목마다 밝힙니다.
  - 주민이 물은 기록은 본인 동의를 받고, 회신 원문을 확인한 것만 올립니다.
  - 기관이 회신한 내용과 제 평가는 칸을 나눠 적습니다.
  - 회신 원문은 신청인과 담당자의 개인정보를 가리고 첨부합니다.

## Evidence on Hand

- Six real records in `index.html` `RECORDS`, all asked by 박재진: 오토밸리로 중산·매곡 방면 진출로, 디아채 대각선 횡단보도 점멸신호, 이화중 한시 통학버스, 울산외고 전환 근거, 농수산물도매시장 이전, 공동주택 특수계량기 교체비. No resident records yet.
- Not yet available: scanned reply documents (`docs: []`), site photos (`photos: []`), 박재진's assessments (`opinion: ""`), a phone number. Do not fabricate testimonials, outcomes, endorsements, counts or quotes from agencies.

## Product Principles

1. **The record speaks before the person.** What was asked and what the agency answered come first; 박재진's assessment is labeled and comes second.
2. **Neutral by default.** Every line should survive election-law scrutiny and read the same to supporters and critics.
3. **Show the gaps.** 입력 전, 답 없음 and 정보 없음 회신 stay visible as facts, not hidden as failures.
4. **Easy for one person to maintain.** Updating the site should stay as simple as editing data, without tooling.
5. **Phone first.** A visitor arriving from a social link should understand one record within seconds.

## Accessibility & Inclusion

Korean-language audience covering all ages of 북구 residents, including older readers, so keep text legible on small screens and controls easy to tap. Target **WCAG 2.1 AA**: text contrast at least 4.5:1 (3:1 for large text), and heading levels must not skip.
