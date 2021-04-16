# **Git use**

- 저의 Github repository URL은 [https://github.com/Park-yu-su/Git_use.git](https://github.com/Park-yu-su/Git_use.git) 입니다.

- 위 보고서는 한 프로젝트를 진행하는 상황을 가정해 git의 명령어를 알려주고 있습니다.
---

## **1) init**

---

마크다운 프로젝트를 진행할 폴더를 새로 만들던 도중, Git을 통해 프로젝트를 관리하고 싶어졌습니다! 하지만 지금 상태로는 아무것도 할 수 없습니다. 
여러분은 본격적으로 Git을 사용하기 위해 **해당 폴더를 git이 사용될 수 있는 로컬 저장소로 만들어야 합니다.**  

이를 위해 `git init` 명령어를 사용합니다.

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

즉, `git init` 명령어는 .git이라는 폴더를 만듦으로써 git 저장소를 생성해주는 역할을 합니다.  
이제 본격적으로 이 폴더에 git을 이용한 버전 관리 준비가 된 것입니다!

## **2) config**

---

이제 git 폴더를 만들어 git을 사용할 준비가 되었습니다. 하지만 아직 끝난 것은 아닙니다. **Git을 설치하고 나면 Git의 사용 환경을 사용자에게 맞게 적절하게 설정해 주어야 합니다.**

이를 위해 `git config` 명령어를 사용합니다.

```
git config
```
 
> <결과>
> 
> ![안내](https://user-images.githubusercontent.com/57581969/114034206-f19dff00-98b8-11eb-9fb6-84393a058aec.jpg)
> 
> - `git config`을 입력하면 위처럼 사용법과 함께, 다양한 옵션이 존재하는 것을 볼 수 있습니다.
> 

옵션이 많아서 헷갈릴 수가 있는데, 우리가 눈여겨보아야 할 점은 **사용자 정보를 설정하는 것** 입니다! Git을 설치하고 나서 가장 먼저 해야 하는 것은 사용자이름과 이메일 주소를 설정하는 것입니다. **Git은 커밋할 때마다 이 정보를 사용하기 때문입니다!**

사용자 정보를 설정하기 위해서는 `config --global` 옵션을 사용한 뒤 아래처럼 입력하면 됩니다.

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

이제 로컬 저장소를 만들고 `git config`을 통해 git을 사용할 사용자 설정까지 완료헀습니다!

## **3) remote**

---

여러분은 이제 로컬 저장소를 통해 git을 사용할 준비가 되었습니다! 하지만 아직 중요한 것이 남았습니다. 여러분은 Github 등의 다양한 외부 저장소를 이용해 **자신이 만든 프로젝트를 공유**하고 **다른 사람과 협업**하여 프로젝트를 진행하고 싶을 것입니다. 
즉, 이제 git의 꽃이라고 할 수 있는 **리모트 저장소(외부 저장소)를 등록하여 사용할 차례**입니다!

리모트 저장소를 설정하기 위해서는 `git remote`를 사용합니다.

```
git remote
```

> <결과>
> 
> ![리모트](https://user-images.githubusercontent.com/57581969/114122419-2cd91600-992b-11eb-84f8-c59760fb5bed.jpg)
>

근데 remote를 입력했는데, 아무것도 뜨지 않은 것을 볼 수 있습니다. 
왜냐하면 `git remote`는 **현재 프로젝트에 등록된 리모트 저장소를 보여주기 때문입니다.** 즉, 방금 로컬 저장소를 만들었기 때문에 현재 등록된 리모트 저장소가 없어 아무것도 뜨지 않게 되는 것입니다.

　  
remote 저장소를 추가하기 위해서는 `git remote add` 를 이용합니다.

```
git remote add <단축이름> <url>        <- url은 외부 저장소(github)의 프로젝트를 저장할 url입니다.
```

> <결과>
> 
> ![리모트 추가](https://user-images.githubusercontent.com/57581969/114122708-d3bdb200-992b-11eb-9e02-b9dad3053515.jpg)
> 
> - 위처럼 단축 이름을 origin으로 설정하고, 깃허브의 주소를 연동시키면 `git remote`를 입력했을 때 리모트 저장소가 추가된 것을 볼 수 있습니다.

　  

만약 잘못된 리모트 저장소를 저장했을 땐  
```
git remote remove <지울 리모트 단축 이름>
```
을 입력하면 등록된 리모트 저장소를 지울 수 있습니다.

> <결과>
> 
> ![리모트 제거](https://user-images.githubusercontent.com/57581969/114123049-7fff9880-992c-11eb-928c-8cfed205f146.jpg)
> 

이제 여러분은 `git remote` 명령어를 통해 로컬 저장소 뿐 아니라 리모트 저장소에도 데이터를 주고받을 수 있게 되었습니다!

## **4) add, status**

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

- **스테이징 영역(Staging Area)** 에 대해 간단히 설명드리면, 작업 폴더와 git 폴더 사이를 연결하는 징검다리 역할을 하는 공간입니다. 작업 폴더는 아직 변경 내용을 자유롭게 수정할 수 있지만, 스테이징 영역은 **커밋할 준비가 된 변경 내용이 Git 저장소에 기록되기 전에 대기하는 장소**라고 볼 수 있습니다.  

즉, `git add` 명령어를 사용해 현재 작업 폴더에 있는 변경된 내용을 스테이징 영역으로 올릴 수 있습니다.

```
git add <추가할 파일 이름>
```

> <결과>
> 
> ![캡처22](https://user-images.githubusercontent.com/57581969/114126439-63b32a00-9933-11eb-9147-8d9020b79e3c.jpg)
> 

위처럼 입력하면 작업된 내용이 스테이징 영역(staging area)에 올라갑니다.  

또한, 현재 작업 폴더 상의 모든 변경 내용을 **한 번에 스테이징 영역으로 올리고 싶을 때**는  

```
git add --all
```

을 사용하면 파일 이름을 일일히 입력할 필요 없이 쉽게 올릴 수 있습니다.

　  

하지만 `git add` 명령어만 사용해서는 아무것도 뜨지 않기 때문에 내가 제대로 했는지 확인할 방법이 없습니다.  

이때 같이 사용하는 것이 `git status` 입니다.

```
git status
```

`git status`는 현재 작업 폴더에 존재하는 파일들의 상황을 알려줍니다.  
또한, 현재 **브랜치(branch)** 를 설명해주는 등 현재 작업 폴더 상황이 속한 위치와 진행된 수정 내역 등을 한 눈에 볼 수 있습니다.

### **git status - 초기의 경우**

--- 

> ![아무것도 안한 경우](https://user-images.githubusercontent.com/57581969/114129358-61ec6500-9939-11eb-9550-4d6625e0a99c.jpg)
>

맨 처음의 경우 `git status`를 입력하면 **작업 사항이 없기 때문**에, 작업 폴더가 깨끗하다는 결과가 나옵니다.

 
### **git status - 작업 파일 변경 직후(add 이전)**

---

> ![add전 status](https://user-images.githubusercontent.com/57581969/114129708-18504a00-993a-11eb-936f-eabb6f657f5e.png)
>

위의 예시처럼 **파일을 수정하고 아직 add를 안한 상태**이면, 스태이징 영역에 올라가지 않은 파일이 빨간 글씨로 표현된 모습을 볼 수 있습니다.

### **git status - 작업 파일 add 후**

---

> ![add 후 status](https://user-images.githubusercontent.com/57581969/114129955-8bf25700-993a-11eb-9ace-9cc675dd1616.png)
> 

**git add를 통해 파일을 스태이징 영역에 올린 뒤** `git status`로 상황을 확인하면, 스태이징 영역에 올라간 파일이 초록 글씨로 표현된 모습을 볼 수 있습니다. 

---

즉, 이제 여러분은 수정한 파일을 `git add`와 `git status`를 통해 스태이징 영역에 올리는 과정까지 수행했습니다!

> <진행 상황>
>
> unstage된 파일 -> **Staging Area에 올리기(완료)** -> stage 된 파일을 commit 하여 로컬 저장소에 기록하기 -> 외부 저장소에다가 commit한 것을 push하기


## **5) commit**

---

여기까지 진행했다면 이제 파일은 스태이징 영역에 올라와 있는 상태입니다. 하지만 아직 로컬 저장소에는 이가 반영되지 않았습니다.  
**로컬 저장소에 변경 사항이 반영되어야지 프로젝트 진행상황을 관리할 수 있기 때문에**  이제 여러분은 로컬 저장소에 스태이징 영역에 올라온 변경 사항을 남겨야 합니다.  

여기에 사용되는 것이 `git commit`입니다.  

커밋을 사용할 때에는 `-m 옵션`을 이용하여 **커밋과 동시에 커밋 메시지를 같이 남겨주는 방법**을 추천하고 있습니다.

```
git commit -m "커밋 메시지"
```


한 번 "1st commit"이라는 이름으로 커밋을 만들어 보도록 합시다!
> <결과>
>
> ![커밋 결과](https://user-images.githubusercontent.com/57581969/114133458-0faf4200-9941-11eb-8895-d36c462b7c00.jpg)
>
> - 위는 여태까지 스태이징 된 파일들을 "1st commit"이라는 이름으로 커밋해 로컬 저장소에 반영하는 과정입니다. 

　  
     
이제 commit을 완료한 후에 git status를 통해 커밋 상황을 보면 

![commit 후 status](https://user-images.githubusercontent.com/57581969/114133770-877d6c80-9941-11eb-9d7e-72f5187f18f0.PNG)

커밋을 완료해 작업 폴더가 깨끗하다는 결과를 출력해주는 것을 알 수 있습니다.

즉, `git commit` 명령어를 통해 여러분은 파일의 수정 상황을 로컬 저장소에 반영했습니다. 이제부터 여러분은 **로컬 저장소에 반영된 사항을 통해 프로젝트의 버전 관리를 할 수 있게 되었습니다!**

> <진행 상황>
>
> unstage된 파일 -> Staging Area에 올리기 -> **stage 된 파일을 commit 하여 로컬 저장소에 기록하기(완료)** -> 외부 저장소에다가 commit한 것을 push하기
> 

## **6) push**

---

이제 여러분은 git의 가장 큰 존재 의의라고 할 수 있는 commit을 완료한 상태입니다. 하지만 commit을 통해 로컬 저장소에 변경 기록을 반영했지만, **github 등의 외부 저장소는 이를 알 길이 없습니다.** 다른 사람들에게 코드를 보여주려면 외부 저장소에도 이 반영 결과를 적용해 주어야 하는데, 그럼 어떻게 해야 할까요?  

이 때 사용하는 것이 바로 `git push` 입니다.

```
git push <저장소명> <브랜치명>
```

저장소명은 아까 `git remote`를 통해 설정하였고(여기서는 origin),  브랜치명은 현재 우리가 수정을 진행한 브랜치명(여기서는 master)을 입력하면 됩니다.

　  

한 번 아까 로컬 저장소에 커밋한 "lst commit"을 외부 저장소에 push해 봅시다!
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

## **7) log**

---

이제 여러분은 위에서 배운 것을 응용하여 토대로 몇 번 파일을 수정하여 로컬저장소에 커밋하고, 외부저장소에 푸시하였다고 가정해봅시다. 그런데 커밋을 올리던 도중, **내가 무엇을 수정하여 무슨 이름으로 커밋**을 했는지 **히스토리**를 보고 싶을 때가 있습니다.

이 때, git의 히스토리를 조회하는 명령어인 `git log`가 있습니다.

```
git log
```

> <결과>
> 
> ![로그](https://user-images.githubusercontent.com/57581969/114825062-b17ed500-9e00-11eb-8b76-5048bc42325d.jpg)
> 
> - 위처럼 커밋 히스토리를 통해 처음에 한 1st commit에 이어 2nd commit까지 총 **2개**의 커밋을 진행한 것을 알 수 있습니다.
>

git log는 원하는 커밋의 히스토리에 접근하는 기능을 가진 만큼 다양한 옵션이 존재합니다. 그 중 잘 쓰이는 옵션인 **"각 커밋에서의 변경 사항을 확인"** 에 대해 알아보도록 합시다.    

**각 커밋에서 무엇이 변경되었는지 확인**하는 log의 옵션은 `-p`로 
```
git log -p
```
와 같이 입력하면 됩니다.

> <결과>
> 
> ![로그 dif](https://user-images.githubusercontent.com/57581969/114825667-7c26b700-9e01-11eb-9317-da4e1f450510.jpg)
>
> - 이전과 달리 diff와 함께 Markdown_introduce.md 파일에서 문자가 변경되었다는 점을 알려주고 있습니다.
> 

이제 여러분은 `git log`를 통해 이전에 커밋한 내용을 하나하나 기억할 필요없이 쉽게 조회할 수 있게 되었습니다!  

## **8) reset**

---

지금까지 총 2개의 커밋(1st commit, 2nd commit)을 진행한 것에 이어, 여러분은 계속 파일을 수정해가며 커밋을 진행했다고 가정해봅시다.  
아뿔싸! 그런데, `git log`를 통해 커밋 이력을 보던 중 **중간에 잘못 수정하고 커밋한 것을 알게 되었고, 이전에 수정하여 커밋한 부분으로 돌아가고** 싶어졌습니다.

이럴 때 일일히 코드를 변경하지 않고, 이전의 커밋으로 돌아갈 수 있는 명령어가 있습니다!  
바로 `git reset`입니다.

```
git reset <돌아가고 싶은 커밋>
```

<돌아가고 싶은 커밋> 부분에는 **커밋**을 작성하거나 **HEAD^, HEAD~2** 등 가장 최신 커밋을 기준으로 상대적 경로를 넣어줄 수 있습니다.

```
git reset 8d70e6f801941af4829f2945ae1f8153ec533e3c    <- wrong commit으로 돌아가자(wrong commit 입력)
git reset HEAD^                                       <- 현재 바로 이전 커밋으로 돌아가자
git reset HEAD~2                                      <- 현재에서 2개 전 커밋으로 돌아가자
```

　

reset의 과정은 한 번에 이해하긴 힘드므로 사진과 함께 과정을 살펴봅시다!  

![잘못](https://user-images.githubusercontent.com/57581969/114827517-bf822500-9e03-11eb-9264-6f81005c10e3.jpg)

사진과 같이 현재 총 4개의 커밋이 있고, **wrong commit2**가 최신 커밋인 것을 알 수 있습니다.

　

이를 간단하게 표현하면 아래와 같습니다.
```
                                             HEAD(master)
                                                 |
1st commit <- 2nd commit <- wrong commit <- wrong commit2
```

여기서 `git reset`을 입력하면 입력한 커밋으로 **HEAD를 이동시킵니다.**  
만약 wrong commit으로 이동한다고 가정하면  

```
                             HEAD(master)
                                 |
1st commit <- 2nd commit <- wrong commit     (X) ~~wrong commit2(삭제됨)~~
```
으로 이동한 것을 알 수 있습니다.

　

> <결과>
> 
> ![reset](https://user-images.githubusercontent.com/57581969/114829641-4d5f0f80-9e06-11eb-80fe-534c813feaeb.jpg)
> 
> - HEAD^ (바로 이전 커밋으로 이동)으로 reset한 결과, git log을 통해 wrong commit2의 이전 커밋인 wrong commit으로 이동한 것을 볼 수 있습니다. 
> 

그런데, git reset은 이전 기록들을 이동하는 만큼 매우 민감하기 때문에, 여러 옵션이 존재합니다.  
```
git reset <옵션> <돌아가고 싶은 커밋>
```
총 3가지 옵션인 **--soft, --mixed, --hard**가 존재하는데, 간단히 알아봅시다!

### **8.1) --soft**

---

git reset --soft는 쉽게 설명하면, 돌아가려했던 커밋으로는 돌아가지만, 그 이후 커밋은 지워지지 않습니다.  

만약 `git reset --soft`를 이용해 wrong commit2에서 2nd commit으로 이동한다면
```
            HEAD(master)
                  |
1st commit <- 2nd commit <- wrong commit <- wrong commit2
```
라고 볼 수 있습니다. 


### **8.2) --mixed**

---

만약 아까처럼 `git reset HEAD^`처럼 따로 옵션을 적지 않으면 `git reset`은 mixed 옵션으로 동작하게 됩니다.  
mixed도 실행하면 가리키는 이동하고 싶은 커밋으로 되돌립니다. 즉, commit 명령과 add 명령을 전부 되돌리는 기능입니다.

만약 `git reset --mixed`를 이용해 wrong commit2에서 2nd commit으로 이동한다면
```
            HEAD(master)
                  |
1st commit <- 2nd commit         X ~~wrong commit <- wrong commit2(삭제됨)~~
```
라고 볼 수 있습니다. 

### **8.3) --hard**

---

git reset --hard는 쉽게 설명하면, 돌아간 이력 이후의 모든 커밋 내용을 지워버리고 실제 working directory에 있는 부분까지 지워버리는 역할을 합니다.  

만약 `git reset --hard`를 이용해 wrong commit2에서 2nd commit으로 이동한다면
```
            HEAD(master)
                  |
1st commit <- 2nd commit
```
라고 볼 수 있습니다. 

이 옵션을 사용하면 **워킹 디렉토리의 파일까지 강제로 덮어쓰기 때문에, soft, mixed 옵션과 달리 Git에 저장된 데이터를 실제로 삭제**하므로 사용에 주의를 해야 합니다.

![bandicam 2021-04-08 18-58-50-394](https://user-images.githubusercontent.com/57581969/114830953-c6ab3200-9e07-11eb-82e7-85bc1badd979.jpg)


## **9) branch, checkout**

---

이제 여러분은 어느 정도 Markdwon파일을 수정하여 프로젝트를 진행한 상황입니다. 그런데, 갑자기 text파일을 만들어 진척상황을 따로 적어야 한다는 통보를 받았습니다. 이제 Markdown파일을 수정해야 text파일도 만들어야 합니다. 이에 여러분은 **Mardown파일을 수정하는 부분이랑 text파일만 수정하는 부분을 독립적으로 따로 나누어 진행**하고 싶어졌습니다.  

여기서 사용하는 기능이 바로 **브랜치(branch)** 입니다.

### **브랜치란?**

- 브랜치란 독립적으로 어떤 작업을 진행하기 위한 개념이라고 볼 수 있습니다. 
- 각각의 브랜치는 다른 브랜치의 영향을 받지 않기 때문에, 여러 작업을 동시에 진행할 수 있습니다.
- Git의 특성 상 여러 명이 작업을 하는 경우, 각자의 브랜치를 파서 작업을 진행하면 충돌 없이 프로젝트를 진행할 수 있습니다.

위의 경우를 예로 든다면, 현재까지는 1개의 브랜치에서만 작업을 진행했지만, text파일을 수정하는 기능만 하는 브랜치를 따로 만들어, 총 2개의 브랜치를 이동하며 작업을 한다고 볼 수 있습니다.

```
Markdown 수정 브랜치 ---------------------------------------------      <- 이 브랜치에서는 Markdown만 수정해 커밋
                             |
                             text파일 수정 브랜치 ----------------      <- 이 브랜치에서는 text파일만 수정해 커밋
```

---

먼저 현재 존재하는 브랜치를 확인하기 위해서는  

```
git branch
```
라고 입력합니다.

　  

또한, 브랜치를 새로 만들기 위해서는  

```
git branch <생성할 브랜치 이름>
```
라고 입력합니다.  

> <결과>
> 
> ![브랜치 생성](https://user-images.githubusercontent.com/57581969/114836165-53a4ba00-9e0d-11eb-83e2-9a7bdc110bd8.jpg)
>
> - `git branch plustxt`를 통해 plustxt 브랜치를 생성한 것을 확인할 수 있습니다.
> 
> - `git branch`만 입력하면 현재 존재하는 브랜치를 출력하고, `git branch <생성 브랜치 이름>`을 입력하고 `git branch`를 입력하면 브랜치가 추가된 것을 볼 수 있습니다.
> 

　  

`git branch`는 여러 옵션을 통해, 브랜치를 제거하거나 수정할 수 있습니다.  

`-d`옵션을 이용하면 **브랜치를 제거**할 수 있습니다.  

```
git branch -d <제거할 브랜치 이름>
```

> <결과>
> 
> ![bandicam 2021-04-08 19-07-26-757](https://user-images.githubusercontent.com/57581969/114836612-d0379880-9e0d-11eb-97d8-2a828964ea95.jpg)
> 

`-m`옵션을 이용하면 **브랜치의 이름을 변경**할 수 있습니다.  

```
git branch -m <변경할 브랜치의 기존 이름> <변경할 새 이름> 
```

> <결과>
> 
> ![bandicam 2021-04-08 19-08-09-499](https://user-images.githubusercontent.com/57581969/114836843-04ab5480-9e0e-11eb-96cd-3aae56487638.jpg)
> 
> - plustxt 브랜치가 addtxt 브랜치로 변경된 것을 알 수 있습니다.
>

### **주의할 점**

---

`git branch`를 이용해서 브랜치를 생성할 때에는 생성할 브랜치가 **어느 위치에서 생성**되는지 잘 파악해야 합니다.  
브랜치 생성은 현재 브랜치를 기준으로 트리처럼 가지를 새로 뻗어나가는 구조이기 때문에, **가지가 생겨나는 뿌리 브랜치**를 헷갈려서는 안 됩니다!

```
                              Branch C -------------------    <- 브랜치 A에서 Branch C를 생성한 경우
                              |
Branch A -------------------------------------------------      
               |
               Branch B-----------------------------------    <- 브랜치 A에서 Branch B를 생성한 경우
                              |
                              Branch D -------------------    <- 브랜치 B에서 Branch D를 생성한 경우
```

---

즉, 브랜치는 생성만 중요한 것이 아니라 **올바르게 이동**하는 것 역시 중요합니다.  

**브랜치를 이동**하기 위해서는 `git checkout`을 이용합니다.

```
git checkout <이동할 브랜치 이름>
```

> <결과>
> 
> ![bandicam 2021-04-08 19-08-49-204](https://user-images.githubusercontent.com/57581969/114838051-4a1c5180-9e0f-11eb-9f27-e68102e52e33.jpg)

　  

`git checkout -b`옵션을 이용하면 **브랜치를 생성하고 바로 해당 브랜치로 이동**할 수 있습니다.

```
git checkout -b <생성할 브랜치 이름>
```

> <결과>
> 
> ![bandicam 2021-04-08 19-09-53-012](https://user-images.githubusercontent.com/57581969/114839704-0cb8c380-9e11-11eb-987d-cc3d0655b771.jpg)
>

## **10) pull**

---

이전까지는 로컬 저장소에 변경된 데이터를 `push`를 통해 외부 저장소에 반영하기만 했습니다.  
하지만 반대로 외부 저장소에 변경된 데이터를 로컬 저장소에 반영하면 어떻게 될까요?  

Github의 수정 기능을 이용해, REAMME.md 파일을 수정했다고 가정해봅시다.  

![bandicam 2021-04-08 19-43-52-913](https://user-images.githubusercontent.com/57581969/114849741-03ccef80-9e1b-11eb-91b7-d97e11b1b229.jpg)

이렇게 되면 로컬 저장소에 있는 README.md 파일과 외부 저장소에 있는 README.md 파일의 내용이 다르게 설정된 모습을 볼 수 있습니다.

> <외부 저장소의 README.md>
> 
> ![bandicam 2021-04-08 19-43-52-9132](https://user-images.githubusercontent.com/57581969/114850140-6c1bd100-9e1b-11eb-9574-2718c8971da5.jpg)

> <로컬 저장소의 README.md>
> 
> ![bandicam 2021-04-08 19-44-24-048](https://user-images.githubusercontent.com/57581969/114850178-76d66600-9e1b-11eb-8d00-5d03aa6fc129.jpg)

　  

그럼 이 상황에서 로컬 저장소에 있는 내용을 수정하고, 외부 저장소에 push한다면 어떻게 될까요?  

![bandicam 2021-04-08 19-45-57-061](https://user-images.githubusercontent.com/57581969/114850333-9d949c80-9e1b-11eb-817e-8d811a79a6f7.jpg)

위와 같이 Github에 푸시하는데 실패했다는 메시지가 출력됩니다.

```
로컬 저장소 커밋 : A -> B -> C -> D
                             <충돌>
외부 저장소 커밋 : A -> B -> X -> Y
```

본래 로컬 저장소와 외부 저장소는 push를 통해 같은 커밋을 공유하지만, **같은 브랜치에서 여러 명이 같이 수정을 하는 상황** 이나 **외부 저장소에서 독단적으로 값을 바꾸는 경우** 등에는 서로의 커밋이 충돌하기 때문에 어느 곳을 기준으로 push를 해야 할지 모르고 오류상황이 발생하게 됩니다.

또한, 로컬 저장소에 있는 변경사항이 자동으로 외부 저장소에 자동으로 반영되지 않은 듯이, **외부 저장소에 있는 변경사항은 자동으로 로컬 저장소에 저장되지 않기** 때문에 `push` 등과 비슷한 명령어를 사용해 외부 저장소의 변경 사항을 로컬 저장소에 반영해주어야 합니다.

　  

이때 사용하는 명령어가 `git pull`입니다.

```
git pull <저장소명> <브랜치명>
```

위처럼 명령어는 `git push`와 거의 비슷한 구조입니다. 

> <결과>
> 
> ![bandicam 2021-04-08 19-47-42-097](https://user-images.githubusercontent.com/57581969/114851765-25c77180-9e1d-11eb-9cdc-265ffdd68e4b.jpg)
> 
> 　
> 
> ![bandicam 2021-04-08 19-49-52-279](https://user-images.githubusercontent.com/57581969/114851812-311a9d00-9e1d-11eb-8bdd-e279b77bb90a.jpg)
> 
> - 로컬 저장소의 README.md가 외부 저장소에 있는 README.md의 변경사항과 같아진 것을 볼 수 있습니다.
> 
> ```
> 로컬 저장소 커밋 : A -> B -> X -> Y -> C -> D 
>                              |    |
> 외부 저장소 커밋 : A -> B -> X -> Y
> ```
>

## **11) tag**

---

이제 브랜치도 나누고 커밋도 추가적으로 진행한 상황입니다. 그런데 이전과 달리 커밋의 수가 증가하니 각 커밋이 무슨 수정을 반영했는지 헷갈리기 시작했고, 커밋도 참조하기 힘들어졌습니다.  
이에 **커밋을 참조하기 쉽게 이름을 붙이고** 싶어졌습니다. 

이를 위해 사용되는 것이 바로 **태그(tag)** 입니다.  
태그는 브랜치처럼 위치가 이동하지 않고 **고정되는 이름** 으로, 주로 버전 같은 것을 적을 때 주로 사용됩니다.

　

태그를 만들기 위해서는 `git tag` 명령어가 사용됩니다.

```
git tag <태그 이름>     <- 태그 설정
git tag                 <- 존재하는 태그 출력
```

> <결과>
> 
> ![bandicam 2021-04-08 20-09-43-861](https://user-images.githubusercontent.com/57581969/114856277-e0f20980-9e21-11eb-888b-221ceabd48bc.jpg)
>

위와 같이 **이름 정보만을 갖는 태그를 "Lightweight tag"** 라고 합니다.  
태그는 단순히 이름만이 아니라 **상세한 정보를 추가로 입력**할 수 있는데, 이러한 태그를 **주석 태그(Annotated tag)** 라고 합니다.

　  

주석 태그를 만들기 위해서는 `-a`옵션을 이용합니다.

```
git tag -a <태그 이름> -m "주석 내용"
```

> <결과>
> 
> ![bandicam 2021-04-08 20-12-49-682](https://user-images.githubusercontent.com/57581969/114856860-91f8a400-9e22-11eb-8a94-c862cf290a85.jpg)
> 

　  

tag를 만들었지만, `git tag`명령어로는 태그의 이름밖에 볼 수 없기 때문에, 추가적으로 `git show` 명령어를 통해 태그 정보와 커밋 정보 등을 확인할 수 있습니다.

```
git show
```

> <결과>
> 
> ![bandicam 2021-04-08 20-15-05-975](https://user-images.githubusercontent.com/57581969/114857063-ce2c0480-9e22-11eb-87a0-a76735e94cd2.jpg)
>


## **12) merge**

---

이제 여러분은 브랜치를 나누어 master 브랜치에서는 Markdown 프로젝트를 진행하고, addtxt 브랜치에서는 text.txt파일을 만들어 txt파일을 수정하고 각 브랜치에 커밋을 반영한 상황입니다. 그리고 txt파일 수정이 끝난 지금, 여러분은 **addtxt 브랜치에 있는 txt파일을 master 브랜치에 옮기고 싶다고** 가정해봅시다.  

현재 상황을 보면 master 브랜치에서 addtxt 브랜치를 파생한 후 각자의 브랜치에게 몇 번의 커밋을 진행했습니다.

```
master--------- Markdown 수정 ----- 마크다운 수정2
          |
        addtxt -------- txt파일 수정 ----------------txt파일 수정2

```
즉, 이렇게 **2갈래 나누어진 브랜치를 다시 하나의 갈래로 합쳐야** 할 필요가 있습니다.

　  

이럴 때 사용하는 명령어가 `git merge`입니다.

```
git merge <합칠 브랜치 이름>
```

하지만 위 명령어를 치기 전에 merge가 적용될 브랜치를 잘 확인해야 합니다.  
현재 목표는 **addtxt 브랜치를 master 브랜치와 합치는 것** 이기 때문에, 먼저 결과가 적용될 **master 브랜치로 이동** 하고 `git merge addtxt`를 사용해야 합니다.  

> <결과>
> 
> ![bandicam 2021-04-08 20-41-19-553](https://user-images.githubusercontent.com/57581969/114977062-06365480-9ec2-11eb-892e-52e4de6ac9f5.jpg)
>
> - 브랜치를 옮긴 후, `git merge addtxt`를 실행하면 merge가 완료된 것을 볼 수 있습니다.
> 
> ![bandicam 2021-04-08 20-47-10-816](https://user-images.githubusercontent.com/57581969/114977239-501f3a80-9ec2-11eb-8d49-f8bc2a633744.jpg)
>
> - 그 후 master 브랜치에서 text.txt파일이 생성된 것을 볼 수 있고, master 브랜치에서 커밋이 정상적으로 진행되는 것을 볼 수 있습니다. 
> 

```
<결과>

master--------- Markdown 수정 ----- Markdown 수정2 ------------------------- Commit
          |                                                |
        addtxt -------- txt파일 수정 ----------------txt파일 수정2
```

## **13) rebase**

---

이제 merge를 통해 txt파일을 master 브랜치에 옮긴 후, 여러분은 Markdown을 열심히 수정해 프로젝트를 거의 다 끝낸 상황입니다.  
그런데 markdown 파일을 급하게 수정해야 하는 상황이 벌어졌고, 이에 여러분은 새로운 브랜치인 Fixmark 브랜치를 파서 markdown 파일을 수정하기 시작했다고 가정해봅시다. 

![bandicam 2021-04-08 20-57-15-663](https://user-images.githubusercontent.com/57581969/114978453-2cf58a80-9ec4-11eb-9dbb-f411ea4ac5ee.jpg)

 - Fixmark 브랜치를 생성하여 Markdown 파일 수정 진행

　  

그리고 master 브랜치에서는 보고서를 작성하기 위해 READMD.md 파일을 수정하기 시작했습니다. 

![bandicam 2021-04-08 21-31-01-501](https://user-images.githubusercontent.com/57581969/114978645-7219bc80-9ec4-11eb-9846-5d4a1f01197f.jpg)

 - master 브랜치로 돌아와서 README.md 파일 수정 진행

그 후, markdown 수정이 최종적으로 끝나서 이제 **Fixmark 브랜치에 있는 markdown 최종 수정본을 보고서를 작성중인 master 브랜치와 합치고 싶어졌습니다.**

```
<현 브랜치 상황>

master--------- 보고서 작성중1 ----- 보고서 작성중2 --------
          |                                                
        Fixmark ---- Markdown 1차 수정 ---- Markdown 1차 수정 ---- Markdown 최종 수정
```

물론 여러분은 이전에 배운 `merge`를 이용해 브랜치를 합칠 수 있겠지만, 이번에는 다른 방법을 사용해 볼 것입니다.

　  

바로 `git rebase` 명령어입니다.

```
git rebase <합칠 브랜치 이름>
```

`git rebase`는 `git merge`하고 비슷한 결과를 보여줍니다. `git rabase`를 사용하면 **한 브랜치에서 변경된 사항을 다른 브랜치에 적용할 수 있습니다.**  

과정을 설명하면 아래와 같습니다.

1. 두 브랜치(master, Fixmark)가 나뉘기 전인 **공통 커밋으로 이동** 한다. 
2. 그 커밋부터 새 브랜치가 가리키는 커밋까지의 변경 사항을 임시로 저장한다.
3. **Rebase 할 브랜치(Fixmark)가 합칠 브랜치(master)를 가리키게 하고,** 아까 저장해 놓았던 변경사항을 차례대로 적용한다.

　  

> <결과>
> 
> ![bandicam 2021-04-08 21-48-24-605](https://user-images.githubusercontent.com/57581969/114979451-d7ba7880-9ec5-11eb-9305-cc054e96c363.jpg)

그 후,  `git merge`를 통해 Fixmark 브랜치의 변경사항을 master에 적용하면 rebase가 완료됩니다.

> <결과>
> 
> ![bandicam 2021-04-08 21-49-06-744](https://user-images.githubusercontent.com/57581969/114979619-2ff17a80-9ec6-11eb-94ab-ab0263e06781.jpg)

　

```
<결과>

master--------- 보고서 작성중1 ---- 보고서 작성중2 ---- [Markdown 1차 수정 ---- Markdown 1차 수정 ---- Markdown 최종 수정]
          |                                                
        Fixmark ---- [Markdown 1차 수정 ---- Markdown 1차 수정 ---- Markdown 최종 수정] <- 여기까지를 복사해 master에 적용한다.
```

## **14) clone**

---

이제 여러분은 merge와 rebase를 적절히 활용해 Markdown 파일과 txt파일의 최종 수정을 끝내, master 브랜치에 옮기고 외부 저장소(Github)에다가 최종 커밋을 push한 상태입니다.  

한 상황을 가정해봅시다. 여러분은 잠시 밖에 나왔습니다. 그런데 급하게 프로젝트에서 수정해야 할 부분이 뒤늦게 생각났습니다. 불행하게도 프로젝트가 담긴 노트북을 집에 두고 왔서, 일단 PC방에 들어갔습니다만, Github에 있는 내용을 일일히 복사해 다시 작성하자니 시간도 오래 걸리고 난처한 상황입니다.

이런 상황 등을 대비해 Git에서는 **외부 저장소(Github)에 있는 프로젝트를 다른 컴퓨터에 복사할 수 있는 기능** 이 존재하는데, 바로 `git clone` 명령어입니다.

```
git clone <복사할 github 레퍼지토리 주소>
```

git clone을 사용하는 방법은 아래와 같습니다.

1. 먼저 clone이 적용될 폴더를 생성한다.
2. cmd 등의 명령 프롬프트를 열어 clone이 적용될 파일이 존재하는 디렉토리로 이동한다.
3. `git clone <복사할 레퍼지토리 주소>`를 입력한다.

> <결과>
> 
> ![bandicam 2021-04-08 22-10-44-703](https://user-images.githubusercontent.com/57581969/114984349-9a0d1e00-9ecc-11eb-820d-fe6587d7ddf4.jpg)
> 
> - 새로운 컴퓨터 환경에서 cmd창을 열어 `git clone`을 실행한 결과입니다.
> 
> ![bandicam 2021-04-08 22-11-12-892](https://user-images.githubusercontent.com/57581969/114984461-b7da8300-9ecc-11eb-8dd2-bb150e312036.jpg)
>
> ![bandicam 2021-04-08 22-11-20-445](https://user-images.githubusercontent.com/57581969/114984557-d50f5180-9ecc-11eb-889c-866b6fdcc2f8.jpg)
>
> 
> - 해당 파일에 들어가보면 Git_use파일이 생성된 것을 볼 수 있고, 프로젝트에 사용된 파일들이 존재하는 것을 볼 수 있습니다.
> 
> ![bandicam 2021-04-08 22-12-29-349](https://user-images.githubusercontent.com/57581969/114984650-ea847b80-9ecc-11eb-97d2-fa590f253a17.jpg)
> 
> ![bandicam 2021-04-08 22-12-29-349](https://user-images.githubusercontent.com/57581969/114985032-4e0ea900-9ecd-11eb-8853-853492827dc1.jpg)
>
> - 또한, 파일 역시 외부 저장소에 있는 내용과 같은 것을 볼 수 있습니다.
> 

　  

또한, 단순히 `git clone`은 파일 내용만 복사하는 것이 아니라, 해당 프로젝트의 커밋 기록 역시 복사되기 때문에 `git log`명령어를 통해 커밋 기록을 조회할 수 있습니다.

![클론 결과](https://user-images.githubusercontent.com/57581969/114985341-a9409b80-9ecd-11eb-9a75-f7d414581a86.PNG)

---

### **이상으로 Github 명령어 학습하기를 마치도록 하겠습니다, 감사합니다.** 

---

## **부록**

보고서에서 사용된 명령어랑, 사용 여부, 해당 명령어 설명 링크를 나타낸 표입니다.  
해당 링크를 클릭할 시, 해당 목차 첫 페이지로 이동합니다.  

| **사용 명령어** | **사용 여부** | **해당 명령어 설명 링크** |
| :-: | :-: | :-: |
| add | [O] | [git add](#4-add-status) |
| branch | [O] | [git branch](#9-branch-checkout) |
| checkout | [O] | [git checkout](#9-branch-checkout) |
| clone | [O] | [git clone](#14-clone) |
| commit | [O] | [git commit](#5-commit) |
| config | [O] | [git config](#2-config) |
| init | [O] | [git init](#1-init) |
| log | [O] | [git log](#7-log) |
| merge | [O] | [git merge](#12-merge) |
| pull | [O] | [git pull](#10-pull) |
| push | [O] | [git push](#6-push) |
| rebase | [O] | [git rebase](#13-rebase) |
| remote | [O] | [git remote](#3-remote) |
| reset(reset --hard) | [O] | [git reset](#8-reset), [git reset --hard](#83---hard)  |
| status | [O] | [git status](#4-add-status) |
| tag | [O] | [git tag](#11-tag) |
