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

**git init** 명령어는 .git이라는 폴더를 만듦으로써 git 저장소를 생성해주는 역할을 합니다.  
즉, 이제 본격적으로 이 폴더에 git을 이용한 버전 관리 준비가 된 것입니다!

## 2) config

---

내용이 추가될 것입니다..
