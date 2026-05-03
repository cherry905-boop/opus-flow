# Opus Flow Piano + Fitness Redesign Prompt

이 저장소는 Opus Flow라는 단일 HTML 파일 React 앱이다.
파일은 `index.html` 하나가 핵심이다.

기존 작곡 중심 앱을 폐기하고, 새 방향으로 다시 설계한다.

## 새 방향

Opus Flow는 작곡 아카이브 앱이 아니라 피아노 연습 + 운동 루틴 + 수행 기록 앱이다.
작곡과 사진 아카이브는 별도 공개 사이트에서 다룬다.
현재 앱에서는 작곡 탭을 제거하거나 숨긴다.
기존 작곡 localStorage 키는 삭제하지 않고 보존한다.

## 작업 목표

- 기존 데이터 구조 중 백업/복원, localStorage 기반 저장 방식은 유지
- UI는 Notion 톤으로 새로 설계
- 모바일/PWA 우선
- 데스크톱에서는 사이드바 + 넓은 관리 화면
- 단일 `index.html` 유지
- React 18 + Babel standalone CDN 유지
- 외부 빌드 도구 추가 금지
- `main` 브랜치 push 금지
- `feature/piano-fitness-redesign` 브랜치에만 커밋

## 새 탭

1. 오늘
2. 피아노
3. 운동
4. 기록
5. 설정

## 오늘

- 오늘 날짜
- 오늘 피아노/운동 루틴
- 빠른 시작
- 오늘 완료한 세션
- 마지막 활동

## 피아노

- 이번 달 집중 항목
- 곡 라이브러리
- 테크닉 라이브러리
- 연습 세션 기록
- 곡: `title`, `composer`, `opus`, `currentSection`, `status`, `notes`
- 테크닉: `title`, `category`, `targetBPM`, `currentBPM`, `status`, `notes`
- 피아노 세션: `date`, `type(piece/technique)`, `targetId`, `duration`, `section`, `bpm`, `repetitions`, `note`, `feeling`

## 운동

- 오늘 운동
- 운동 루틴
- 운동 항목 라이브러리
- 운동 세션 기록
- 운동 항목: `name`, `category`, `unit`, `notes`, `status`
- 운동 세션: `date`, `exerciseId`, `sets`, `reps`, `weight`, `duration`, `distance`, `note`, `feeling`

## 기록

- 캘린더
- 이번 주 피아노 총 시간
- 이번 주 운동 횟수
- 연속 수행일
- 주간 리뷰
- 지난 리뷰

## 설정

- 피아노 라이브러리 관리
- 운동 항목 관리
- 루틴 관리
- 목표 설정
- 백업/복원
- 데이터 요약

## localStorage

기존 키는 삭제하지 말 것:

- `of3-works`
- `of3-sessions`
- `of3-reviews`
- `of3-cats`
- `of3-routine`
- `of3-goals`
- `of3-horizons`
- `of3-timer`

새 키 추가:

- `of3-piano-pieces`
- `of3-piano-techniques`
- `of3-piano-sessions`
- `of3-exercises`
- `of3-exercise-sessions`
- `of3-settings`

## 백업/복원

- 새 키 포함
- 기존 백업도 불러올 수 있게 호환
- `schemaVersion` 올리기

## 디자인

Notion 톤.
흰 배경, 따뜻한 회색 텍스트, 얇은 보더, 작은 pill, hairline row.
모바일은 하단 탭.
데스크톱은 좌측 사이드바.
모바일은 빠른 기록 중심.
데스크톱은 관리/통계 중심.

## 작업 완료 후

- `git diff` 확인
- 동작 검증 방법 작성
- 브랜치에 커밋
- `main` push 금지
