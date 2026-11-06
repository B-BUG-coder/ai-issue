# Step 2: 사용한 명령어

아래는 `ai-issue` GitHub 저장소를 만들고 이슈를 생성한 뒤, README를 원격 저장소에 올릴 때 사용한 명령어입니다.

## GitHub 로그인 확인

```powershell
gh auth status
```

## 공개 GitHub 저장소 생성

```powershell
gh repo create B-BUG-coder/ai-issue --public
```

## 로컬 폴더에 Git 저장소 초기화 및 원격 연결

```powershell
git -C C:\workspace\ai-issue init --initial-branch=main
git -C C:\workspace\ai-issue remote add origin https://github.com/B-BUG-coder/ai-issue.git
git -C C:\workspace\ai-issue remote -v
```

## `배포됨` 이슈 생성

```powershell
gh api --method POST repos/B-BUG-coder/ai-issue/issues --field title='배포됨' --jq .html_url
```

## README 커밋 및 푸시

```powershell
git -C C:\workspace\ai-issue add README.md
git -C C:\workspace\ai-issue commit -m "Add README"
git -C C:\workspace\ai-issue push -u origin main
```
