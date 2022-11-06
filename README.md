## ExploringJVMviaVisualVM
### Description
Take this <a href="https://github.com/Arsennikum/jvm-visualvm-experience">project</a> and research memory usage through VisualVM.

You need:
1. Take screenshots of the graphs and mark on them with a simple graphic editor and text, at which moments what actions of the program took place.
2. Mark on the timeline of graphs each line that the program has output to the console and explain it in your own words in the text

### Realization
#### Output data after starting the program:

![IDEA](https://user-images.githubusercontent.com/63547457/200165301-3adc6759-e1bf-4d74-a6f2-a7b6a0ecd285.png)
#### 
1-2: 
Classes: загрузка 529 классов io.vertx и вспомогательных, так как число классов увеличилось на 814. 
Metaspace: увеличение Metaspace до 7,5 МБ, используется 6,86 МБ
Heap: увеличение размера используемого пространства с 14 МБ до 34 МБ. При этом размер выделенной памяти не меняется и равен 128 МБ.
3-4:
Classes: 2081 классов io.netty. Однако по выходным данным работы программы должно было добавиться 2117 классов. Видимо, 36 классов были добавлены ранее.
Metaspace: увеличение Metaspace до 11,63 МБ, используется 11,09 МБ
Heap: срабатывание Garbage Collector (сборщика мусора), после чего объем используемой памяти сначала уменьшается. Однако затем оно увеличивается до 69,49 МБ.
При этом размер выделенной памяти не меняется и равен 128 МБ.
