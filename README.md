JetBrainsPolishDictionary
=========================


# Package contains files:

 - polish.dic - official aspell polish dict in utf
 - polish.nopl.dic - The some like above but all non ascii chars converted to ascii
	
 - **polish.final.dic** - *Recommend version* - (polish chars + ascii version of words)
 	Sorted and uniq filtered 
 	
 	This version is recommended when You use polish words in functions, class and variables names, but without local characters 




Build with linux command:
========================

	aspell --lang pl dump master | aspell --lang pl expand | tr ' ' '\n' > polish.dic


# Final file 

	iconv -f utf8 -t ascii//TRANSLIT < polish.dic  > polish.nopl.dic

	cat polish.dic polish.nopl.dic | sort -u > polish.final.dic
	

# Problems
  - Current version PhpStorm (8.0 beta) require change in Xmx (to Xmx756m for example) to work correctly with this dictionary on big project
	


## Based on 

    http://lpodolski.com/blog/polish-spell-checking-for-phpstorm/