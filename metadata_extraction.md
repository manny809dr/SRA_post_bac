# Bioconductor


```r
library(SRAdb)
```

```
Loading required package: RSQLite
```

```
Warning: package 'RSQLite' was built under R version 3.3.3
```

```
Loading required package: graph
```

```
Loading required package: BiocGenerics
```

```
Loading required package: parallel
```

```

Attaching package: 'BiocGenerics'
```

```
The following objects are masked from 'package:parallel':

    clusterApply, clusterApplyLB, clusterCall, clusterEvalQ,
    clusterExport, clusterMap, parApply, parCapply, parLapply,
    parLapplyLB, parRapply, parSapply, parSapplyLB
```

```
The following objects are masked from 'package:stats':

    IQR, mad, xtabs
```

```
The following objects are masked from 'package:base':

    anyDuplicated, append, as.data.frame, cbind, colnames,
    do.call, duplicated, eval, evalq, Filter, Find, get, grep,
    grepl, intersect, is.unsorted, lapply, lengths, Map, mapply,
    match, mget, order, paste, pmax, pmax.int, pmin, pmin.int,
    Position, rank, rbind, Reduce, rownames, sapply, setdiff,
    sort, table, tapply, union, unique, unsplit, which, which.max,
    which.min
```

```
Loading required package: RCurl
```

```
Warning: package 'RCurl' was built under R version 3.3.3
```

```
Loading required package: bitops
```

```
Setting options('download.file.method.GEOquery'='auto')
```

```
Setting options('GEOquery.inmemory.gpl'=FALSE)
```

```r
sqlfile <-'SRAmetadb.sqlite'
if(!file.exists('SRAmetadb.sqlite'
)) sqlfile <<- getSRAdbFile()
sra_con <- dbConnect(SQLite(),sqlfile)
```

## Metadata for SRA datasets

```r
x=1293541:1293641
str=sprintf("SRR%d",x)
a <- listSRAfile (in_acc = c(str), sra_con = sra_con, fileType = 'sra', srcType='fasp')
a
```

```
           run     study    sample experiment
1   SRR1293541 SRP042012 SRS607446  SRX543540
2   SRR1293542 SRP035648 SRS572592  SRX548483
3   SRR1293543 SRP035648 SRS573739  SRX548484
4   SRR1293544 SRP035648 SRS570610  SRX548485
5   SRR1293545 SRP035648 SRS575399  SRX548486
6   SRR1293546 SRP035648 SRS570082  SRX548487
7   SRR1293547 SRP035648 SRS570370  SRX548488
8   SRR1293548 SRP035648 SRS570242  SRX548489
9   SRR1293549 SRP042012 SRS608811  SRX544917
10  SRR1293550 SRP040795 SRS616371  SRX548491
11  SRR1293551 SRP035648 SRS573191  SRX548492
12  SRR1293552 SRP035648 SRS572872  SRX548490
13  SRR1293553 SRP035648 SRS574444  SRX548493
14  SRR1293554 SRP035648 SRS575493  SRX548494
15  SRR1293555 SRP035648 SRS571166  SRX548495
16  SRR1293556 SRP035648 SRS571230  SRX548496
17  SRR1293557 SRP035648 SRS571385  SRX548497
18  SRR1293558 SRP035648 SRS571077  SRX548498
19  SRR1293559 SRP042012 SRS608795  SRX544902
20  SRR1293560 SRP040795 SRS616372  SRX548499
21  SRR1293561 SRP040795 SRS616373  SRX548500
22  SRR1293562 SRP040795 SRS616374  SRX548501
23  SRR1293563 SRP035648 SRS574318  SRX548502
24  SRR1293564 SRP035648 SRS574990  SRX548503
25  SRR1293565 SRP035648 SRS571230  SRX548496
26  SRR1293566 SRP042012 SRS607611  SRX543709
27  SRR1293567 SRP042012 SRS608803  SRX544910
28  SRR1293568 SRP040795 SRS616335  SRX548078
29  SRR1293569 SRP040795 SRS616231  SRX547972
30  SRR1293570 SRP040795 SRS586280  SRX507328
31  SRR1293571 SRP035648 SRS572388  SRX548504
32  SRR1293572 SRP035648 SRS570773  SRX548505
33  SRR1293573 SRP035648 SRS574140  SRX548506
34  SRR1293574 SRP035648 SRS574606  SRX548507
35  SRR1293575 SRP035648 SRS574312  SRX548508
36  SRR1293576 SRP042012 SRS608765  SRX544869
37  SRR1293577 SRP045025 SRS616375  SRX548509
38  SRR1293578 SRP035648 SRS573128  SRX548510
39  SRR1293579 SRP035648 SRS573161  SRX548511
40  SRR1293580 SRP035648 SRS571266  SRX548512
41  SRR1293581 SRP035648 SRS573728  SRX548513
42  SRR1293582 SRP035648 SRS573184  SRX548514
43  SRR1293583 SRP035648 SRS570056  SRX548515
44  SRR1293584 SRP035648 SRS570052  SRX548516
45  SRR1293585 SRP042012 SRS607609  SRX543705
46  SRR1293586 SRP042012 SRS607464  SRX543558
47  SRR1293587 SRP035648 SRS575356  SRX548517
48  SRR1293588 SRP035648 SRS574730  SRX516570
49  SRR1293589 SRP035648 SRS066147  SRX548518
50  SRR1293590 SRP035648 SRS574297  SRX548519
51  SRR1293591 SRP035648 SRS570342  SRX548520
52  SRR1293592 SRP035648 SRS572814  SRX548521
53  SRR1293593 SRP035648 SRS573477  SRX548522
54  SRR1293594 SRP035648 SRS570514  SRX503525
55  SRR1293595 SRP035648 SRS570423  SRX548523
56  SRR1293596 SRP042012 SRS608804  SRX544911
57  SRR1293597 SRP044993 SRS616376  SRX548524
58  SRR1293598 SRP035648 SRS574800  SRX548525
59  SRR1293599 SRP035648 SRS572429  SRX548526
60  SRR1293600 SRP035648 SRS575674  SRX548527
61  SRR1293601 SRP035648 SRS570135  SRX548528
62  SRR1293602 SRP035648 SRS574533  SRX548529
63  SRR1293603 SRP035648 SRS575217  SRX548530
64  SRR1293604 SRP035648 SRS575107  SRX548531
65  SRR1293605 SRP035648 SRS574866  SRX548532
66  SRR1293606 SRP042012 SRS608794  SRX544901
67  SRR1293607 SRP042012 SRS607443  SRX543537
68  SRR1293608 SRP040795 SRS586258  SRX507299
69  SRR1293609 SRP040795 SRS616236  SRX547977
70  SRR1293610 SRP040795 SRS616377  SRX548533
71  SRR1293611 SRP040795 SRS586171  SRX507205
72  SRR1293612 SRP035648 SRS572348  SRX503520
73  SRR1293613 SRP035648 SRS573999  SRX548534
74  SRR1293614 SRP035648 SRS574203  SRX548535
75  SRR1293615 SRP042012 SRS608804  SRX544911
76  SRR1293616 SRP040795 SRS616327  SRX548070
77  SRR1293617 SRP035648 SRS572991  SRX548536
78  SRR1293618 SRP035648 SRS572592  SRX548483
79  SRR1293619 SRP035648 SRS572782  SRX548537
80  SRR1293620 SRP035648 SRS575333  SRX548538
81  SRR1293621 SRP035648 SRS570494  SRX548539
82  SRR1293622 SRP042012 SRS607447  SRX543555
83  SRR1293623 SRP042012 SRS607415  SRX543386
84  SRR1293624 SRP040795 SRS616378  SRX548540
85  SRR1293625 SRP035648 SRS573580  SRX548541
86  SRR1293626 SRP035648 SRS570610  SRX548485
87  SRR1293627 SRP035648 SRS570042  SRX548542
88  SRR1293628 SRP042012 SRS608787  SRX544893
89  SRR1293629 SRP045035 SRS616379  SRX548543
90  SRR1293630 SRP035648 SRS572388  SRX548504
91  SRR1293631 SRP035648 SRS572206  SRX513199
92  SRR1293632 SRP035648 SRS574017  SRX548544
93  SRR1293633 SRP035648 SRS572905  SRX548545
94  SRR1293634 SRP042012 SRS607417  SRX543471
95  SRR1293635 SRP042012 SRS607433  SRX543527
96  SRR1293636 SRP040795 SRS616344  SRX548087
97  SRR1293637 SRP035648 SRS571214  SRX548546
98  SRR1293638 SRP035648 SRS571266  SRX548512
99  SRR1293639 SRP035648 SRS575481  SRX548547
100 SRR1293640 SRP042012 SRS608784  SRX544891
101 SRR1293641 SRP042012 SRS608798  SRX544905
                                                                                                                  fasp
1   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543540/SRR1293541/SRR1293541.sra
2   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548483/SRR1293542/SRR1293542.sra
3   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548484/SRR1293543/SRR1293543.sra
4   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548485/SRR1293544/SRR1293544.sra
5   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548486/SRR1293545/SRR1293545.sra
6   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548487/SRR1293546/SRR1293546.sra
7   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548488/SRR1293547/SRR1293547.sra
8   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548489/SRR1293548/SRR1293548.sra
9   anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544917/SRR1293549/SRR1293549.sra
10  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548491/SRR1293550/SRR1293550.sra
11  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548492/SRR1293551/SRR1293551.sra
12  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548490/SRR1293552/SRR1293552.sra
13  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548493/SRR1293553/SRR1293553.sra
14  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548494/SRR1293554/SRR1293554.sra
15  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548495/SRR1293555/SRR1293555.sra
16  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548496/SRR1293556/SRR1293556.sra
17  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548497/SRR1293557/SRR1293557.sra
18  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548498/SRR1293558/SRR1293558.sra
19  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544902/SRR1293559/SRR1293559.sra
20  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548499/SRR1293560/SRR1293560.sra
21  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548500/SRR1293561/SRR1293561.sra
22  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548501/SRR1293562/SRR1293562.sra
23  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548502/SRR1293563/SRR1293563.sra
24  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548503/SRR1293564/SRR1293564.sra
25  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548496/SRR1293565/SRR1293565.sra
26  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543709/SRR1293566/SRR1293566.sra
27  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544910/SRR1293567/SRR1293567.sra
28  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548078/SRR1293568/SRR1293568.sra
29  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX547/SRX547972/SRR1293569/SRR1293569.sra
30  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX507/SRX507328/SRR1293570/SRR1293570.sra
31  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548504/SRR1293571/SRR1293571.sra
32  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548505/SRR1293572/SRR1293572.sra
33  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548506/SRR1293573/SRR1293573.sra
34  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548507/SRR1293574/SRR1293574.sra
35  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548508/SRR1293575/SRR1293575.sra
36  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544869/SRR1293576/SRR1293576.sra
37  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548509/SRR1293577/SRR1293577.sra
38  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548510/SRR1293578/SRR1293578.sra
39  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548511/SRR1293579/SRR1293579.sra
40  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548512/SRR1293580/SRR1293580.sra
41  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548513/SRR1293581/SRR1293581.sra
42  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548514/SRR1293582/SRR1293582.sra
43  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548515/SRR1293583/SRR1293583.sra
44  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548516/SRR1293584/SRR1293584.sra
45  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543705/SRR1293585/SRR1293585.sra
46  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543558/SRR1293586/SRR1293586.sra
47  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548517/SRR1293587/SRR1293587.sra
48  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX516/SRX516570/SRR1293588/SRR1293588.sra
49  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548518/SRR1293589/SRR1293589.sra
50  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548519/SRR1293590/SRR1293590.sra
51  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548520/SRR1293591/SRR1293591.sra
52  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548521/SRR1293592/SRR1293592.sra
53  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548522/SRR1293593/SRR1293593.sra
54  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX503/SRX503525/SRR1293594/SRR1293594.sra
55  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548523/SRR1293595/SRR1293595.sra
56  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544911/SRR1293596/SRR1293596.sra
57  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548524/SRR1293597/SRR1293597.sra
58  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548525/SRR1293598/SRR1293598.sra
59  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548526/SRR1293599/SRR1293599.sra
60  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548527/SRR1293600/SRR1293600.sra
61  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548528/SRR1293601/SRR1293601.sra
62  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548529/SRR1293602/SRR1293602.sra
63  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548530/SRR1293603/SRR1293603.sra
64  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548531/SRR1293604/SRR1293604.sra
65  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548532/SRR1293605/SRR1293605.sra
66  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544901/SRR1293606/SRR1293606.sra
67  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543537/SRR1293607/SRR1293607.sra
68  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX507/SRX507299/SRR1293608/SRR1293608.sra
69  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX547/SRX547977/SRR1293609/SRR1293609.sra
70  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548533/SRR1293610/SRR1293610.sra
71  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX507/SRX507205/SRR1293611/SRR1293611.sra
72  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX503/SRX503520/SRR1293612/SRR1293612.sra
73  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548534/SRR1293613/SRR1293613.sra
74  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548535/SRR1293614/SRR1293614.sra
75  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544911/SRR1293615/SRR1293615.sra
76  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548070/SRR1293616/SRR1293616.sra
77  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548536/SRR1293617/SRR1293617.sra
78  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548483/SRR1293618/SRR1293618.sra
79  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548537/SRR1293619/SRR1293619.sra
80  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548538/SRR1293620/SRR1293620.sra
81  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548539/SRR1293621/SRR1293621.sra
82  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543555/SRR1293622/SRR1293622.sra
83  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543386/SRR1293623/SRR1293623.sra
84  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548540/SRR1293624/SRR1293624.sra
85  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548541/SRR1293625/SRR1293625.sra
86  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548485/SRR1293626/SRR1293626.sra
87  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548542/SRR1293627/SRR1293627.sra
88  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544893/SRR1293628/SRR1293628.sra
89  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548543/SRR1293629/SRR1293629.sra
90  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548504/SRR1293630/SRR1293630.sra
91  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX513/SRX513199/SRR1293631/SRR1293631.sra
92  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548544/SRR1293632/SRR1293632.sra
93  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548545/SRR1293633/SRR1293633.sra
94  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543471/SRR1293634/SRR1293634.sra
95  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX543/SRX543527/SRR1293635/SRR1293635.sra
96  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548087/SRR1293636/SRR1293636.sra
97  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548546/SRR1293637/SRR1293637.sra
98  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548512/SRR1293638/SRR1293638.sra
99  anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX548/SRX548547/SRR1293639/SRR1293639.sra
100 anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544891/SRR1293640/SRR1293640.sra
101 anonftp@ftp-trace.ncbi.nlm.nih.gov:/sra/sra-instant/reads/ByExp/sra/SRX/SRX544/SRX544905/SRR1293641/SRR1293641.sra
```

