源码地址：http://mirrors.ustc.edu.cn/aosp/tools/repo.git

# 使用方法：
1. 使用git clone http://mirrors.ustc.edu.cn/aosp/tools/repo.git 下载源码
2. 修改repo文件,将REPO_URL修改为服务器上repo库所在的地址 gitlab@gitlab.autoio.org:dashboards/git-repo.git
3. 根据模板修改manifest.xml

# manifest.xml模板：
```
<?xml version="1.0" encoding="UTF-8"?>
<manifest>

    <default sync-j="8" remote="autoio" revision="1.5"/>

    <remote fetch="https://source.codeaurora.org/external/imx" name="CAF"/>
    <remote fetch="ssh://gitlab@gitlab.autoio.org" name="autoio"/>

    <project remote="CAF" revision="2f76097309ceb20025af6f0dd853e0f4b641d40a" name="meta-fsl-bsp-release" path="sources/meta-fsl-bsp-release" >
    <project remote="autoio" revision="1.5" name="yocto-grp/meta-sunxi-autoio" path="sources/meta-sunxi-autoio"/>
    <project remote="autoio" revision="1.5" name="yocto-grp/bsp-base" path="sources/base">
        <linkfile dest="README" src="README"/>
    </project>

</manifest>
```
