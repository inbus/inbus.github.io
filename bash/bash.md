#Bash

##Convert a string to lower or upper case in Bash
>###To lowercase
>
>```
>$ string="A FEW WORDS"
>$ echo "${string,}"
>a FEW WORDS
>$ echo "${string,,}"
>a few words
>$ echo "${string,,[AEIUO]}"
>a FeW WoRDS
>
>$ string="A Few Words"
>$ declare -l string
>$ string=$string; echo "$string"
>a few words
>```
>###To uppercase
>
>```
>$ string="a few words"
>$ echo "${string^}"
>A few words
>$ echo "${string^^}"
>A FEW WORDS
>$ echo "${string^^[aeiou]}"
>A fEw wOrds
>
>$ string="A Few Words"
>$ declare -u string
>$ string=$string; echo "$string"
>A FEW WORDS
>```
>###Toggle (undocumented, but optionally configurable at compile time)
>
>```
>$ string="A Few Words"
>$ echo "${string~~}"
>a fEW wORDS
>$ string="A FEW WORDS"
>$ echo "${string~}"
>a FEW WORDS
>$ string="a few words"
>$ echo "${string~}"
>A few words
>```
>###Capitalize (undocumented, but optionally configurable at compile time)
>
>```
>$ string="a few words"
>$ declare -c string
>$ string=$string
>$ echo "$string"
>A few words
>```
>###Title case:
>
>```
>$ string="a few words"
>$ string=($string)
>$ string="${string[@]^}"
>$ echo "$string"
>A Few Words
>
>$ declare -c string
>$ string=(a few words)
>$ echo "${string[@]}"
>A Few Words
>
>$ string="a FeW WOrdS"
>$ string=${string,,}
>$ string=${string~}
>$ echo "$string"
>A few words
>```

