# Variables
LATEX=pdflatex
BIBTEX=bibtex
TEX_FILE=main.tex
PDF_FILE=main.pdf
BIB_DIR=bibtex/bib
FIGS_DIR=figs
SVG2PDF=inkscape --export-type=pdf --export-filename

# Regla por defecto: compilar el documento principal
all: $(PDF_FILE)

# Compilación principal
$(PDF_FILE): $(TEX_FILE) $(wildcard $(FIGS_DIR)/*.svg) $(wildcard $(BIB_DIR)/*.bib)
	@echo "Compilando el documento LaTeX..."
	$(LATEX) $(TEX_FILE)  # Ejecutar pdflatex
	$(BIBTEX) main         # Ejecutar bibtex
	$(LATEX) $(TEX_FILE)    # Ejecutar pdflatex nuevamente
	$(LATEX) $(TEX_FILE)    # Ejecutar pdflatex una vez más para referencias cruzadas

# Convertir archivos SVG a PDF
$(FIGS_DIR)/%.pdf: $(FIGS_DIR)/%.svg
	@echo "Convirtiendo SVG a PDF: $@"
	$(SVG2PDF) $<

# Limpiar archivos generados
clean:
	@echo "Limpiando archivos generados..."
	rm -f *.aux *.fdb_latexmk *.fls *.log *.out *.synctex.gz *.toc *.bbl *.blg

# Limpiar todo, incluyendo archivos PDF generados
clean_all: clean
	rm -f $(PDF_FILE)

# Mostrar las dependencias
show_deps:
	@echo "Dependencias del proyecto:"
	@echo "TEX: $(TEX_FILE)"
	@echo "BIB: $(wildcard $(BIB_DIR)/*.bib)"
	@echo "FIGS: $(wildcard $(FIGS_DIR)/*.svg)"
