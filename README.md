# GO-Plot-Proteomics-
setwd ("C:/Users/Pawan Jha")

library(GOplot)
library(ggplot2)
library(ggdendro)
library(gridExtra)
library(RColorBrewer)

data_david <- read.csv("David_GO.csv")

data_genelist <- read.csv("gene_logFC.csv")

circ <- circle_dat(data_david, data_genelist)
#################################Barplot GO########### size width and lenghth 6
GOBar(circ, display = 'multiple')
##################################
GOBar(circ, display = 'multiple', title = 'Z-score coloured barplot', zsc.col = c('yellow', 'black', 'cyan'))

#############cirplot##########size width and lenghth 8
##BP##
IDs <- c("GO",	"GO:",	"GO:",	"GO:",	"GO:",	"GO:")######GO: GO stands for GO number ###########
GOCircle(circ, nsub = IDs)

##CC##
IDs <- c("GO",	"GO:",	"GO:",	"GO",	"GO:",		"GO:")
GOCircle(circ, nsub = IDs)

##MF##

IDs <- c("GO:",	"GO:",	"GO:",	"GO",	"GO",	"GO")
GOCircle(circ, nsub = IDs)
##########################
