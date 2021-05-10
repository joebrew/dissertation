  # dissertation
Dissertation

pdftk 0intro.pdf cat 1-33 output 0introshort.pdf
pdftk 0intro.pdf cat 40-end output 9conclusion.pdf

pdftk 0intro.pdf cat 34 output x1.pdf
pdftk 0intro.pdf cat 35 output x2.pdf
pdftk 0intro.pdf cat 36 output x3.pdf
pdftk 0intro.pdf cat 37 output x4.pdf
pdftk 0intro.pdf cat 38 output x5.pdf
pdftk 0intro.pdf cat 39 output x6.pdf



pdftk 0introshort.pdf x1.pdf 1surveyexperts.pdf x2.pdf 2fdi.pdf x3.pdf 3gambia.pdf x4.pdf 4vaccine.pdf x5.pdf 5cowsquito.pdf x6.pdf 6.pdf 9conclusion.pdf cat output combined.pdf



# pdfjam --outfile newfile.pdf --pagecommand '{Page}' combined.pdf



total=171
gs -o pagenumbers.pdf    \
   -sDEVICE=pdfwrite        \
   -g5950x8420              \
   -c "/Helvetica findfont  \
       6 scalefont setfont \
       1 1  ${total} {      \
       /PageNo exch def     \
       540 10 moveto        \
       (Page ) show         \
       PageNo 3 string cvs  \
       show                 \
       ( of ${total}) show  \
       showpage             \
       } for"
pdftk combined.pdf              \
  multistamp pagenumbers.pdf \
  output pages-numbered.pdf


0intro.pdf           4vaccine.pdf            8gdp.pdf
 1surveyexperts.pdf   5cowsquito.pdf          9externalities.pdf
 2fdi.pdf             6.pdf                  'Academic summary.pdf'
 3gambia.pdf          7syntheticcontrol.pdf   joe_brew_dissertation_v0.pdf
 
 ### VU SPECIFIC STUFF
 pdftk pages-numbered.pdf cat 6-end output temp2.pdf
 pdftk 0intro.pdf cat 1-1 output pretty_title.pdf
 pdftk 0intro.pdf cat 4-4 output acknowledge.pdf
 pdftk 000_vu_title_page.pdf pretty_title.pdf acknowledge.pdf temp2.pdf cat output vu_final.pdf
