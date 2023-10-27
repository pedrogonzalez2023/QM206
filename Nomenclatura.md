```python
import numpy as np
import pandas as pd
```


```python
aniones=pd.read_csv("https://raw.githubusercontent.com/pedrogonzalez2023/QM206/main/aniones.csv")
cationes=pd.read_csv("https://raw.githubusercontent.com/pedrogonzalez2023/QM206/main/cationes.csv")
cas=np.array(cationes["simbolo"])
can=np.array(cationes["nombre"])
cac=np.array(cationes["carga"])
anf=np.array(aniones["formula"])
ann=np.array(aniones["nombre"])
anc=np.array(aniones["carga"])
poly=np.array(aniones["poly"])
```


```python
def simplifica(na,nc):
  num=np.array([na,nc])
  m=np.max(num)
  res=num
  for n in np.arange(2,m+1):
    arr=np.mod(num,n)

    if np.sum(arr)==0:
      res=num/n

  return res
simplifica(2,4)
```




    array([1., 2.])




```python
def generaNombre():
    
    na=np.random.randint(0,len(anf))
    nc=np.random.randint(0,len(cas))
    caCarga=cac[nc]
    anCarga=anc[na]
    ns=simplifica(anCarga,caCarga)
    pp=(ns[0]>0 and poly==1)
    formula=cas[nc]+(str(ns[0]) if ns[0]>1 else "")+("(" if ns[1]>1 else "")+  anf[na]+(")"+str(ns[1]) if ns[1]>1 else "")

  
    nombre=ann[na]+" de "+ can[nc]

    return [formula,nombre]

```


```python
for i in range(100):
    cad=generaNombre()
    print(cad)
```

    ['LiBrO3', 'bromato de litio']
    ['NaClO4', 'perclorato de sodio ']
    ['Ag2Se', 'seleniuro de plata ']
    ['Cr2(Se)3', 'seleniuro de cromo (II)']
    ['Fe(ClO2)2', 'clorito de hierro (III)']
    ['CsIO3', 'yodato de cesio ']
    ['AgH2PO4', 'dihidr¢geno fosfato de plata ']
    ['Ca(BrO4)2', 'perbromato de calcio ']
    ['HCl', 'cloruro de acido']
    ['NH42HPO4', 'hidr¢geno fosfato de amonio ']
    ['Cr(IO4)2', 'peryodato de cromo (II)']
    ['Zn(F)2', 'fluoruro de zinc ']
    ['Na2Se', 'seleniuro de sodio ']
    ['Cu2SO4', 'sulfato de cobre (I)']
    ['NaClO2', 'clorito de sodio ']
    ['Fe(BrO2)2', 'bromito de hierro (II)']
    ['PbSeO4', 'selenato de plomo (II)']
    ['Ag2CrO4', 'cromato de plata ']
    ['Al2(SO3)3', 'sulfito de aluminio ']
    ['HClO4', 'perclorato de acido']
    ['HNO2', 'nitrito de acido']
    ['AgCH3COO', 'acetato de plata ']
    ['LiNO2', 'nitrito de litio']
    ['Cr2(O2)3', 'peróxido de cromo (II)']
    ['Cr(HSO3)3', 'hidr¢geno sulfito de cromo (II)']
    ['CsClO2', 'clorito de cesio ']
    ['Fe(BrO2)2', 'bromito de hierro (II)']
    ['Sr(HSO4)2', 'hidr¢geno sulfato de estroncio ']
    ['Fe(NO2)2', 'nitrito de hierro (III)']
    ['Cr(ClO)3', 'hipoclorito de cromo (II)']
    ['LiBr', 'bromuro de litio']
    ['Pb(ClO4)2', 'perclorato de plomo (II)']
    ['Rb2CO3', 'carbonato de rubidio ']
    ['Ba(IO)2', 'hipoyodito de Ion bario ']
    ['Cr(I)3', 'yoduro de cromo (II)']
    ['Cr(F)3', 'fluoruro de cromo (II)']
    ['Cs2SO4', 'sulfato de cesio ']
    ['Li2HPO4', 'hidr¢geno fosfato de litio']
    ['Ba(I)2', 'yoduro de Ion bario ']
    ['CuH2PO4', 'dihidr¢geno fosfato de cobre (I)']
    ['HBrO3', 'bromato de acido']
    ['Sr(Cl)2', 'cloruro de estroncio ']
    ['Ca(SCN)2', 'tiocianato de calcio ']
    ['Rb2S', 'sulfuro de rubidio ']
    ['Ba(HCO3)2', 'hidr¢geno carbonato de Ion bario ']
    ['Sn(Cl)2', 'cloruro de esta¤o (II)  ']
    ['CuMnO4', 'permanganato de cobre (I)']
    ['SrHPO4', 'hidr¢geno fosfato de estroncio ']
    ['H2Se', 'seleniuro de acido']
    ['Sn(HSO3)2', 'hidr¢geno sulfito de esta¤o (II)  ']
    ['Fe(IO2)2', 'yodito de hierro (III)']
    ['Ag2SeO4', 'selenato de plata ']
    ['NaOH', 'hidr¢xido  de sodio ']
    ['Ag2SeO3', 'selenito de plata ']
    ['Ba(MnO4)2', 'permanganato de Ion bario ']
    ['SrCrO4', 'cromato de estroncio ']
    ['Fe(OH)2', 'hidr¢xido  de hierro (II)']
    ['NaF', 'fluoruro de sodio ']
    ['Zn(IO2)2', 'yodito de zinc ']
    ['Cr(ClO2)2', 'clorito de cromo (II)']
    ['CuHCO3', 'hidr¢geno carbonato de cobre (I)']
    ['Zn(BrO3)2', 'bromato de zinc ']
    ['Ag2O', 'óxido de plata ']
    ['Cr2(CrO4)3', 'cromato de cromo (II)']
    ['LiF', 'fluoruro de litio']
    ['NH4BrO4', 'perbromato de amonio ']
    ['Ba(BrO3)2', 'bromato de Ion bario ']
    ['CuSeO3', 'selenito de cobre (II)']
    ['Pb(CN)2', 'cianuro de plomo (II)']
    ['Cs2SeO4', 'selenato de cesio ']
    ['Cs3PO4', 'fosfato de cesio ']
    ['RbIO2', 'yodito de rubidio ']
    ['ZnO', 'óxido de zinc ']
    ['NaIO2', 'yodito de sodio ']
    ['ZnHPO4', 'hidr¢geno fosfato de zinc ']
    ['K3PO4', 'fosfato de potasio ']
    ['FeS', 'sulfuro de hierro (II)']
    ['Al(HSO4)3', 'hidr¢geno sulfato de aluminio ']
    ['CsI', 'yoduro de cesio ']
    ['Ba(Br)2', 'bromuro de Ion bario ']
    ['Ca(I)2', 'yoduro de calcio ']
    ['AgHSO4', 'hidr¢geno sulfato de plata ']
    ['FeSO4', 'sulfato de hierro (III)']
    ['HIO', 'hipoyodito de acido']
    ['Cr(Br)2', 'bromuro de cromo (II)']
    ['Al(HSO3)3', 'hidr¢geno sulfito de aluminio ']
    ['Rb3N', 'nitruro de rubidio ']
    ['ZnSe', 'seleniuro de zinc ']
    ['Ag2CrO4', 'cromato de plata ']
    ['SrCr2O7', 'dicromato de estroncio ']
    ['Cr(ClO)2', 'hipoclorito de cromo (II)']
    ['RbCN', 'cianuro de rubidio ']
    ['NH4BrO4', 'perbromato de amonio ']
    ['BaCrO4', 'cromato de Ion bario ']
    ['Fe(BrO4)2', 'perbromato de hierro (III)']
    ['Ca(ClO2)2', 'clorito de calcio ']
    ['Sn(BrO4)2', 'perbromato de esta¤o (II)  ']
    ['CsClO', 'hipoclorito de cesio ']
    ['CuBrO4', 'perbromato de cobre (I)']
    ['NH42O', 'óxido de amonio ']
    


```python

```


```python

```
