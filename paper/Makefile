LATEX = pdflatex
BIBTEX = bibtex
BASH = bash -c
ECHO = echo
RM = rm -rf
TMP_SUFFS = pdf aux bbl blg log dvi ps eps out
SUFF = pdf

NAME = main

RM_TMP = ${RM} $(foreach suff, ${TMP_SUFFS}, ${NAME}.${suff})

CHECK_RERUN = grep Rerun $*.log

all: ${NAME}.${SUFF}

%.pdf: %.tex
	${LATEX} $<
	${BIBTEX} ${NAME}
	${LATEX} $<
	${LATEX} $<

clean:
	${RM_TMP}

view:
	open $(NAME).pdf &