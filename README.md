# **Git use**

- 저의 Github repository URL은 [https://github.com/Park-yu-su/Git_use.git](https://github.com/Park-yu-su/Git_use.git) 입니다.

- 위 보고서는 한 프로젝트를 진행하는 상황을 가정해 git의 명령어를 알려주고 있습니다.
---

## 1) init

---

마크다운 프로젝트를 진행할 폴더를 새로 만들던 도중, Git을 통해 프로젝트를 관리하고 싶어졌습니다! 하지만 지금 상태로는 아무것도 할 수 없습니다. 
여러분은 본격적으로 Git을 사용하기 위해 **해당 폴더를 git이 사용될 수 있는 로컬 저장소로 만들어야 합니다.**  

이를 위해 **git init** 명령어를 사용합니다.

```
git init
```

> <결과>
>
>![git init](https://user-images.githubusercontent.com/57581969/114034203-f1056880-98b8-11eb-83d6-7555744bf4db.jpg)


위처럼 입력하면 숨김파일로 .git이라는 폴더가 생성되는데 여기에 들어가면 git 저장소에 필요한 여러 파일들이 생성되어 있는 것을 볼 수 있습니다.

> <.git 파일 내부>
>
> ![.git 폴더](https://user-images.githubusercontent.com/57581969/114034204-f19dff00-98b8-11eb-9b66-660ebd077323.jpg)
>
> - 각 브랜치의 정보를 담은 branch 폴더부터 시작해 HEAD 등 git에서 사용되는 여러 파일이 담겨 있습니다.

즉, **git init** 명령어는 .git이라는 폴더를 만듦으로써 git 저장소를 생성해주는 역할을 합니다.  
이제 본격적으로 이 폴더에 git을 이용한 버전 관리 준비가 된 것입니다!

## 2) config

---

이제 git 폴더를 만들어 git을 사용할 준비가 되었습니다. 하지만 아직 끝난 것은 아닙니다. **Git을 설치하고 나면 Git의 사용 환경을 사용자에게 맞게 적절하게 설정해 주어야 합니다.**

이를 위해 **git config** 명령어를 사용합니다.

```
git config
```
 
> <결과>
> 
> ![안내](https://user-images.githubusercontent.com/57581969/114034206-f19dff00-98b8-11eb-9fb6-84393a058aec.jpg)
> 
> - git config을 입력하면 위처럼 사용법과 함께, 다양한 옵션이 존재하는 것을 볼 수 있습니다.
> 

옵션이 많아서 헷갈릴 수가 있는데, 우리가 눈여겨보아야 할 점은 **사용자 정보를 설정하는 것** 입니다! Git을 설치하고 나서 가장 먼저 해야 하는 것은 사용자이름과 이메일 주소를 설정하는 것입니다. **Git은 커밋할 때마다 이 정보를 사용하기 때문입니다!**

사용자 정보를 설정하기 위해서는 **config --global** 옵션을 사용한 뒤 아래처럼 입력하면 됩니다.

```
git config --global user.name <사용자이름>  
git config --global user.email <사용할 E-mail>  
```

> <결과>
> 
> ![입력](https://user-images.githubusercontent.com/57581969/114121520-745ea280-9929-11eb-8bfa-f46e919c8166.jpg)
>
> - 위처럼 창이 뜨면 올바르게 사용자 정보가 설정된 것입니다.
> 

사용자가 설정된 것을 보고 싶으면  
```
git config --global user.name
git config --global user.email
```
을 입력하면 됩니다.

> <결과>
> 
> ![bandicam 2021-04-08 18-08-04-391-2](https://user-images.githubusercontent.com/57581969/114121524-758fcf80-9929-11eb-9086-b7f9874def0c.jpg)
> 

이제 로컬 저장소를 만들고 **git config**을 통해 git을 사용할 사용자 설정까지 완료헀습니다!

## 3) remote

---

여러분은 이제 로컬 저장소를 통해 git을 사용할 준비가 되었습니다! 하지만 아직 중요한 것이 남았습니다. 여러분은 Github 등의 다양한 외부 저장소를 이용해 **자신이 만든 프로젝트를 공유**하고 **다른 사람과 협업**하여 프로젝트를 진행하고 싶을 것입니다. 
즉, 이제 git의 꽃이라고 할 수 있는 **리모트 저장소(외부 저장소)를 등록하여 사용할 차례**입니다!

리모트 저장소를 설정하기 위해서는 **git remote** 사용합니다.

```
git remote
```

> <결과>
> 
> ![리모트](https://user-images.githubusercontent.com/57581969/114122419-2cd91600-992b-11eb-84f8-c59760fb5bed.jpg)
>

근데 remote를 입력했는데, 아무것도 뜨지 않았습니다. 
왜냐면 git remote는 **현재 프로젝트에 등록된 리모트 저장소를 보여주기 때문입니다.** 방금 로컬 저장소를 만들었기 때문에, 현재 등록된 리모트 저장소가 없기 때문에 아무것도 뜨지 않게 되는 것입니다.

　  
remote 저장소를 추가하기 위해서는 **git remote add** 를 이용합니다.

```
git remote add <단축이름> <url>        <- url은 외부 저장소(github)의 프로젝트를 저장할 url입니다.
```

> <결과>
> 
> ![리모트 추가](https://user-images.githubusercontent.com/57581969/114122708-d3bdb200-992b-11eb-9e02-b9dad3053515.jpg)
> 
> 위처럼 단축 이름을 origin으로 설정하고, 깃허브의 주소를 연동시키면 **git remote**를 입력했을 때 리모트 저장소가 추가된 것을 볼 수 있습니다.

만약 잘못된 리모트 저장소를 저장했을 땐  
```
git remote remove <지울 리모트 단축 이름>
```
을 입력하면 등록된 리모트 저장소를 지울 수 있습니다.

> <결과>
> 
> ![리모트 제거](https://user-images.githubusercontent.com/57581969/114123049-7fff9880-992c-11eb-928c-8cfed205f146.jpg)
> 

이제 여러분은 **git remote** 명령어를 통해 로컬 저장소 뿐 아니라 리모트 저장소에도 데이터를 주고받을 수 있게 되었습니다!

## 4) add, status

---

이제 프로젝트를 진행할 폴더를 만들어서 사용자 설정도 하고 리모트 저장소에 연결까지 완료했습니다. 모든 기본 준비를 마친 여러분은 이제 파일을 만들고 어느 정도 프로젝트를 진행했다고 가정해봅시다.

![캡처2](https://user-images.githubusercontent.com/57581969/114125484-8ba18e00-9931-11eb-9992-7c419c1bd52a.PNG)

현재 작업 폴더에 'Markdown_introduce.md' 라는 파일이 추가된 상황입니다.  
git은 파일을 추가하거나 생성한다고 해서 **바로 변경 사항이 적용되지 않습니다.** 그러므로 우리는 일련의 과정을 거쳐 이를 로컬저장소 또는 외부 저장소에 저장해야 합니다.

미리 간단히 일련의 과정을 설명하면  
```
unstage된 파일 -> Staging Area에 올리기 -> stage 된 파일을 commit 하여 로컬 저장소에 기록하기 -> 외부 저장소에다가 commit한 것을 push하기
```
이렇게 되어 있습니다. (자세한 내용은 뒤에서 설명하겠습니다.)  

![stage 관계](https://user-images.githubusercontent.com/57581969/114127003-7aa64c00-9934-11eb-8e1c-7c9293bae0a7.png)

- 스테이징 영역(Staging Area)에 대해 간단히 설명드리면, 작업 폴더와 git 폴더 사이를 연결하는 징검다리 역할을 하는 공간입니다. 작업 폴더는 아직 변경 내용을 자유롭게 수정할 수 있지만, 스테이징 영역은 커밋할 준비가 된 변경 내용이 Git 저장소에 기록되기 전에 대기하는 장소라고 볼 수 있습니다.  

즉, **git add** 명령어를 사용해 현재 작업 폴더에 있는 변경된 내용을 스테이징 영역으로 올릴 수 있습니다.

```
git add <추가할 파일 이름>
```

> <결과>
> 
> ![캡처22](https://user-images.githubusercontent.com/57581969/114126439-63b32a00-9933-11eb-9147-8d9020b79e3c.jpg)
> 

위처럼 입력하면 작업된 내용이 스테이징 영역(staging area)에 올라갑니다.  

또한, 현재 작업 폴더 상의 모든 변경 내용을 한 번에 스테이징 영역으로 올리고 싶을 때는  

```
git add --all
```

을 사용하면 파일 이름을 일일히 입력할 필요 없이 쉽게 올릴 수 있습니다.

　  

하지만 **git add**만 사용해서는 아무것도 뜨지 않기 때문에 내가 제대로 했는지 확인할 방법이 없습니다.  
이때 같이 사용하는 것이 **git status** 입니다.

```
git status
```

git status는 현재 작업 폴더에 존재하는 파일들의 상황을 알려줍니다.  
또한, 현재 **브랜치(branch)** 를 설명해주는 등 **git status** 는 현재 작업 폴더 상황이 속한 위치와 진행된 수정 내역 등을 설명해줍니다. 

### git status - 초기의 경우

--- 

> ![아무것도 안한 경우](https://user-images.githubusercontent.com/57581969/114129358-61ec6500-9939-11eb-9550-4d6625e0a99c.jpg)
>

맨 처음의 경우 git status를 입력하면 작업 사항이 없기 때문에, 작업 폴더가 깨끗하다는 결과가 나옵니다.

 
### git status - 작업 파일 변경 직후(add 이전)

---

> ![add전 status](https://user-images.githubusercontent.com/57581969/114129708-18504a00-993a-11eb-936f-eabb6f657f5e.png)
>

위의 예시처럼 파일을 수정하고 아직 add를 안한 상태이면, 스태이징 영역에 올라가지 않은 파일이 빨간 글씨로 표현된 모습을 볼 수 있습니다.

### git status - 작업 파일 add 후

---

> ![add 후 status](https://user-images.githubusercontent.com/57581969/114129955-8bf25700-993a-11eb-9ace-9cc675dd1616.png)
> 

add 명령어를 실행한 후 git status로 파일 상황을 확인하면, 스태이징 영역에 올라간 파일이 초록 글씨로 표현된 모습을 볼 수 있습니다. 

---

즉, 이제 여러분은 수정한 파일을 **git add**와 **git status**를 통해 스태이징 영역에 올리는 과정까지 수행했습니다!

> <진행 상황>
>
> unstage된 파일 -> **Staging Area에 올리기(완료)** -> stage 된 파일을 commit 하여 로컬 저장소에 기록하기 -> 외부 저장소에다가 commit한 것을 push하기


## 5) git commit

---

여기까지 진행했다면 이제 파일은 스태이징 영역에 올라와 있는 상태입니다. 하지만 아직 로컬 저장소에는 이가 반영되지 않았습니다.  
**로컬 저장소에 변경 사항이 반영되어야지 프로젝트 진행상황을 관리할 수 있기 때문에**  이제 여러분은 로컬 저장소에 스태이징 영역에 올라온 변경 사항을 남겨야 합니다.  

여기에 사용되는 것이 **git commit**입니다.  
커밋을 사용할 때에는 -m 옵션을 이용하여 **커밋과 동시에 커밋 메시지를 같이 남겨주는 방법**을 추천하고 있습니다.

```
git commit -m "커밋 메시지"
```

> <결과>
>
> ![커밋 결과](https://user-images.githubusercontent.com/57581969/114133458-0faf4200-9941-11eb-8895-d36c462b7c00.jpg)
>
> - 위는 여태까지 스태이징 된 파일들을 "1st commit"이라는 이름으로 커밋해 로컬 저장소에 반영하는 과정입니다. 

　  

commit을 완료한 후에 git status를 통해 커밋 상황을 보면 

![commit 후 status](https://user-images.githubusercontent.com/57581969/114133770-877d6c80-9941-11eb-9d7e-72f5187f18f0.PNG)

커밋을 완료해 작업 폴더가 깨끗하다는 결과를 출력해주는 것을 알 수 있습니다.

즉, **git commit**을 통해 여러분은 파일의 수정 상황을 로컬 저장소에 반영했습니다. 이제부터 여러분은 **로컬 저장소에 반영된 사항을 통해 프로젝트의 버전관리를 할 수 있게 되었습니다!**

> <진행 상황>
>
> unstage된 파일 -> Staging Area에 올리기 -> **stage 된 파일을 commit 하여 로컬 저장소에 기록하기(완료)** -> 외부 저장소에다가 commit한 것을 push하기
> 

## 6) push

이제 여러분은 git의 가장 큰 존재 의의라고 할 수 있는 commit을 완료한 상태입니다. 하지만 commit을 통해 로컬 저장소에 변경 기록을 반영했지만, **github 등의 외부 저장소는 이를 알 길이 없습니다.** 다른 사람들에게 코드를 보여주려면 외부 저장소에도 이 반영 결과를 적용해 주어야 하는데, 그럼 어떻게 해야 할까요?  

이 때 사용하는 것이 바로 **git push**입니다.

```
git push <저장소명> <브랜치명>
```

저장소명은 아까 **git remote**를 통해 설정하였고(여기서는 origin),  브랜치명은 현재 우리가 수정을 진행한 브랜치명(여기서는 master)을 입력하면 됩니다.

> <결과>
> 
> ![bandicam 2021-04-08 18-26-25-454](https://user-images.githubusercontent.com/57581969/114134777-3bcbc280-9943-11eb-87cf-9865dd2c30bb.jpg)
>
> - push를 하면 github의 유저 이름과 비밀번호를 입력받는데, 이를 입력하면 자동으로 github에 push가 됩니다.
> 
> 　
> ![bandicam 2021-04-08 18-27-58-376](https://user-images.githubusercontent.com/57581969/114135200-dfb56e00-9943-11eb-8139-a14dc2908c79.jpg)
>
> - 그리고 설정해놓은 github 홈페이지로 들어가면 위와 같이 커밋한 결과가 반영되는 모습을 볼 수 있습니다.

　  

**축하합니다!** 여러분은 이제 git에서 가장 중요한 작업인 **프로젝트 수정, 수정사항 커밋, 커밋한 상황 로컬 저장소에 올리기** 의 일련의 과정을 수행할 수 있게 되었습니다. 앞으로 프로젝트를 진행하면서 발생하는 수정사항들은 전부 아래의 과정을 거쳐 로컬/외부 저장소에 저장됩니다.
```
unstage된 파일 -> Staging Area에 올리기 -> stage 된 파일을 commit 하여 로컬 저장소에 기록하기 -> 외부 저장소에다가 commit한 것을 push하기
                   git add <파일명>                  git commit -m <커밋 이름>                      git push <저장소명> <브랜치명>
```

## 7) 
