# GO-Plot-Proteomics-
setwd ("C:/Users/Pawan Jha/Box Sync/WORKING_Soft/Single Cell RNAseq/Single Cell_SCIENCE/Proteomics New/GO_Analysis/Neurons_Phospho")

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
IDs <- c("GO:0007010",	"GO:0030030",	"GO:0010639",	"GO:0022607",	"GO:0030182",	"GO:0050803")
GOCircle(circ, nsub = IDs)

##CC##
IDs <- c("GO:0030054",	"GO:0005856",	"GO:0045202",	"GO:0043228",	"GO:0097458",		"GO:0005737")
GOCircle(circ, nsub = IDs)

##MF##

IDs <- c("GO:0003779",	"GO:0045296",	"GO:0044822",	"GO:0008289",	"GO:0030234",	"GO:0005085")
GOCircle(circ, nsub = IDs)
##########################
