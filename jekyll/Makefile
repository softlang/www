ssh = softlang@linux.uni-koblenz.de

none:

# Install gems in Gemfile
install-gems:
	bundle install

# Show where a theme is installed
show:
	-bundle show jekyll-theme-
	-bundle show minima

# Build site
build:
	bundle exec jekyll build

# Serve site on localhost
serve:
	bundle exec jekyll serve

# Pack site
pack:
	cp ../../yas/dump.json _site/yas
	rm site.zip; cd _site; zip -r ../site.zip .

# Upload site's zipfile to web server
upload:
	scp site.zip ${ssh}:www

# Unzip site on web server
unzip:
	ssh ${ssh} "cd www; unzip -o site.zip"

# Deploy site on web server
deploy:
	make build
	make pack
	make upload
	make unzip

clean:
	rm -f yas/languages.md
	rm -f yas/functions.md
	rm -f yas/representations.md
	rm -f yas/externals.md
	rm -f yas/files.md
	rm -f yas/directories.md
	rm -f yas/languages/*.md
	rm -f yas/functions/*.md
	rm -f yas/representations/*.md
	rm -f yas/directories/*.md
	rm -f yas/files/*.md
