* download gnuplot from https://sourceforge.net/projects/gnuplot/files/gnuplot/ 
* install to /opt/sw/tools/... (all software and libraries should be located in this folder)

```
./configure --prefix=/opt/sw/tools/gnuplot-5.0.6 --disable-shared 2>&1 | tee gnuplot_configure_20170620.log
make 2>&1 | tee gnuplot_make_20170620.log
```