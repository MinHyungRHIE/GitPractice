# Git 명령어 익히기
<img width="400" height="200" src="https://miro.medium.com/max/875/1*BCZkmZR1_YzDZy22Vn4uUw.png" alt="Gitimg" title="GIT을 익혀보자">
<hr>

![Prunus](http://www.gstatic.com/webp/gallery/4.jpg)

### Git 저장소 영역
| <영역> | 이름 | 설명 |
|:---:|:---:|:---:|
| `<USER>` | Working Directory | .git이 있는 실제 파일들이 있는 작업공간  |
| `<INDEX>` | staging Area | 준비 영역 |
| `<HEAD>` | Local Repository | 최종 확정본 |
| `<GITHUB>` | Remote Repository | Github.com |

<hr>

### Git의 대략적인 흐름
| 영역   | init | add | commit | push | pull | clone | merge | fetch |
|:---:   |:---: |:---:|:---:   |:---: |:---: |:---:  |:---:  |:---:  |
| User   |  `O` |  v  |        |      |  `O` |  `O`  |  `O`  |       |
| INDEX  |      | `O` |    v   |      |   ^  |   ^   |   ^   |       |
| HEAD   |      |     |   `O`  |   v  |   ^  |   ^   |   ^   |  `O`  |
| GITHUB |      |     |        |  `O` |   ^  |   ^   |       |   ^   |

<hr>

### 로컬 --> Github
| 단    계 | 명령어 | 저  장  소 | 설명 |
|:---:|:---:|:---:|:---:|
| `1` | git init | USER | .git파일을 만듭니다. |
| `2-1` | git config --global user.name "닉네임" | USER | 닉네임을 설정합니다. |
| `2-2` | git config --global user.email "이메일" | USER | 이메일을 설정합니다. |
| 삭제 | rm -r .git | USER | .git파일을 삭제합니다. |
| `3` | git remote add origin "주소" | INDEX | Remote Repository을 설정합니다. |
| 삭제 | git remote rm origin | INDEX | 설정된 Remote Repository를 삭제합니다.(주로 오타를 입력해서 다시 시도시 이용) |
| 확인 | git status | INDEX | staging Area에 준비중인 파일/폴더 상태를 보여줍니다. R(unadded), G(added) |
| `4` | git add 파일/폴더 | INDEX-->HEAD | 준비중인 파일/폴더를 확정시킵니다. |
| 취소 | git reset HEAD파일/폴더 | HEAD-->INDEX | ROLLBACK! |
| `5` | git commit -m "확정본에 대한 설명" | HEAD | 해당 작업에 대한 commit을 생성합니다. |
| `6` | git push -u origin master | HEAD-->GITHUB | github.com에 이동! |
