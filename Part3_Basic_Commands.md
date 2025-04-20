
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
- `git diff --staged / --cached` → Staged changes dikhao
- `git commit` → Changes ko permanent banao
- `git commit -m "msg"` → Commit ke sath ek note bhi chipka do

---

🧠 Git ka kaam sirf file rakhna nahi, **kaunsi file me kya kab kaise badla** – ye pura dhyan rakhna hota hai.



## 🧹 FILES HATAO YA RENAME KARO – `git rm`, `git mv`, aur `git commit -a`

---

### 🔥 `git rm <file_name>` – File ko hatao Git aur system dono se

Agar koi file Git me tracked hai aur tum use hataana chahte ho, to `git rm <file_name>` likho. Lekin dhyaan rahe, **ye file tumhare system se bhi ud jaayegi** (local se bhi delete ho jaati hai).

```bash
git rm filename.txt
```

Agar file staged hai aur hata nahi rahi to **force** lagana padega:

```bash
git rm --force filename.txt
# ya short me
git rm -f filename.txt
```

---

### 🚫 `git rm --cached <file_name>` – Sirf Git se hatao, system me rehne do

Ye tab kaam aata hai jab file galti se track ho gayi (jaise `.env`, `node_modules` etc.) aur ab tum chahte ho Git usko bhool jaaye – par local folder me file bani rahe:

```bash
git rm --cached filename.txt
```

> Ye file ko Git ke tracking se hata dega, lekin tumhare computer se nahi.

---

### 🔁 `git mv` – File ka naam badlo, Git ko bhi pata chale

Normally agar file ka naam rename karte ho manually (Explorer me ya `mv` command se), to Git us change ko track nahi karta. But agar tum chaahte ho ki Git use rename ke roop me hi samjhe, to use karo:

```bash
git mv old_name.txt new_name.txt
```

---

### ⚡ `git commit -a` – Bina staging ke seedha commit

Kayi baar tumhe sab kuch ek hi baar me karna hota hai – matlab file me change karo aur seedha commit kar do bina `git add` kiye. Tab use karo:

```bash
git commit -a -m "sab kuch ek hi baar me"
```

> **Note:** Ye sirf unhi files pe kaam karta hai jo pehle se tracked ho. Nayi files pe nahi chalega.

---

## 📜 COMMIT HISTORY DEKHO – `git log` ke variations

---

### 📘 Simple log:

```bash
git log
```

> Ye dikhaata hai har commit ki puri kahani – jaise ki:

- `checksum` (commit ID)
- `author_name`
- `author_email`
- `commit_message`
- `date_written`

---

### 🧾 Concise log with stats:

```bash
git log --stat
```

> Ye dikhaata hai ki kaunse files me kitne lines badle.

---

### 🔢 Limited commits:

```bash
git log -3
```

> Sirf last 3 commits dikha dega.

---

### 🔍 Patch ke sath har commit ka diff:

```bash
git log --patch
```

> Har commit ke andar kya-kya lines add/remove hui – sab detail me dikhata hai.

---

Bhai Git ek yaadash wala dost hai – lekin use tumhe batana padta hai ki kya yaad rakhna hai aur kya bhool jana hai 😄


## 🔎 GIT LOG KO FILTER KARNA – Sirf Jo Zarurat Ho Wahi Dekho

---

Kabhi kabhi tumhe **poora history** dekhne ki zarurat nahi hoti, bas kuch specific hi chahiye hota hai – jaise ki:

### 📅 Sirf pichle 2 hafte ka kaam:

```bash
git log --since=2.weeks
```

> Ye sirf unhi commits ko dikhayega jo pichle 2 hafton me kiye gaye hain.

---

### 🧑 Kisi particular author ne kya kiya:

```bash
git log --author="xyz"
```

> Isse sirf us author ke commits dikhenge jiska naam tumne diya ho (`xyz` ke jagah apna naam daal dena).

---

### 🔍 Commit message me koi specific word ho:

```bash
git log --grep="bugfix"
```

> Jaise maan lo tumhe sirf “bugfix” ya “UI update” waale commits dekhne hain.

---

## 🛠️ GADBAD HO GAYI? – `git commit --amend` SE FIX KARO

---

Kabhi kabhi hota hai na – tum commit kar dete ho, aur baad me lagta hai:

- Arre yaar file add karna bhool gaya!
- Commit message galat daal diya!
- Jldi commit maar diya bina sochhe!

Us waqt **`git commit --amend`** kaafi kaam ka hota hai.

```bash
git commit --amend
```

> Ye tumhara **last commit overwrite** kar deta hai. Tum naya message de sakte ho, aur jo files staged hain, unko hi include karega.

⚠️ **Lekin ek warning** – agar tumne ye commit kisi ke saath share kar liya tha (jaise GitHub push kar diya), to uska history todna risky ho sakta hai. Collaborators confuse ho jaate hain. Isliye amend ko carefully use karo – sirf apne local kaam me.

---

## 🧯 STAGED FILE KO UNSTAGE KARNA – `git restore --staged`

---

Kabhi file ko `git add` kar diya, par baad me laga “abhi to ye ready hi nahi hai” – uss waqt kaam aata hai:

```bash
git restore --staged <file_name>
```

> Ye command file ko **unstage** kar degi, mtlb staging area se hata degi. Lekin original file tumhare working directory me rahegi.

⚠️ **Dhyan rahe**: Agar tumne iske saath `--worktree` bhi laga diya, to file ko bilkul waise kar dega jaise last commit me thi – to saari nayi changes bhi udd sakti hain. Soch samajh ke chalana bhai!

---





