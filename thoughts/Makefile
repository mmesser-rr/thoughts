SRCDIRS = .
SRCEXTS = .md
SOURCES = $(foreach d,$(SRCDIRS),$(wildcard $(addprefix $(d)/*,$(SRCEXTS))))
HTMLS = $(addsuffix .html, $(basename $(SOURCES)))

html:$(HTMLS) index.html

clean:
	-rm *.html

%.html:%.md
	markdown $< > $@

index.html:$(HTMLS)
	echo "<h1>Index</h1>" > $@
	echo "<ul>" >> $@
	$(foreach h,$(HTMLS),echo "<li><a href=\"$(h)\">$(h)</a></li>" >> $@)
	echo "</ul>" >> $@

