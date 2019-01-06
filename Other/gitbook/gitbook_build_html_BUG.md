# gitbook build 生成的HTML无法跳转问题

由于gitbook版本过高导致生成的html打开后无法跳转章节

gitbook降低版本到 **2.6.7** 就可以了

使用如下命令

`gitbook build --gitbook=2.6.7`

如果遇到：

`Error loading version latest: Error: Cannot find module 'internal/util/types'`  

---
> **将node版本降低:**
- ### linux & ubuntu 环境
    1. 安装node管理 n
        - `sudo npm install -g n`
    2. 降低版本，更新npm
        - `sudo n 6`
    3. 安装npm
        - `sudo npm install npm -g` 
- ### window 环境
    - nvm管理node版本
        - `nvm install 6.16.0`
        - `nvm use 6.16.0`
    - 因为切换了新的node环境需要重新安装gitbook-cli
        - `npm install -g gitbook-cli`

---
- 此时运行gitbook2.6.7的命令即可。  
    - `gitbook build --gitbook=2.6.7`

- 待转换完成后，将npm版本（例如11.11.1）切回来即可,以免影响其他模块
    - linux & ubuntu
        - `sudo n 11.11.1`
    - window
        - `nvm use 你的最新版`

> 虽然可以生成HTML并可以跳转，但是生成的HTML无法使用search功能，因为search-pro插件需要gitbook版本大于或等于3.0才能使用
