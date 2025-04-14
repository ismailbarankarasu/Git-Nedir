
# Git Nedir?

Git, yazılım geliştirme sürecinde kullanılan en popüler **versiyon kontrol sistemidir**. Kod üzerinde yapılan değişikliklerin izlenmesini ve yönetilmesini sağlar. Bir yazılım projesinde kodlar sürekli değişir ve güncellenir. Git, bu değişikliklerin kaydını tutarak, projeye daha iyi bir kontrol ve düzen sağlar. Git, projelerdeki tüm değişiklikleri yerel olarak saklar ve takım üyeleri arasında senkronize çalışmayı sağlar.

Bu repo, Git komutları ve temel kullanımının açıklamalarını içermektedir. Git'in ne olduğu, nasıl kullanıldığı ve temel komutların işlevleri hakkında bilgi edinmek için bu dokümanı takip edebilirsiniz.

## İçerik

- [Git Nedir?](#git-nedir)
- [Git'in Temel Kavramları](#gitin-temel-kavramları)
- [Git Komutları](#git-komutları)
  - [`git init`](#git-init)
  - [`git add`](#git-add)
  - [`git commit`](#git-commit)
  - [`git status`](#git-status)
  - [`git log`](#git-log)
  - [`git branch`](#git-branch)
  - [`git checkout`](#git-checkout)
  - [`git merge`](#git-merge)
  - [`git remote add`](#git-remote-add)
  - [`git push`](#git-push)
  - [`git pull`](#git-pull)
- [Git ve GitHub](#git-ve-github)
- [Git ile Proje Yönetimi](#git-ile-proje-yönetimi)

---

## Git Nedir?

Git, bir **versiyon kontrol sistemi** olarak yazılımdaki tüm değişikliklerin kaydını tutar. Bu sayede yazılımcılar projelerinde yaptıkları değişiklikleri kolayca takip edebilir, eski sürümlere geri dönebilir ve başkalarıyla işbirliği yapabilirler. Git, özellikle ekip çalışmasında önemli bir rol oynar, çünkü aynı projede birden fazla kişi aynı anda çalışabilir ve Git, tüm bu değişiklikleri birleştirip düzgün bir şekilde yönetir.

---

## Git'in Temel Kavramları

- **Repository (Depo):** Git’in takip ettiği tüm dosyaların bulunduğu klasördür. Hem yerel (bilgisayarındaki) hem de uzak (örneğin GitHub'daki) depolar olabilir.
- **Commit:** Projendeki değişikliklerin kaydedildiği anıdır. Her commit bir “anlık” sürüm olarak kaydedilir.
- **Branch (Dal):** Git’te paralel olarak birden fazla farklı kod geliştirebilmek için dallar kullanılır.
- **Merge:** Farklı dallardaki değişikliklerin birleştirilmesidir.
- **Push:** Yapılan değişikliklerin uzak depoya gönderilmesidir.
- **Pull:** Uzak depodaki güncellemelerin yerel depoya indirilmesidir.

---

## Git Komutları

Aşağıda en yaygın kullanılan **Git komutları** ve ne işe yaradıkları açıklanmıştır:

### `git init`
**Açıklama:**  
Git deposu başlatır. Git ile projeyi izlemeye başlamak için kullanılır.

```bash
git init
```

### `git add`
**Açıklama:**  
Çalışma alanında yapılan değişiklikleri "staging" alanına ekler. Bu, commit için hazır hale getirilmiş değişiklikleri ifade eder.

```bash
git add dosya.txt  # Belirli dosyayı ekler
git add .  # Tüm değişiklikleri ekler
```

### `git commit`
**Açıklama:**  
Staging alanındaki değişiklikleri kaydeder. Her commit ile projede bir sürüm oluşturulur.

```bash
git commit -m "Değişiklik mesajı"
```

### `git status`
**Açıklama:**  
Çalışma alanındaki ve staging alanındaki değişikliklerin durumunu gösterir. Hangi dosyaların değiştirilip commit’e eklendiğini görmeni sağlar.

```bash
git status
```

### `git log`
**Açıklama:**  
Commit geçmişini gösterir. Hangi değişikliklerin ne zaman yapıldığını görmek için kullanılır.

```bash
git log
```

### `git branch`
**Açıklama:**  
Projede kullanılan dalları listeler. Yeni bir dal oluşturmak için de kullanılır.

```bash
git branch              # Mevcut dalları listeler
git branch yeni-dal     # Yeni bir dal oluşturur
```

### `git checkout`
**Açıklama:**  
Başka bir dala geçiş yapmanı sağlar. Bu komut ile projede farklı geliştirmelere başlanabilir.

```bash
git checkout ana-dal     # Ana dalına geçiş
git checkout yeni-dal    # Yeni dalına geçiş
```

### `git merge`
**Açıklama:**  
İki dalı birleştirir. Genellikle yeni özellikler üzerinde çalışan bir dalı ana dala entegre etmek için kullanılır.

```bash
git checkout ana-dal     # Ana dalına geçiş yap
git merge yeni-dal       # Yeni dalı ana dal ile birleştir
```

### `git remote add`
**Açıklama:**  
Yerel projeyi uzaktaki bir Git deposuna bağlar.

```bash
git remote add origin https://github.com/kullanici/repo.git
```

### `git push`
**Açıklama:**  
Yerel depodaki değişiklikleri uzak depoya gönderir.

```bash
git push -u origin ana-dal
```

### `git pull`
**Açıklama:**  
Uzak depodaki değişiklikleri yerel depoya indirir.

```bash
git pull
```

---

## Git ve GitHub

Git, **yerel** bir versiyon kontrol sistemidir. GitHub ise **bulut tabanlı** bir Git depolama platformudur. Git, projeyi bilgisayarında takip ederken, GitHub uzak bir sunucuda projeni saklar.

GitHub üzerinden projeye katkıda bulunan kişiler, kendi bilgisayarlarında değişiklik yapabilir ve bu değişiklikleri GitHub üzerinden paylaştırabilirler.

---

## Git ile Proje Yönetimi

Git ve GitHub, özellikle büyük projelerde ekip çalışmasını kolaylaştırır. Projeyi **branching** ile farklı bölümlere ayırabilir ve her biri üzerinde bağımsız olarak çalışabilirsiniz. Değişiklikler tamamlandığında, **merge** ile bu bölümleri birleştirirsiniz.

Git, ayrıca **commit** mesajları sayesinde hangi değişikliğin hangi amacı taşıdığını belgeler ve geri dönmek gerektiğinde eski sürümlere dönme imkanı sağlar.

---

## Sonuç

Git, yazılım geliştirme sürecinin temel taşlarından biridir. Değişiklikleri izlemek, yönetmek ve ekip çalışmasını kolaylaştırmak için olmazsa olmaz bir araçtır. Bu rehberde, Git’in temel komutları ve nasıl kullanılacağı hakkında bilgi edindiniz.

Daha fazla bilgi için [Git resmi belgelere](https://git-scm.com/doc) göz atabilirsiniz.

---

**Proje Linki:** [Git-Nedir GitHub Repo](https://github.com/ismailbarankarasu/Git-Nedir)
