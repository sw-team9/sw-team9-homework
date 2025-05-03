# Team9 Git 협업 가이드

우리는 각 팀원이 개별 브랜치에서 작업한 후 Pull Request를 통해 `main` 브랜치에 병합하는 방식으로 협업합니다.  
Git 및 GitHub에 익숙하지 않은 팀원을 위해 전체 작업 절차를 정리해볼게요!
---

## 1. 브랜치 생성 및 이동

작업을 시작할 때는 반드시 본인 전용 브랜치를 만들어 작업합니다.

```bash
git checkout -b 브랜치이름
```

예시:
```bash
git checkout -b yurim
```

---

## 2. 커밋 메시지 규칙

다음 형식을 따라 커밋 메시지를 작성합니다.

```
[숙제이름-담당번호] 작업 내용
```

- `숙제이름`: requirement-descriptions, requirement-list 등
- `담당번호`: 본인이 맡은 항목 번호

예시:
- `[requirement-descriptions-1] 식당 추천 디스크립션 내용 추가`
- `[requirement-list-2] 식당 리스트 내용 추가`

---

## 3. 커밋 및 푸시

작업한 파일을 저장소에 반영합니다.

```bash
git add .
git commit -m "[숙제이름-담당번호] 작업 내용"
git push origin 브랜치이름
```

예시:
```bash
git add .
git commit -m "[requirement-list-1] 식당 추천 리스트 작성"
git push origin yurim
```

---

## 4. GitHub에서 Pull Request 보내기

1. GitHub 저장소에 접속
2. `main ← 본인 브랜치` 기준으로 Pull Request 생성
3. 제목과 설명에는 작업 내용을 정확하게 작성
4. 팀원에게 리뷰 요청

---

## 5. 리뷰 및 머지 기준

- Pull Request는 **1명 이상의 승인(Approve)** 을 받아야 병합할 수 있습니다.
- 충돌(conflict)이 발생하면 직접 해결한 뒤 다시 푸시해야 합니다.
- 리뷰어가 변경 요청(Request changes)을 남기면 반영 후 다시 푸시합니다.

---

## 6. 충돌 해결 시

1. `main` 브랜치와의 충돌이 발생한 경우 다음 명령어로 병합을 시도합니다.

```bash
git pull origin main --rebase
```

2. 충돌이 발생한 파일을 열어 `<<<<<<<`, `=======`, `>>>>>>>` 표시를 수정합니다.
3. 수정 완료 후 아래 명령어를 입력합니다.

```bash
git add .
git rebase --continue
```

4. 이후 푸시합니다.

```bash
git push -f origin 브랜치이름
```

---

## 7. 브랜치 전략

- `main`: 최종 병합용 브랜치 (직접 작업 절대 금지)
- `개인 브랜치`: 각자 작업용 브랜치, 예: `yurim`
