# WARNING: WILL FAIL ON STUFF OLDER THAN 2011 BECAUSE OF pdflatex ISSUES

RM = /bin/rm -f
DVIPS = dvips -Ppdf # The -Ppdf option includes fonts but can screw up on
                    # included graphics.  Use with extreme prejudice.
PS2PDF = ps2pdf

.SUFFIXES: .tex .dvi .ps .pdf

ALLFILES = $(patsubst physics1_ps%.tex,physics1_ps%.pdf,$(wildcard *.tex)) \
	$(patsubst physics1_exam%.tex,physics1_exam%.pdf,$(wildcard *.tex)) \
	$(patsubst worksheet_%.tex,worksheet_%.pdf,$(wildcard *.tex)) physics1_final.pdf
all: $(ALLFILES) clean

.tex.pdf:
	pdflatex $*
	pdflatex $*
	pdflatex $*

clean:
	$(RM) *.log *.aux *.dvi *.toc *.bbl *.blg

spotless: clean
	$(RM) *.pdf *.ps
