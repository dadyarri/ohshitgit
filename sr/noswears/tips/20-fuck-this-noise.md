---
tags: tip
title: Zaboravi sve ovo, odustajem.
id: forget-this-noise
note: this should always be the last one in the list, so setting order to 20 so I don't have to re-name/re-order it
order: 20
---

```git
cd ..
sudo rm -r stupid-git-repo-dir
git clone https://some.github.url/stupid-git-repo-dir.git
cd stupid-git-repo-dir
```

Hvala Eric V. za ovo. Sve pritužbe na korištenje `sudo`-a u ovoj šali mogu se usmjeriti na njega. 


Ali sada stvarno, ako vam je branč toliko uništen da trebate resetovati stanje vašeg repositorija kako bi bio isti kao i remote repositori na "git-approved" način, pokušajte s ovim, ali pazite ovi su destruktivne i nepovratne akcije!

```git
# uzmi zadnje stanje origin-a
git fetch origin
git checkout master
git reset --hard origin/master
# izbriši sve fajlove i foldere koje git ne prati
git clean -d --force
# ponovi checkout/reset/clean za svaki pokvareni branč
```