# **QuickSight 신규 User 생성 방법 & Sharing Asset** 



1. **QuickSight Default Region으로 이동합니다.(대부분은 Seoul을 선택하시면 됩니다.)**

**![image-20241012132806165](images/image-20241012132806165.png)**



----

2. **Manage QuickSight를 클릭합니다.**

**![image-20241012132925287](images/image-20241012132925287.png)**



---

3. **Inviate Users** Click

![image-20241012133035964](images/image-20241012133035964.png)



---

4. 초대하려는 email을 입력 후 **+ 를 클릭** 합니다.

![image-20241012133122492](images/image-20241012133122492.png)



---

5. 필요한 **Role**을 선택 후 **Inviate**를 Click합니다. 우선 **ADMIN** 권한을 주겠습니다.

![image-20241012134353305](images/image-20241012134353305.png)



---

6. **Inviate Email**이 아래처럼 옵니다.

![image-20241012133405042](images/image-20241012133405042.png)



---

7. email을 열고 **Click to accept Invitation**을 Click합니다.

![image-20241012133434270](images/image-20241012133434270.png)



---

8. **Password 설정 창**에서 Password를 입력 하고 **Set new password**를 클릭합니다.

![image-20241012133610415](images/image-20241012133610415.png)



---

9. Password를 설정하면 Login 창이 뜹니다. QuickSight Account Name을 10번 스텝에서 확인 후 입력합니다.

![image-20241012133708238](images/image-20241012133708238.png)



---

10. 화면 맨 우측 상단에 **Profile**버튼을 클릭하면, Account name이 보입니다. 아래의 예에서는 **kiwony101**입니다.

![image-20241012133756029](images/image-20241012133756029.png)



----

11. 9번의 QuickSight Login 창에서 **QuickSight account name**부분에 10번에서 확인한 Account Name을 입력 후 NEXT를 클릭합니다.

![image-20241012133902341](images/image-20241012133902341.png)



---

12. **Sign in to kiwony101**이라고 화면이 바뀌고, 아래 Username에 아까 초대했던 email주소와 비밀번호를 입력합니다.

![image-20241012134016978](images/image-20241012134016978.png)

![image-20241012134105804](images/image-20241012134105804.png)





---

13. Login 후에 확인해보면 기존에 만든 DataSet이나 Analsis등이 안 보이는 것을 확인 할 수 있습니다. 새로 생성된 User에게 기존의 DataSet이나 Analysis에 대한 권한을 주지 않았기 때문입니다. 기존에 작업하던 계정으로 가서 권한을 부여합니다.

![image-20241012134640810](images/image-20241012134640810.png)



---

14. 우선 DataSet 권한을 주겠습니다. 기존 QuickSight 계정으로 로그인 후 신규 User johnyoon0701@gmail.com에게 권한을 주겠습니다.

    아래의 예에서는 lge-vs-chip DataSet을 클릭합니다.

![image-20241012135002287](images/image-20241012135002287.png)



---

15. **Permissions** 클릭 후 **ADD USERS & GROUPS**를 클릭합니다.

![image-20241012135103723](images/image-20241012135103723.png)



---

16. 권한을 부여할 QuickSight User를 검색 후 **ADD**를 클릭합니다.

![image-20241012135203151](images/image-20241012135203151.png)



---

17. User에게 줄 Permissions을 선택합니다. Owner 또는 Reader를 줄 수 있습니다. 아래의 예에서는 Owner로 주겠습니다.

![image-20241012135254467](images/image-20241012135254467.png)



---

18. 신규 유저 johnyoon0701@gmail.com로 로그인한 QuickSight 화면에서 새로 고침을 하면 아까 보이지 않던 **lge-vs-chip** DataSet이 보이는 것을 확인 할 수 있습니다.

![image-20241012135429171](images/image-20241012135429171.png)



---

19. 이번엔 기존에 만들어둔 분석 Analysis 화면에 대한 권한을 신규 유저 **johnyoon0701@gmail.com**에게 주겠습니다.

    기존 User의 QuickSight 화면에서 **Shared Folders**로 이동 후 **New Folder**를 클릭하고, Folder이름을 입력후 **Create**를 클릭합니다.

    **Shared Folders** 아래에 신규 Folder가 생성됩니다.

![image-20241012135959074](images/image-20241012135959074.png)



![image-20241012140014788](images/image-20241012140014788.png)



![image-20241012140051064](images/image-20241012140051064.png)



---

20. 생성한 Folder에 다른 User가 접근 할 수 있도록 허용하겠습니다. **점 3개를 클릭** 후 **Share**를 클릭합니다.

![image-20241012140208727](images/image-20241012140208727.png)



---

21. 접근 권한을 줄 User를 검색 후 잠시 기다리면 아래처럼 List Up이 됩니다. 해당 User를 클릭하면 아래 화면처럼 보이게 됩니다.

    추가된 User에게 권한을 부여합니다. 우리는 **Owner** 권한을 주겠습니다. **Owner** 선택 후 **Share**를 클릭합니다.

![image-20241012140256604](images/image-20241012140256604.png)



![image-20241012140340812](images/image-20241012140340812.png)



---

22. 이제 **LGE-VS-CHIP**이란 Folder에 추가되는 QuickSight Asset들은  johnyoon0701@gmail.com이 Owner로서 접근 할 수 있습니다.

![image-20241012140612792](images/image-20241012140612792.png)



---

23. 기존에 만들어둔 Analysis를 공유하기 위해서 Analysis 화면으로 이동 후, 공유하기 원하는 분석 Asset의 메뉴 버튼 클릭 후 **Add to folder**를 클릭 합니다.

![image-20241012140730976](images/image-20241012140730976.png)



---

24. 선택창이 보이면 **Shared folders**에 방금 만든 **LGE-VS-CHIP**을 선택 후 **ADD**를 클릭합니다.

    정말 Share할 것인지 묻는 화면에서 **Add and share**를 클릭합니다.

![image-20241012140833583](images/image-20241012140833583.png)

![image-20241012140913826](images/image-20241012140913826.png)



![image-20241012140948392](images/image-20241012140948392.png)



---

25. 신규 user **johnyoon0701@gmail.com** QuickSight 화면에서 새로 고침을 하면 기존에 보이지 않던 분석 Asset이 보입니다.

![image-20241012141033209](images/image-20241012141033209.png)



---

26. 실제 분석 Asset을 클릭하면, 신규 유저에서 아래처럼 정상적으로 해당 Asset을 사용하는 것을 확인 할 수 있습니다.

![image-20241012141133307](images/image-20241012141133307.png)



























