# Git workshop2

สร้าง Repository บน github
![](../assets/images/github-createrepo.png)

กรอกข้อมูล
![](../assets/images/github-newrepo.png)

ยังไม่ต้อง  `Add a README file` option จะทำให้ ได้ Reposity ที่ว่างๆ ต่อมา github จะแสดงค่า ค่า setup เพื่อให้เราไปสร้าง git remote ในเครื่อง logo

![](../assets/images/github-add-remote-repo.png)

สำหรับ สร้าง repo ใหม่
```
echo "# git_lab1" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/opendevbook/git_lab1.git
git push -u origin main
```

หามี Repository อยู่ แล้วก็ให้ใช้คำสั่งต่อไปนี้

```
git remote add origin https://github.com/opendevbook/git_lab1.git
git branch -M main
git push -u origin main
```
- **git remote add origin <url>** add remote repository
- **git branch -M main**  เปลี่ยนชือ branch ปัจจุบัน เป็น `main` โดย `-M` flag จะเป็นการ fore ให้เปลี่ยนชื่อ
- **git push -u origin main** ทำการ push local repository ไปยัง remote repository ใน branch ชื่อเดียวกัน กับ local และ `-u` flag ทำหน้า บอกกับ git ว่า `origin` repository จะทำหน้าที่เป็น upstream  

่ก่อนการ Apply คำสั่ง
![](../assets/images/github-before.png)

หลังการสั่งคำสั่ง

![](../assets/images/github-after.png)

คำว่า upstream repository (origin/main) หมายถึง repository ทำหน้าเก็บ Code ที่เป็น code หลัก และทำหน้าที่ sync กับ code ใน local git

## Git Fork model

ทดลองการ Fork repository python

Fork https://github.com/python/cpython repository
![](../assets/images/github-fork-python.png)
กดปุ่ม Fork 

![](../assets/images/github-fork-create.png)

กด `create fork`

![](../assets/images/github-fork-process.png)

## copy repo และ clone มายัง local repo

ให้เรา copy 
![](../assets/images/github-fork-success.png)

```
$ git clone https://github.com/opendevbook/cpython.git
$ cd cpython
$ git branch -r
```
> เปลี่ยน owner ให้เป็นของเรา

![](../assets/images/github-clone-fork.png)


### เพิ่ม upstream repository

```
$ git remote -v
origin  https://github.com/opendevbook/cpython.git (fetch)
origin  https://github.com/opendevbook/cpython.git (push)

$ git branch -v

$ git remote add upstream https://github.com/python/cpython
```

- เพิ่มที่เก็บโค้ดต้นฉบับ (upstream) เป็น remote ในที่เก็บโค้ดของคุณ

![](../assets/images/github-add-upstream.png)

### git fetch upstream
```
$ git fetch upstram
```
![](../assets/images/github-fetch-upstream.png)

#### merge upstram เข้ากับ main ของ local
```
$ git merge upstream/main
```
- ผสานการเปลี่ยนแปลงจากสาขา main ของ upstream เข้ากับสาขาในเครื่องของคุณ

#### ดู commit log ของสาขา upstream
```
$ git log upstram/main
```

![](../assets/images/github-log-upstream.png)