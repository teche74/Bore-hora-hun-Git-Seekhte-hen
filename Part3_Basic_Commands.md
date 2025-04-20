
# 🧰 Git Ki Pehli Mulakaat – First Time Setup

> Tumne ab tak jaan liya ki **Git kyun important hai** is yug ke developers ke liye.  
> Ab chalo – thoda hands-on ho jaaye? 💻

---

## 👋 Sabse Pehle – Pehli Mulakaat Ke Rasme

> Jab dosti nayi ho, toh thoda introduction zaruri hota hai 😄  
> Git bhi wahi chahta hai – **tumhara naam aur email**!

---

### 🙋‍♂️ Naam Aur Email Batana

Jab bhi tum koi **commit** karte ho, Git kehta hai:  
_"Bhai tu kaun hai?"_  

Aur uska jawab dena hota hai:

```
git config --global user.name "Tumhara Naam"
git config --global user.email "tumhara@email.com"
```

> ⚠️ `--global` ka matlab: **ye setting har repository pe apply hogi**  
> Agar kisi specific repo ke liye alag naam/email chahiye, toh `--global` mat lagao.

---

### 📝 Apna Editor Set Karna

Git tumse kuch cheezein likhwaata hai — jaise commit messages.  
Uske liye tumhara **favourite editor** chahiye hoga:

```
git config --global core.editor "tumhara-editor"
```

> Jaise: `notepad`, `vim`, `code`, etc.  
> Tumhara editor = tumhari writing style 😉

---

### 🌿 Default Branch Ka Naam Badalna

By default, Git tumhari first branch ka naam `main` rakhta hai.  
Lekin agar tum chaaho toh isse **kuch bhi** bana sakte ho:

```
git config --global init.defaultBranch "tumhara-branch-naam"
```

> Default naam tumhari marzi ka — Git hai flexible 😎

---

## 🆘 Git Se Help Lena

> Git ke commands yaad na rahein? Koi baat nahi — Git khud help karega!

Bas likho:

```
git help <command>
```

Ya:

```
git <command> --help
```

> Example: `git config --help` se tumhe pura guide mil jaayega.  
> Git = tumhara coding partner 🤝

---
# GIT ME REPO BNANE KE TAREEKE

-- git me kaam krne ke liye git ko kuch dena bhi to padega na, matlab git tabhi to dhyan rakhega jab usko bataoge ki bhai tujhe kya kya sambhalna hai. Ab git ke folders banane ke 2 tareeke hote hain:

---

### 1️⃣ `git init` – Apni khud ki repo banao

Agar tumhare paas ek folder hai jisme kaam chal raha hai, to usi folder ko version control me lana ho to bas ye likho:

```bash
git init
```

Isse kya hoga? Git us folder me ek **`.git`** naam ka chhupa hua (hidden) folder bana deta hai, jisme saara ka saara version control ka khel hota hai – history, settings, sab kuch.

---

`.git` ke andar yeh sab cheezein hoti hain:

- `config` → repo ka setting yaha hota hai
- `HEAD` → abhi kis branch pe ho, wo batata hai
- `objects/` → tumhare commits aur data ka compressed backup
- `refs/` → commits, branches, tags ke pointer
- `hooks/` → kuch scripts jo commit se pehle/baad chalte hain
- `description` → repo ka chhota sa intro
- `info/` → ignore karne layak cheezein yaha define hoti hain

> Ye sab directly mat chedna unless tu expert hai 😄

---

### 2️⃣ `git clone` – Kisi aur ki repo ko apne system me le aao

Agar koi online repo pasand aa gayi (jaise GitHub wali), to usey seedha apne system me laane ke liye likho:

```bash
git clone <repo-ka-link>
```

Ye pura folder bana ke uske andar `.git` folder le aata hai – yani ready-made repo!

---

### 🔄 Changes dekhne aur file track karne ka kaam

Agar dekhna ho ki kya kya change hua hai, to:

```bash
git status
```

> Ye batata hai ki kaunsi files track ho rahi hain aur kaunsi nahi.

Agar koi nayi file hai aur Git ko bolna hai "bhai isko bhi track kar", to:

```bash
git add <file-ka-naam>
```

---

⚡ **Quick Recap**:

- `git init` → Apna khud ka project start karna
- `.git folder` → Pura Git ka dimaag yahi hai
- `git clone` → Online repo ko le aana
- `git status` + `git add` → Changes aur tracking ka game

---

🧠 Bas itna samajh lo: Git ko sirf code ka nahi, code ke pichhe ki kahani ka bhi record rakhna hota hai.


## 🔍 GIT DIFF AUR COMMIT – CHANGES KA KHEL

---

### 🧾 `git diff` – Dekho kya badla hai

Jab tumne file me kuch badla kiya ho, lekin abhi tak Git ko bataya nahi ho (matlab `add` bhi nahi kiya), tab `git diff` likh ke check kar sakte ho:

```bash
git diff
```

> Ye batayega ki **exact kaunsi lines** badli hain tumhari file me. Naye line green me, delete kiye line red me dikhte hain. Bhai sab details deta hai ye!

---

### 📥 `git diff --staged` ya `--cached`

Ab agar tumne `git add` karke changes ko staging area me bhej diya hai, aur dekhna hai ki **staging me kya gaya hai**, to likho:

```bash
git diff --staged
```

ya

```bash
git diff --cached
```

> Dono same hi kaam karte hain – jo cheezein staged ho chuki hain, unka diff dikhate hain. 

---

### 📝 `git commit` – Changes ko save karo history me

Ab jab sab kuch theek lag raha ho, aur tu chah raha ho ki Git is point tak ka kaam yaad rakhe, to tu `commit` karega:

```bash
git commit
```

> Ye command staged changes ko Git ki memory me permanently daal deta hai (samajh lo photo khinch leta hai us waqt ki).

---

### 🗣️ Message bhi dena hai? Use `-m`

Commit ke sath message bhi dena ho, jo bata sake ki is commit me kya kiya gaya, to ye likho:

```bash
git commit -m "ye file me navin changes kiye"
```

> Message clear likhna best hota hai future ke liye – warna khud bhi bhool jaoge tumne kya kiya tha 😅

---

### 🔄 TL;DR:

- `git diff` → Unstaged changes dikhao
- `git diff --staged` → Staged changes dikhao
- `git commit` → Changes ko permanent banao
- `git commit -m "msg"` → Commit ke sath ek note bhi chipka do

---

🧠 Git ka kaam sirf file rakhna nahi, **kaunsi file me kya kab kaise badla** – ye pura dhyan rakhna hota hai.
