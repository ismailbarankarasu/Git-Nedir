
# Git Nedir? Temelden İleri Seviyeye Git Kullanımı

## 1. Git'e Giriş

Git, yazılım geliştirme projelerinde kullanılan popüler bir **versiyon kontrol sistemidir (VCS)**. Bir projenin geçmişindeki tüm değişiklikleri izler, birden çok geliştiricinin aynı projede aynı anda çalışabilmesini sağlar ve hataların takibini kolaylaştırır. Git, projelerdeki dosyaların geçmişini takip etmek için veri yapıları kullanır ve bir dağıtık sistem olarak çalışır.

---

## 2. Git Temel Komutları

### 2.1. Git'i Başlatmak

Yeni bir Git deposu başlatmak için şu komutu kullanabilirsiniz:

```bash
git init
```

Bu komut, geçerli dizinde bir `.git` dizini oluşturur ve bu dizin, projenizin Git tarafından takip edilmesini sağlar.

---

### 2.2. Depoyu Klonlamak

Bir uzaktaki Git reposunu bilgisayarınıza klonlamak için:

```bash
git clone <repository_url>
```

Bu komut, uzaktaki bir depoyu bilgisayarınıza kopyalar.

---

### 2.3. Değişiklikleri Takip Etmek

Değişiklikleri takip etmek ve Git’e eklemek için:

```bash
git add <file_name>
```

Tüm değişiklikleri eklemek için:

```bash
git add .
```

---

### 2.4. Değişiklikleri Kaydetmek

Değişikliklerinizi kaydetmek için:

```bash
git commit -m "Commit mesajı"
```

---

### 2.5. Değişiklikleri Göndermek

Yerel değişikliklerinizi uzaktaki depoya göndermek için:

```bash
git push origin main
```

---

### 2.6. Değişiklikleri Çekmek

Uzaktaki depodaki değişiklikleri bilgisayarınıza çekmek için:

```bash
git pull origin main
```

---

## 3. Git Branching (Dallanma)

### 3.1. Dallanma (Branch) Nedir?

Git'teki dallanma, projede bağımsız bir geliştirme ortamı yaratır. Ana projeden bağımsız olarak yeni özellikler geliştirebilir veya hata düzeltmeleri yapabilirsiniz.

---

### 3.2. Yeni Bir Dal Oluşturmak

Yeni bir dal oluşturmak için şu komutu kullanabilirsiniz:

```bash
git branch <branch_name>
```

---

### 3.3. Dal’a Geçmek

Bir dala geçmek için şu komutu kullanın:

```bash
git checkout <branch_name>
```

Yeni bir dal oluşturup ona geçmek için:

```bash
git checkout -b <branch_name>
```

---

### 3.4. Dal Birleştirmek (Merge)

Bir dalı diğer dal ile birleştirmek için şu komutu kullanabilirsiniz:

```bash
git merge <branch_name>
```

Örnek: `feature-branch` dalını `main` dalına birleştirmek için:

```bash
git checkout main
git merge feature-branch
```

---

## 4. Git Rebase

Rebase, git geçmişinizi yeniden düzenler. Rebase kullanarak commit geçmişinizi daha temiz ve anlaşılır tutabilirsiniz.

---

### 4.1. Rebase Yapmak

`feature-branch` dalını `main` dalına rebase etmek için:

```bash
git checkout feature-branch
git rebase main
```

---

## 5. Git Bisect

Git bisect, bir hatanın hangi commit'ten kaynaklandığını bulmak için kullanılan bir araçtır. İki commit arasında binary search (ikili arama) yaparak problemi tespit eder.

### 5.1. Git Bisect Kullanımı

Hatayı hangi commit'in oluşturduğunu bulmak için şu adımları izleyebilirsiniz:

1. Bisect modunu başlatın:

```bash
git bisect start
```

2. Hata bulunan commit'i işaretleyin:

```bash
git bisect bad
```

3. Sağlam commit'i işaretleyin:

```bash
git bisect good <commit_id>
```

Git, her iki commit arasında ikili arama yaparak hatalı commit'i bulacaktır.

---

## 6. Git Cherry-Pick

Bir commit'i bir başka dalda uygulamak için:

```bash
git cherry-pick <commit_id>
```

Bu komut, belirli bir commit'i mevcut dalınıza uygular. Örneğin, `12345abc` commit'ini almak için:

```bash
git cherry-pick 12345abc
```

---

## 7. Git Submodule (Alt Modül)

Alt modüller, bir projede başka bir Git reposunu takip etmenin bir yoludur.

### 7.1. Alt Modül Eklemek

Bir alt modül eklemek için:

```bash
git submodule add <repository_url>
```

Örneğin, `my-submodule` isminde bir alt modül eklemek için:

```bash
git submodule add https://github.com/username/repo.git my-submodule
```

### 7.2. Alt Modülü Güncellemek

Alt modülü güncellemek için şu komutu kullanabilirsiniz:

```bash
git submodule update --remote
```

---

## 8. Git Hooks

Git hooks, Git işlemleri sırasında otomatik olarak çalıştırılacak betiklerdir. Bu betikler, commit işlemleri öncesinde veya sonrasında çalışabilir.

### 8.1. Pre-Commit Hook

Örneğin, kodunuzu commit etmeden önce bir linter çalıştırmak için pre-commit hook kullanabilirsiniz.

Pre-commit hook dosyasını oluşturun:

```bash
touch .git/hooks/pre-commit
```

Ve ardından dosyaya aşağıdaki script'i ekleyin:

```bash
#!/bin/sh
# Kodunuzu linter ile kontrol edin
npm run lint
```

---

## 9. GitHub İleri Seviye Özellikler

GitHub, Git’in bulut tabanlı versiyon kontrol sistemidir. GitHub üzerinde projelerinizi yönetmek ve işbirliği yapmak çok daha kolaydır.

### 9.1. Pull Request (PR) Yaratmak

Bir projede değişiklik yapıp ana projeye katkı sağlamak için pull request oluşturabilirsiniz. Bu süreç, katkılarınızın gözden geçirilip onaylanmasını sağlar.

---

### 9.2. Fork ve Pull Request

Bir projeyi fork'lamak ve katkı sağlamak için şu adımları izleyin:

1. Projeyi fork'layın
2. Kendi fork'unuzda değişiklikleri yapın
3. Pull request oluşturun

---

### 9.3. GitHub Actions (CI/CD)

GitHub Actions, sürekli entegrasyon (CI) ve sürekli teslimat (CD) için kullanılan güçlü bir araçtır. Projelerinizde testleri otomatikleştirmek ve deploy işlemleri için action'lar yazabilirsiniz.
