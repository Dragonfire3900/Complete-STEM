##########
# Config #
##########
LATEX_OPTS += -pdf -verbose -file-line-error -synctex=1 -interaction=nonstopmode

###############
# Definitions #
###############
RM := rm -f 
LATEXMK := latexmk
    # callback: 1
    # continuous: 1
    # executable: latexmk

################
# Main Targets #
################
clean:
	${RM} ./lecs.tex;

all: complete.pdf

####################
# Internal targets #
####################
lecs.tex: $(wildcard ./*/lec[0-9]*.tex)
	@{ $(foreach file, $(shell printf "%s\n" $^ | sort -V),echo "\input{$(file)}";) } > $@

complete.pdf: complete.tex lecs.tex
	${LATEXMK} ${LATEX_OPTS} $^

.PHONY: all clean
