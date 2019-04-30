1、首先确认该脚本最新为4.0 适用于任何weblogic补丁版本的修复
2、选择 hand(手动) 或 auto(自动) 是根据您是否启动服务来判断的，如果没有启动任何weblogic服务，请选择 hand模式；启动了weblogic服务请选择auto模式
   两种模式解释说明：  
    hand(手动):手工指定 [wls_home]和 [bsu_home] 目录
	auto(自动): 不用指定 脚本自动通过已经启动weblogic进程获取 [wls_home]和 [bsu_home] 目录
3、执行脚本用户统一请用root用户执行，脚本会自动切换weblogic 用户执行操作。（注意：如果用weblogic用户执行，脚本执行进入死循环中）
4、补丁和脚本位置建议都放在/opt目录下，然后按照说明执行
   参数解释：
   [新补丁名] : zip的压缩补丁包解压出来 XXX.jar文件【XXX】或 安装后版本检查【XXX】
   [新wls包名]:官网提供出zip的压缩补丁包
5、执行后请查看日志（/opt/wlspatchxxxxxxxx_log.txt），来验证检查、移除、安装过程是否成功。
6、如果需要脚本在后台执行
   请按照格式 nohup python install_wls_Patch4.0.py [auto|hand] [mode] [...] > nohup.out|tail -f nohup.out &