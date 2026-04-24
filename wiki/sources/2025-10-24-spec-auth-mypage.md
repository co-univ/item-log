---
title: "로그인 / 회원가입 / 마이페이지 명세서 (Confluence)"
type: source
status: stable
sources: [raw/2025-10-24-spec-auth-mypage.md]
updated: 2026-04-24
source_url: https://youthing.atlassian.net/wiki/spaces/~712020e8812b2eb985491caedb51d1b356e362/pages/29818898
author: 전민재
source_date: 2025-10-24
---

# 로그인 / 회원가입 / 마이페이지

mait 사용자 계정 라이프사이클의 진입·관리 기능. 소셜(구글/카카오/네이버) + 로컬(이메일+비밀번호) 두 경로 지원.

## 핵심 요약

- **로그인**: 소셜 3종(구글/카카오/네이버) + 로컬(이메일/비밀번호). 소셜 실패는 표준 에러 토스트.
- **회원가입(소셜)**: 최초 진입 시 "계정 설정하기" 모달 — 약관 동의 + 닉네임만 입력하면 시작 가능.
- **회원가입(로컬)**: 이메일 인증(10분 유효) + 비밀번호 정책(8자+영문+숫자+특수문자) + 이름 + 전화번호(중복불가) + 닉네임 + 약관 동의.
- **마이페이지**: 이메일·이름은 수정 불가. 전화번호·닉네임·비밀번호는 수정 가능.
- **닉네임 정책**: 자동 랜덤 제안(`user1234`), 2~20자, 금지어 필터링, 중복 불가.

## 영향받는 wiki 페이지

- [features/auth-and-account.md](../features/auth-and-account.md) — 신규
- [decisions/account-policies.md](../decisions/account-policies.md) — 신규 (비밀번호 / 닉네임 / 전화번호 정책 모음)
- [glossary/core-terms.md](../glossary/core-terms.md) — 닉네임, 약관 등 추가

## 미해결

- "로그인 유지" 옵션의 토큰 정책 (만료 기간, refresh 정책 등) 미정
- 금지어(비속어, 운영자 등) 리스트 출처/관리 주체 미정
- 소셜 로그인 신규 가입과 기존 이메일 가입 계정의 연동(merge) 정책 미정
- 마이페이지에서 전화번호/닉네임/비밀번호 외 다른 항목(예: 프로필 사진)에 대한 명세 없음
