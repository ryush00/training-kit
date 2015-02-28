---
layout: cheat-sheet
title: GitHub Git 치트시트
byline: Git는 Github 활동을 랩톱이나 데스크톱에서 용이하게 할 수 있도록 해주는 오픈소스 분산 버전 관리 시스템입니다. 이 치트 시트는 일반적으로 사용되는 Git 명령어에 관한 설명을 빠르게 참고할 수 있도록 요약되어 있습니다.
leadingpath: ../
---

{% capture colOne %}
## Git 설치
GitHub는 자주 쓰이는 작업을 GUI로 할수 있도록 제공하고 고급 시나리오를 위한 자동으로 업데이트되는 명령줄을 포함하는 데스크톱 클라이언트를 제공합니다.

### GitHub for Windows
http://windows.github.com

### GitHub for Mac
http://mac.github.com

Linux 또는 POSIX 시스템을 위한 Git 배포판은 공식 Git SCM 웹사이트에서 구할 수 있습니다.

### Git 모든 플랫폼 버전
http://git-scm.com

## 도구 설정
모든 로컬 저장소의 사용자 정보 설정 방법

```$ git config --global user.name "[name]"```

커밋시 붙는 이름을 설정합니다


```$ git config --global user.email "[email address]"```

커밋시 붙는 이메일을 설정합니다


## 저장소 생성
저장소를 새로 만들거나 기존의 URL으로부터 가져옵니다


```$ git init [project-name]```

지정한 이름의 로컬 저장소를 만듭니다


```$ git clone [url]```

프로젝트와 모든 버전 기록을 다운받습니다


{% endcapture %}
<div class="col-md-6">
{{ colOne | markdownify }}
</div>


{% capture colTwo %}

## 변경하기
변경 사항을 검토하고 커밋을 합니다.


```$ git status```

커밋될 새롭거나 수정된 파일의 목록을 보여줍니다


```$ git diff```

스테이지되지않은 파일의 차이를 표시합니다


```$ git add [file]```

버전 관리를 위한 스냅샷 파일을 만듭니다


```$ git diff --staged```

Shows file differences between staging and the last file version


```$ git reset [file]```

Unstages the file, but preserves its contents


```$ git commit -m"[descriptive message]"```

Records file snapshots permanently in version history

## Group changes
Name a series of commits and combine completed efforts


```$ git branch```

Lists all local branches in the current repository


```$ git branch [branch-name]```

Creates a new branch


```$ git checkout [branch-name]```

Switches to the specified branch and updates working directory


```$ git merge [branch-name]```

Combines the specified branch’s history into the current branch


```$ git branch -d [branch-name]```

Deletes the specified branch
{% endcapture %}
<div class="col-md-6">
{{ colTwo | markdownify }}
</div>
<div class="clearfix"></div>

---

{% capture colThree %}
## Refactor file names
Relocate and remove versioned files


```$ git rm [file]```

Deletes the file from the working directory and stages the deletion


```$ git rm --cached [file]```

Removes the file from version control but preserves the file locally


```$ git mv [file-original] [file-renamed]```

Changes the file name and prepare it for commit

## Suppress tracking
Exclude temporary files and paths

```
*.log
build/
temp-*
```

A text file named `.gitignore` suppresses accidental versioning of files and paths matching the specified patterns


```$ git ls-files --other --ignored --exclude-standard```

Lists all ignored files in this project

## Save fragments
Shelve and restore incomplete changes


```$ git stash```

Temporarily stores all modified tracked files


```$ git stash pop```

Restores the most recently stashed files


```$ git stash list```

Lists all stashed changesets


```$ git stash drop```

Discards the most recently stashed changeset
{% endcapture %}
<div class="col-md-6">
{{ colThree | markdownify }}
</div>

{% capture colFour %}
## Review history
Browse and inspect the evolution of project files


```$ git log```

Lists version history for the current branch


```$ git log --follow [file]```

Lists version history for the file, including renames


```$ git diff [first-branch]...[second-branch]```

Shows content differences between two branches


```$ git show [commit]```

Outputs metadata and content changes of the specified commit

## Redo commits
Erase mistakes and craft replacement history


```$ git reset [commit]```

Undoes all commits after `[commit]`, preserving changes locally


```$ git reset --hard [commit]```

Discards all history and changes back to the specified commit

## Synchronize changes
Register a remote (URL) and exchange repository history


```$ git fetch [remote]```

Downloads all history from the remote repository


```$ git merge [remote]/[branch]```

Combines the remote branch into the current local branch


```$ git push [remote] [branch]```

Uploads all local branch commits to GitHub


```$ git pull```

Downloads bookmark history and incorporates changes
{% endcapture %}
<div class="col-md-6">
{{ colFour | markdownify }}
</div>
