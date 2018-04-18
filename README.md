# Transforming PLP programs to OSDD programs
* Load xform.pl (in XSB this is `?- [xform].`)
* Run: `?- transform_file('inputfile', 'outputfile')`
* It is assumed that all `values/2` declarations appear before any other lines of code in 'inputfile'.
# Generating an OSDD for query q(v1,...,vn) 
* Load syminfer.pl, and transformed file 'outputfile' (in XSB this is `?- [syminfer, 'outputfile'].`)
* Run: `?- compute_osdd(q(v1,....,vn), O).`
* It is assumed that `q(v2,...,vn)` is a ground query and `v1,...,vn`
  are constants from the `values/2` declarations.
* `O` will unify with the computed OSDD
# Visualizing OSDDs
* Generate OSDD `O` and use: `?- writeDot(O, 'dotfile.dot').`
* Install and use `dot` tool to generate PNG/PDF or other format file
* Use: `$ dot -Tpdf dotfile.dot -o dotfile.pdf` to transform to PDF
