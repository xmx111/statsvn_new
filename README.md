# statsvn_new
原来的statsvn 0.7.0不支持svn1.10+, 所以这里追加了兼容性


#使用方法 bat命令
  
    
    SET WORKSP=D:\Projects\workingcopy_dir
    SET STATESVN=D:\Program Files\statsvn-0.7.0
    SET SVNLOG=%STATESVN%\svnlog

    D:  ####注释： 这里指向工程所在盘符
    cd %WORKSP%
    svn log -r {2019-1-1}:{2019-4-1} --xml -v > %SVNLOG%\svn.log

    pause

    D:  ####注释： 这里指向Statsvn所在目录的盘符
    cd %STATESVN%
    java -jar statsvn.jar %SVNLOG%\svn.log %WORKSP% -output-dir %SVNLOG%\result

    pause

