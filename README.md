vivo
====
解决课件访问跨域问题步骤：
原理：同源策略，将课件和程序放在相同的jboss下面，达到同源目的后即不存在跨域访问的问题了
步骤：
 1：cd /usr/local/jboss-4.2.3/server/default/deploy
 2：ln -s /nas/fastfds/data fds.war #这里的fds.war参数是写死的，不能改
 3：更新lms.war\WEB-INF\classes\com\hanpu\lms\business\library\service\impl\DocServiceImpl.class、lms.war\WEB-INF\classes\com\hanpu\lms\business\course\action\ScormInfoAction.class
 4：ps -ef | grep nginx ，把过滤出来的nginx进程全部杀掉
 5：重启jboss
