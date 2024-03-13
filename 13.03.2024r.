# Weronika Mądzielewska
# Technologie cyfryzacji danych biotechnologicznych
# 13.03.2024r.

library(rtracklayer)
library("ggplot2")

setwd(dir="c:/Users/Student/OneDrive - University of Warmia and Mazuria in Olsztyn/Pulpit/WerMad/")
getwd()


#TABELA======================================================
gtf=import.gff("Homo_sapiens.GRCh38.111.chr.gtf")
class(gtf)
summary(gtf)
structure(gtf)

gtf_tab=as.data.frame(gtf)
table(gtf_tab$seqnames)
table(gtf_tab$gene_biotype)
head(gtf)

gtf_geny=gtf_tab[gtf_tab$type=="gene",]
table(gtf_geny$gene_biotype)
ggplot(gtf_geny,aes(gtf_geny$width,gtf_geny$start,colour=gtf_geny$gene_biotype))+geom_point()


ggplot(gtf_geny, aes(x = gene_biotype, y = width, fill = gene_biotype)) +
  geom_boxplot() + scale_y_log10() +
  labs(x = "Biotyp", y = "Długość genu", title = "Rozklad dlugosci genów w zalezności od biotypu")
