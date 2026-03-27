# Git a GitHub - Udělejte si pořádek ve zdrojácích

---

# Co je Git a GitHub

**[Git](https://git-scm.com/)** je nástroj pro správu historie kódu a verzování.  
**[GitHub](https://github.com/)** je platforma, která hostuje Git repozitáře a umožňuje týmovou spolupráci.

---

# Nástroje

- [git](https://git-scm.com/downloads)  
- [gh](https://cli.github.com/)  
- [GitHub Desktop](https://desktop.github.com/download/)  
- [Visual Studio Code](https://code.visualstudio.com/Download)  
- …

---

# Základní terminologie

- **Repository (repo):** Projektová složka sledovaná Gitem, obsahuje soubory i historii.  
- **Clone:** Stažení vzdáleného repozitáře na lokální počítač.  
- **Stage:** Příprava změn pro commit.  
- **Commit:** Snímek změn uložený do repozitáře.  
- **Branch:** Paralelní větev vývoje, často pro nové funkce nebo opravy.  
- **Merge:** Sloučení změn z jedné větve do druhé.  
- **Push:** Odeslání lokálních commitů do vzdáleného repozitáře.  
- **Pull:** Stažení a začlenění změn z remote repozitáře.  

---

# Základní workflow: Nový projekt a první commit na GitHub

1. Vytvořte repozitář (na GitHubu nebo lokálně)  
2. Naklonujte repozitář nebo ho otevřete na svém počítači  
3. Vytvořte nový soubor (např. README nebo projektový soubor)  
4. Přidejte soubor do staging area  
5. Vytvořte commit s komentářem  
6. Nahrajte commit na GitHub (push) 

---

# Konfigurace git a gh po první instalaci

```bash
# Git identita pro commity
git config --global user.name "Jmeno Prijmeni"
git config --global user.email "email@example.com"
git config --global init.defaultBranch main

# Přihlášení do GitHub CLI
gh auth login
gh auth status
```

---

# Příkazy - nový repozitář a GitHub

```bash
git init
# Po úpravě souborů
git add .
git commit -m "Initial commit"
git branch -M main

# Vytvoření repozitáře na GitHubu přes gh
gh repo create NAZEV-REPO --public --source=. --remote=origin

# Alternativa bez gh:
git remote add origin https://github.com/UZIVATEL/NAZEV-REPO.git
git push -u origin main
```

---

# Příkazy - existující repozitář na GitHub

```bash

git clone https://github.com/UZIVATEL/NAZEV-REPO.git
cd NAZEV-REPO

# Po úpravě souborů
git add .
git commit -m "Popis změn"
git pull --rebase origin main
git push origin main
```

---

# Příkazy - pouze lokální repozitář (bez GitHubu)

```bash
git init

# Po úpravě souborů
git add .
git commit -m "První lokální commit"

# Kontrola historie a stavu
git log --oneline --decorate --graph
git status
```

---

# Branch – Commit – Pull Request

![Branch – Commit – Pull Request](branch.png)

---

# Doporučení

- Používejte smysluplné commit message.  
- Jeden commit by měl obsahovat jen souvysející změny.
- Nikdy neukládejte do repozitáře hesla nebo citlivá data.  
- Používejte `.gitignore` pro vyloučení nepotřebných nebo citlivých souborů. 

---

# Dokumentace

- Repozitáře uchovávají dokumentaci na jednom místě s historií verzí.  
- Markdown (`.md`) je jednoduchý, čitelný a GitHub jej hezky renderuje.  
- README soubory vysvětlují nastavení a použití; Wiki slouží pro strukturované návody.  
- Pull requesty umožňují peer review dokumentace.  
- GitHub Pages dokáže publikovat dokumentaci jako web.  
- GitHub Copilot může pomoci s psaním dokumentace podle zdrojového kódu.  
