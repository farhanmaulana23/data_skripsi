# Pengolahan Data Skripsi Farhan
Ada beberapa data penting yang harus digunakan:

  - Viabilitas transforman dalam cfu/ml (viabilitas.csv)
  - Aktivitas umum WCB dalam U/ml selama 90 menit (akt_umum.csv)
  - Aktivitas spesifik WCB dalam U/cfu selama 90 menit (akt_spes.csv)
  - Aktivitas umum WCB dalam U/ml selama 72 jam (termostabilitas.csv)
  
# Berikut skripnya!
Untuk Gambar 4.2
```sh
library(ggplot2)
via_1 <- read.csv(file = "viabilitas.csv")
graf42 <- ggplot(via_1, aes(x=Treatment, y=cfu, fill = Treatment)) 
+ geom_boxplot(size=0.5) 
+ geom_jitter(width=0.05) 
+ labs(title="Uji Viabilitas LCC dan T-LCC",x="Perlakuan", y = "cfu/mL")
graf42

```
Untuk Gambar 4.3
```sh
library(ggplot2)
pnpb_1 <- read.csv(file = "akt_umum.csv")
graf43 <- ggplot(via_1, aes(x=Treatment, y=aktivitas, fill = Treatment)) 
+ geom_boxplot(size=0.5) 
+ geom_jitter(width=0.05) 
+ labs(title="Uji Aktivitas pNPB",x="Perlakuan", y = "U/mL")
graf43
```
Untuk Gambar 4.4
```sh
library(ggplot2)
pnpb_1 <- read.csv(file = "akt_spes.csv")
graf44 <- ggplot(via_1, aes(x=Treatment, y=aktivitas, fill = Treatment)) 
+ geom_boxplot(size=0.5) 
+ geom_jitter(width=0.05) 
+ labs(title="Uji Aktivitas pNPB",x="Perlakuan", y = "U/cfu")
graf44
```
Untuk Gambar 4.5
```sh
library(ggplot2)
ter_1 <- read.csv(file="termostabilitas_fix.csv")
ter_1$Waktu <- factor(ter_1$Waktu)
melt_ter1 <- melt(ter_1)

p <- ggplot(melt_ter1, aes(x=Waktu, y=value, fill=variable))+geom_boxplot() +facet_wrap(~variable)+labs(x="Waktu (jam)", y="U/mL")+scale_fill_brewer(labels = c("T+L (non), 55 ??C
+ ","T+L (ind), 55 ??C
+ ","T+L(non), 37 ??C
+ ","L, 55 ??C
+ ","L, 37 ??C
+ "))
```
