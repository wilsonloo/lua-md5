# lua-md5 
封装nginx/src/core/ 里面的md5模块代码

* 使用方法:
```sh
    local md5 = require "md5"
    local result = md5.update("hello world")
    print(result)
```

* linux 下编译只需要修改Makefile
    ```sh
        PREFIX ?=          ../skynet/3rd/lua               #改成你的lua include
        LDFLAGS +=         -shared

        LUA_INCLUDE_DIR ?= $(PREFIX)/
        LUA_LIB_DIR ?=     ../skynet/luaclib/              #改成你要的安装目录
    ```

* window 下编译
    * 需要安装 Mingw64
    * 需要准备 windows版本的 lua5.3 头文件或库（可从 deps/lua-5.3.5_Win64_dllw6_lib.zip 拿去别解压）
    ```makefile
        #改成你的lua include
        PREFIX ?=          C:\\Users\\wilson\\buildstation\\lua-5.3.5_Win64_dllw6_lib\\include\\

        LDFLAGS +=         -shared
        LUA_INCLUDE_DIR ?= $(PREFIX)/
        
        #改成 liblua53.a 所在目录
        LUA_LIB_DIR ?=     C:\\Users\\wilson\\buildstation\\lua-5.3.5_Win64_dllw6_lib\\
    ```
    * 使用make生成 md5.dll
    ```sh
        mingw32-make -f Makefile.mingw64
    ```

联系方式:
e-mail:samule21@163.com
e-mail:myfishlgc@163.com