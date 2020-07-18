# The goal here is to build a proper SRPM file
# We don't really support it so it will be really hackish

srpm:
	dnf install -y perl
	cd SOURCES && make depend
	tar -czf SOURCES.tgz SOURCES
	cp SOURCES.tgz SOURCES/
	sed -i "s/Source1: Makefile/Source0: SOURCES.tgz/" $(spec)
	rpmbuild --define "_topdir $(shell pwd)" -bs $(spec)
	mv SRPMS/* $(outdir)/
