配置c++支持c++11花了很长时间，网上大多说的不对。

首先配置支持c++编译运行（launch.json和tasks.json文件），这两个文件网上都有配置方法。

下面讲讲网上没有的：

运行的时候发现auto不支持，那就肯定是c++11不支持，网上都说在tasks.json文件的args下加上"-std=c++11"，  
但是还不能运行auto。使用F5调试能够运行auto，但右键run code不行，我想到了是插件code runner没设置支持c++11  
于是去code runner插件下Executor Map下方Edit in setting.json。  
把这个放进去就好了（把原有的去掉）  
```json
{
    "editor.fontSize": 18,
    "terminal.integrated.fontSize": 18,
    "code-runner.runInTerminal": false,//true是在terminal运行
    "C_Cpp.default.cppStandard": "c++11",
    "code-runner.executorMap": {
        "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt -std=c++11 && $dir$fileNameWithoutExt"
    },
    
    "files.associations": {
        "typeinfo": "cpp"
    },
    
    "window.zoomLevel": 1

    /*
    "code-runner.executorMapByFileExtension": {
        "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt -std=c++11 && $dir$fileNameWithoutExt"
    }
    */
    
}
```
还有一个问题，run code插件不支持输入，所以当你要有输入数据的时候，把"code-runner.runInTerminal": false,的false改为true  
这样就是在vs code的terminal上运行。当然如果你要在cmd上显示运行结果，那就去tasks.json上面吧弹出cmd设为true。
