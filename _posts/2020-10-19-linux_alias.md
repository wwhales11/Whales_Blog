---
title :  "리눅스 alias 설정방법"
categories : linux
   
---
<br/>
<br/>
<br/>
# alias 기본	

명령어를 길게 입력하기 싫거나 매크로 돌리듯이 단축 키 기능을 하는게 바로 alias 명령이다.	


$ alias   -->   alias 명령 올 출력	
$ alias c='clear'   -->   'c'를 clear으로 수행하게 해준다. 	
추가로 이렇게 커맨드 창에만 입력하면 캐시처럼 화면을 끄면 사라진다. 	
영구 저장을 위해 홈디렉토리로 가서 (cd ..) 	

```	
$ vim .bashrc	
```	

이렇게 수정하고 	

```	
$ . .bashrc	
```	

이걸로 배시파일 저장해 주면 환경설정으로 적용된다. 	


# 포스팅 alias	

블로그 포스팅할 때 불편한 점이 모든 포스트를 직접 .md파일로 만들어서 Front Matter라고 제목이랑 카테고리 같은 설정을 넣고 	
_posts폴더에 넣어야지 겨우 작동한다는 점이였다. 	

이에 대한 해결책으로 _draft폴더에 2020-01-01.md파일을 미리 만들어 놓고 복사해서 수정하면 좋지 않을까 생각했다.	


***
<br/>
<br/>
# <구현> 	
<br/>

```	
$ alias bmo='cp ~/github/whales/_draft/draft.md ~/github/whales/_posts/; cd ~/github/whales/_posts; vim draft.md;'	
```
<br/>

이렇게 alias를 만들어 놓으면 'bmo'라는 명령어로 복사(cp)해서 _posts 파일에 넣고 whales로 이동 해서  vim을 이용하여  draft를 수정작성하면 된다.  	
<br/>

물론 저장할 때	
<br/>

```	
:w 2020-10-19-얖.md 	
```	
<br/>

이런식으로 저장해야 된다. 다 같은 드래프트 파일이면 곤란하니까.	

<br/>

아직 파일 저장할 때 지킬 테마들의 특유의 "yyyy-mm-dd-제목.md" 형식을 어떻게 제목만으로 저장할 수 있는지 알고 싶다. 	
<br/>
기본 룰이라 안되려나	

***
<br/>
#git push alias	
<br/>

alias로 또 좋은 단축키로 만든게 git push까지 명령어를 압축해서 쓰는거다.	

<br/>
```	
alias gg='git add .; git commit -m '\''UP'\''; git push;'	
```	
<br/>

이런 식으로 add, commit, push 까지 일련의 과정들을 alias 환경변수로 만들어서 쓰면 편하다.	

<br/>
만약 push명령에서 아이디랑 비밀번호 치는게 귀찮으면 	
```	
git config --global credential.helper store	
```	
<br/>

이걸로 아이디랑 비번 캐시해두면 여러 입력들이 생략된다.	
<br/>
<br/>  
<br/>  
<br/>  
**오늘의 교훈 : github.io 블로깅은 쓸데없이 복잡하고 귀찮다. 커스터마이징은 가능해도 지킬테마가 너무 난해하다. **	
<br/>
<br/>

블로그에 포스트 하나 올리기 하드코어하다. 
