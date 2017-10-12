
# Hello World
different color for highlighting genes in Manhattan plot in qqman

Hi  would like to have two differents colors for my highliting genses. Label 1 and label 2 shpuld be green and the others labels should be are red. It is possible an how I can do this?


FST plots in R: using a fancy R package..
Installl and load the qqman package

install.packages("qqman")
library(qqman)

#Read in data file for complet genome: allFST.txt
fst=read.table(file.choose(), header=F)

Transform data into a format readable by qqman 

group <-  substr(fst$V1, 6, 10)                # get rid of “group”  CHR <- as.numeric(as.roman(group)) # turn into number 
BP <- fst$V2               # BP=“base-pair” position on chromosome 
FST <- fst$V3              # Fst’s 
mydf1 <-data.frame(CHR, BP, FST)          # create a data frame 
mydf2 <-  mydf1[order(mydf1$CHR), ]    # order df by chr. 
SNP <- seq(1, length(mydf2$CHR), 1)       # build SNP-IDs 
mydf3 <- data.frame(SNP, mydf2) # build new df with SNP-IDs 
rownames(mydf3) <- NULL                 # get rid of rownames 


Highlighting genes
Define SNP position of ATP1a1a and EDA and the ankwon snp

label1 <- as.vector(subset(mydf3, CHR==1 & BP >= 21703186 & BP < 21730451, select=c(SNP,BP) ) )

startATP1a1a=min(label1$SNP) 
endATP1a1a=max(label1$SNP) 

label2 <- as.vector(subset(mydf3, CHR==4 & BP >= 12800220 & BP < 12810446, select=c(SNP,BP) ) ) 
 
 startEDA=min(label2$SNP)
 endEDA=max(label2$SNP)
 
 label3 <- as.vector(subset(mydf3, CHR==7 & BP >= 2023000 & BP <  2026000, select=c(SNP,BP) ) ) 
 
 startx7=min(label3$SNP) 
 endx7=max(label3$SNP)
 
 label4 <- as.vector(subset(mydf3, CHR==2 & BP >= 11833000 & BP <  11836000 , select=c(SNP,BP) ) ) 
 
 startx2=min(label4$SNP) 
 endx2=max(label4$SNP)
 
 label5 <- as.vector(subset(mydf3, CHR==9 & BP >= 8584500 & BP <  8585500, select=c(SNP,BP) ) ) 
 
 startx9=min(label5$SNP) 
 endx9=max(label5$SNP)
 
 label6 <- as.vector(subset(mydf3, CHR==19 & BP >= 2463000 & BP <  2466000, select=c(SNP,BP) ) ) 
 
 startx19=min(label6$SNP) 
 endx19=max(label6$SNP)
 
 label7 <- as.vector(subset(mydf3, CHR==13 & BP >= 8453000 & BP <  8456000, select=c(SNP,BP) ) ) 
 
 startx13=min(label7$SNP) 
 endx13=max(label7$SNP)
 
 label8 <- as.vector(subset(mydf3, CHR==20 & BP >= 8903000 & BP <  8906000, select=c(SNP,BP) ) ) 
 
 startx20=min(label8$SNP) 
 endx20=max(label8$SNP)
 
 label9 <- as.vector(subset(mydf3, CHR==8 & BP >= 1253000 & BP <  1256000, select=c(SNP,BP) ) ) 
 
 startx8=min(label9$SNP) 
 endx8=max(label9$SNP)
 
 label10 <- as.vector(subset(mydf3, CHR==12 & BP >= 14344700 & BP <  14345100, select=c(SNP,BP) ) ) 
 
 startx12=min(label10$SNP) 
 endx12=max(label10$SNP)
 
 
  label11 <- as.vector(subset(mydf3, CHR==16 & BP >= 11413000 & BP <  11416000, select=c(SNP,BP) ) ) 
 
 startx16=min(label11$SNP) 
 endx16=max(label11$SNP)
 
 
   label12 <- as.vector(subset(mydf3, CHR==6 & BP >= 6273000 & BP <  6276000, select=c(SNP,BP) ) ) 
 
 startx6=min(label12$SNP) 
 endx6=max(label12$SNP)
 
   label13 <- as.vector(subset(mydf3, CHR==3 & BP >= 1413000 & BP <  1416000, select=c(SNP,BP) ) ) 
 
 startx3=min(label13$SNP) 
 endx3=max(label13$SNP) 
   label14 <- as.vector(subset(mydf3, CHR==11 & BP >= 5553000 & BP <  5556000, select=c(SNP,BP) ) ) 
 
 startx11=min(label14$SNP) 
 endx11=max(label14$SNP)
 
   label15 <- as.vector(subset(mydf3, CHR==18 & BP >= 5404900 & BP <  5405110, select=c(SNP,BP) ) ) 
 
 startx18=min(label15$SNP) 
 endx18=max(label15$SNP)
 
   label16 <- as.vector(subset(mydf3, CHR==15 & BP >= 3493000 & BP <  3496000, select=c(SNP,BP) ) ) 
 
 startx15=min(label16$SNP) 
 endx15=max(label16$SNP)
 
 
   label17 <- as.vector(subset(mydf3, CHR==10 & BP >= 3073000 & BP <  3076000, select=c(SNP,BP) ) ) 
 
 startx10=min(label17$SNP) 
 endx10=max(label17$SNP)
     label18 <- as.vector(subset(mydf3, CHR==14 & BP >= 6743000 & BP <  6746000, select=c(SNP,BP) ) ) 
 
 startx14=min(label18$SNP) 
 endx14=max(label18$SNP)
 
    label19 <- as.vector(subset(mydf3, CHR==17 & BP >= 6014800 & BP <  6015200, select=c(SNP,BP) ) ) 
 
 startx17=min(label19$SNP) 
 endx17=max(label19$SNP)
 
    label20 <- as.vector(subset(mydf3, CHR==5 & BP >= 2493000 & BP <  2496000, select=c(SNP,BP) ) )  
 startx5=min(label20$SNP) 
 endx5=max(label20$SNP)
 
    label21 <- as.vector(subset(mydf3, CHR==21 & BP >= 6203000 & BP <  6206000, select=c(SNP,BP) ) ) 
 
 startx21=min(label21$SNP) 
 endx21=max(label21$SNP)
 
 
Plot chromosomes 1-21, with genes highlighted 

manhattan(subset(mydf3, CHR %in% c(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21)), chr="CHR", bp="BP",
p="FST",  snp="SNP" , logp=FALSE, ylab="Fst", ylim=c(0,1.1),
 cex=0.4, highlight = SNP[c(startATP1a1a:endATP1a1a, startEDA:endEDA,
 startx7:endx7, startx2:endx2, startx9:endx9, startx19:endx19,
 startx13:endx13, startx20:endx20, startx8:endx8, startx12:endx12,
 startx16:endx16, startx6:endx6, startx3:endx3, startx11:endx11,
 startx18:endx18, startx15:endx15, startx10:endx10, startx14:endx14, startx17:endx17, startx5:endx5, startx21:endx21)]) 
   
 
    label12 <- as.vector(subset(mydf3, CHR==6 & BP >= 6273000 & BP <  6276000, select=c(SNP,BP) ) ) 
 
 startx6=min(label12$SNP) 
 endx6=max(label12$SNP)
 
   label13 <- as.vector(subset(mydf3, CHR==3 & BP >= 1413000 & BP <  1416000, select=c(SNP,BP) ) ) 
 
 startx3=min(label13$SNP) 
 endx3=max(label13$SNP) 
   label14 <- as.vector(subset(mydf3, CHR==11 & BP >= 5553000 & BP <  5556000, select=c(SNP,BP) ) ) 
 
 startx11=min(label14$SNP) 
 endx11=max(label14$SNP)
 
   label15 <- as.vector(subset(mydf3, CHR==18 & BP >= 5404900 & BP <  5405110, select=c(SNP,BP) ) ) 
 
 startx18=min(label15$SNP) 
 endx18=max(label15$SNP)
 
   label16 <- as.vector(subset(mydf3, CHR==15 & BP >= 3493000 & BP <  3496000, select=c(SNP,BP) ) ) 
 
 startx15=min(label16$SNP) 
 endx15=max(label16$SNP)
 
 
   label17 <- as.vector(subset(mydf3, CHR==10 & BP >= 3073000 & BP <  3076000, select=c(SNP,BP) ) ) 
 
 startx10=min(label17$SNP) 
 endx10=max(label17$SNP)
     label18 <- as.vector(subset(mydf3, CHR==14 & BP >= 6743000 & BP <  6746000, select=c(SNP,BP) ) ) 
 
 startx14=min(label18$SNP) 
 endx14=max(label18$SNP)
 
    label19 <- as.vector(subset(mydf3, CHR==17 & BP >= 6014800 & BP <  6015200, select=c(SNP,BP) ) ) 
 
 startx17=min(label19$SNP) 
 endx17=max(label19$SNP)
 
    label20 <- as.vector(subset(mydf3, CHR==5 & BP >= 2493000 & BP <  2496000, select=c(SNP,BP) ) )  
 startx5=min(label20$SNP) 
 endx5=max(label20$SNP)
 
    label21 <- as.vector(subset(mydf3, CHR==21 & BP >= 6203000 & BP <  6206000, select=c(SNP,BP) ) ) 
 
 startx21=min(label21$SNP) 
 endx21=max(label21$SNP)
 
 
Plot chromosomes 1-21, with genes highlighted 

manhattan(subset(mydf3, CHR %in% c(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21)), chr="CHR", bp="BP",
p="FST",  snp="SNP" , logp=FALSE, ylab="Fst", ylim=c(0,1.1),
 cex=0.4, highlight = SNP[c(startATP1a1a:endATP1a1a, startEDA:endEDA,
 startx7:endx7, startx2:endx2, startx9:endx9, startx19:endx19,
 startx13:endx13, startx20:endx20, startx8:endx8, startx12:endx12,
 startx16:endx16, startx6:endx6, startx3:endx3, startx11:endx11,
 startx18:endx18, startx15:endx15, startx10:endx10, startx14:endx14, startx17:endx17, startx5:endx5, startx21:endx21)]) 
   
 
 



