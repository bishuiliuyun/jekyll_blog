---                                                                                                    
layout:     post                                                                                       
title:      shell之printf                                                     
subtitle:   printf                                                                       
date:       2020-02-23                                                                                 
author:     bishuiliuyun                                                                                         
#header-img: img/post-bg-universe.jpg                                                                   
catalog: true                                                                                          
tags:                                                                                                  
    - Shell                                                                                              
--- 


### printf

```shell
printf "%5s %10s %10s\\n" No Name Mark
printf "%5s %10s %10.2f\\n" 1 Sarath 80.3456
printf "%5s %10s %10.2f\\n" 2 James 90.9989
printf "%5s %10s %10.2f\\n" 3 Jeff 98.7

printf "\\n\\n\\n\\n"

printf "%-5s %-10s %-10s\\n" No Name Mark
printf "%-5s %-10s %-10.2f\\n" 1 Sarath 80.3456
printf "%-5s %-10s %-10.2f\\n" 2 James 90.9989
printf "%-5s %-10s %-10.2f\\n" 3 Jeff 98.7
```
