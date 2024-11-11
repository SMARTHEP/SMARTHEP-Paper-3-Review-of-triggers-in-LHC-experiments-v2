export TEXINPUTS := ../:${TEXINPUTS}
CONTENTFILE := $(shell find . -maxdepth 1 -name "*.tex")
OUTPUTFILE := $(foreach FILE, $(CONTENTFILE), $(shell basename ${FILE} .tex))
OUTPUTFILE := $(foreach FILE, $(OUTPUTFILE), build/$(FILE).pdf)

all: .copyfiles


build/%.pdf: ./%.tex
	latexmk -pdflatex -jobname=$(basename $@) $<

.copyfiles: $(OUTPUTFILE)
	touch $^

build:
	mkdir -p build

clean:
	rm -rf build