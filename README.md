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

이제 git 폴더를 만들어 git을 사용할 준비가 되었습니다. 하지만 아직 끝난 것은 아닙니다! **Git을 설치하고 나면 Git의 사용 환경을 사용자에게 맞게 적절하게 설정해 주어야 합니다!**

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

사용자 정보를 설정하기 위해서는 **config --global** 옵션을 사용한 뒤 아래처럼 입력하면 됩니다!

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
을 입력하면 됩니다!

> <결과>
> 
> ![bandicam 2021-04-08 18-08-04-391-2](https://user-images.githubusercontent.com/57581969/114121524-758fcf80-9929-11eb-9086-b7f9874def0c.jpg)
> 

이제 로컬 저장소를 만들고 **git config**을 통해 git을 사용할 사용자 설정까지 완료헀습니다!

## 3) remote

---

여러분은 이제 로컬 저장소를 통해 git을 사용할 준비가 되었습니다! 하지만 아직 끝나지는 않았습니다. 여러분은 Github 등의 다양한 외부 저장소를 이용해 **자신이 만든 프로젝트를 공유**하고 **다른 사람과 협업**하고 싶을 것입니다. 
즉, 이제 git의 꽃이라고 할 수 있는 **리모트 저장소(외부 저장소)를 사용할 차례**입니다!

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
it remote add <단축이름> <url>        <- url은 외부 저장소(github)의 프로젝트를 저장할 url입니다.
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

## 4) add

---

