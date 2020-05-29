1.g++方式  
```
{
"cmd": ["g++","-std=c++11", "-Wall", "${file}", "-o", "${file_path}/${file_base_name}"],
"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
"working_dir": "${file_path}",
"selector": "source.c, source.c++",
"encoding":"cp936",
"variants":
[
{
"name": "Run",
"cmd": ["cmd", "/c", "g++", "-std=c++11", "-Wall","${file}", "-o", "${file_path}/${file_base_name}", "&&", "cmd", "/c", "${file_path}/${file_base_name}"]
},
{
"name": "RunInCommand",
"cmd": ["cmd", "/c", "g++", "-std=c++11", "-Wall","${file}", "-o", "${file_path}/${file_base_name}", "&&", "start", "cmd", "/c", "${file_path}/${file_base_name} & echo.&pause"]
}
]
}
```
上面这个当时我把`-std=c++11`放在`"-o"`后面，导致每次build都显示no such dir or document


---
2.clang++方式  
```
{
    "cmd": ["clang++", "${file}","-std=c++11", "-stdlib=libc++", "-o", "${file_path}/${file_base_name}"],
    "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
    "working_dir": "${file_path}",
    "selector": "source.c, source.c++",
    "cmd": ["bash", "-c", "g++ '${file}' -o '${file_path}/${file_base_name}' && open -a Terminal.app '${file_path}/${file_base_name}'"],
    "variants":
    [
        {
            "name": "Run",
            "cmd": ["bash", "-c", "clang++  '${file}' -std=c++11 -stdlib=libc++ -o '${file_path}/${file_base_name}' && '${file_path}/${file_base_name}'"]
        }
]}
```
