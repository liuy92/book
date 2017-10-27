# hive语句

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.返回值

if \[ ! $? -eq 0 \] ;then

   echo "vb\_rpt\_middle\_tea\_month\_visours\_first\_do execute failed !!!!"

   exit 1

fi

判断hdfs文件是否存在

hadoop fs -test -e "/report/sqoop/teacher\_class\_homework\_day/${logday}/"

if \[ ! $? -eq 0 \] ;then

   echo "file not exist!!!!"

   exit 1

fi



logday=$1

current\_time=$\(date '+%Y-%m-%d %H:%M:%S'\)

if \[ $\# == 0 \];then

 logday=$\(date +%Y-%m-%d\)

fi



date=$1

date=\`date +%Y-%m-%d -d " 1 days ago $date"\`

n=\`date -d "2017-07-01" +%w\`

week=\`date +%Y-%m-%d -d "${n} days ago $date"\`

dateofmonth=\`date +%Y-%m -d " $date"\`



task\_start\_time=$\(date "+%Y-%m-%d %H:%M:%S"\)

task\_end\_Time=$\(date "+%Y-%m-%d %H:%M:%S"\)

echo "task\_start\_time:==&gt;"+$task\_start\_time

echo "task\_end\_Time:==&gt;"+$task\_end\_Time





--文件是否存在

hadoop fs -test -e "/report/vbawork/vbawork\_report/rpt\_middle\_tea\_grade\_month\_visours\_first\_do\_view/" \|\| exit 88



from\_unixtime\(unix\_timestamp\(\),'yyyy-MM-dd HH:mm:ss'\)



--查找

find . -name "\*.sh" \|xargs grep -i vb\_primary\_teacher\_school\_acitve\_day\_tmp



--结束任务

yarn application -kill application\_1459415708938\_273283





---建表语句

use vbawork\_business;

create EXTERNAL table vb\_rpt\_teacher\_level\_integral\_month\(

ttl\_level bigint

\) comment '注释：XXX' 

partitioned by \(month string\)

ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.lazy.LazySimpleSerDe'

 WITH SERDEPROPERTIES\(

 'field.delim'='\t',

 'escape.delim'='\\'

 \) STORED AS INPUTFORMAT "com.hadoop.mapred.DeprecatedLzoTextInputFormat"

 OUTPUTFORMAT "org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat"

 location '/report/vbawork/vbawork\_business/vb\_rpt\_teacher\_level\_integral\_month/'; 





从hive导入oracle

sqoop export --table r\_christmas\_hw\_day\_bk1  --columns 'createday,stu\_comhw\_count\_all,stu\_sum\_all,stu\_count\_all,stu\_comhw\_num\_pc,stu\_sum\_pc,stu\_count\_pc,stu\_comhw\_num\_app,stu\_sum\_app,stu\_count\_app,tea\_assign\_hw\_count\_all,tea\_count\_all,tea\_sum\_all,tea\_assign\_hw\_count\_pc,tea\_count\_pc,tea\_sum\_pc,tea\_assign\_hw\_count\_app,tea\_count\_app,tea\_sum\_app,parent\_use\_count\_all,parent\_flowers\_count\_all,parent\_count\_all,parent\_sum\_all,parent\_class\_count\_all,parent\_use\_count\_wechat,parent\_flowers\_count\_wechat,parent\_count\_wechat,parent\_sum\_wechat,parent\_class\_count\_wechat,parent\_use\_count\_app,parent\_flowers\_count\_app,parent\_count\_app,parent\_sum\_app,parent\_class\_count\_app,tea\_hw\_count\_all,tea\_hw\_count\_pc,tea\_hw\_count\_app' -connect jdbc:oracle:thin:@10.0.1.156:1521:orcl --username vba --password vba --export-dir /report/r\_christmas\_hw\_day\_view --input-fields-terminated-by '\001' --input-lines-terminated-by '\n' --direct



导出csv以逗号分隔，hive表也以逗号分隔

  LOAD DATA LOCAL INPATH '/data/hadoop/workspace/report\_user/shuyan.yuan/teacher\_active/tempt\_test\_20160203.csv' OVERWRITE INTO TABLE tmp.tempt\_test; 

LOAD DATA LOCAL INPATH '/data/hadoop/workspace/report\_user/shuyan.yuan/teacher\_active/teacher\_homework\_used\_20160203.csv' OVERWRITE INTO TABLE vbawork\_business.vb\_teacher\_status partition\(dt='2016-02-03'\); 

导入csv，txt等文本文件，创建表时的存储格式不能是压缩格式的





msck repair table vbawork\_business.vb\_growing\_world\_log\_day;



ALTER TABLE vb\_student\_effective\_order\_status ADD  PARTITION \(dt='2016-05-29'\) LOCATION '/report/vbawork/vbawork\_business/vb\_student\_effective\_order\_status/dt=2016-05-29'; 





从oracle导入hive

sqoop import --hive-import --connect jdbc:oracle:thin:@10.6.0.89:1521:orcl --username vba --password vba --verbose -m 1 --table KNOWLEDGE\_PIONT\_TS --hive-database tmp --hive-table r\_school\_status\_20161011



查看

hadoop fs -cat /report/r\_sms\_month\_20160106/\*  \| more

 

修改字段

	ALTER TABLE vb\_middle\_teacher\_homework\_day   

		  CHANGE  primary\_jounior\_school p\_or\_j\_school string   

     

	 

加字段	 

ALTER TABLE rpt\_christmas\_hw\_integral\_day   

      add COLUMNS \(stu\_comhw\_times\_all bigint,stu\_comhw\_times\_pc bigint,stu\_comhw\_times\_app bigint \)

	  

删除分区

ALTER TABLE rpt\_christmas\_hw\_integral\_day\_tea DROP IF EXISTS PARTITION \(dt='2016-01-15'\);



ALTER TABLE rpt\_christmas\_hw\_integral\_day   

      replace COLUMNS \(hwandexam\_num ,exam\_num \)



ALTER TABLE vb\_r\_middle\_teacher\_active\_day\_cp RENAME TO vb\_r\_middle\_teacher\_active\_day;



cast\(substr\(regexp\_replace\('2017-07-01','-',''\),1,6\)as bigint\) 



--查看建表相关语句

show create table  vbawork\_business.vb\_student\_homework\_day\_oracle\_bk;



show partitions table\_name partition\(dt='2016-01-15'\)



方法：pmod\(datediff\('\#date\#', '2012-01-01'\), 7\)  

返回值：int

说明：1、返回值为“0-6”\(“0-6”分别表示“星期日-星期六”）;2、需要注意pmod和 datediff 函数的使用方法.





\# hive parameter

set mapred.child.java.opts=-Xmx900m;

set mapreduce.reduce.memory.mb=8048 ;

set mapreduce.reduce.java.opts='-Xmx8048M';

set mapreduce.map.memory.mb=1024;

set mapreduce.map.java.opts='-Xmx900M';

set mapred.child.map.java.opts='-Xmx900M';

set mapreduce.reduce.memory.mb=8048;

set mapreduce.reduce.java.opts='-Xmx8048M';



set mapreduce.job.name=rpt\_student\_region\_total\_day; \#任务名，强烈建议设置

set mapred.output.compress=true;

set hive.exec.compress.output=true;

set mapred.output.compression.codec=com.hadoop.compression.lzo.LzopCodec ;

set io.compression.codecs=com.hadoop.compression.lzo.LzopCodec ;

set hive.exec.dynamic.partition.mode=nonstrict; \#开启动态分区时设置

set hive.exec.dynamic.partition=true;

set hive.exec.max.dynamic.partitions.pernode=2000;

set hive.exec.max.dynamic.partitions=2000;

set hive.auto.convert.join=false;

set mapreduce.job.reduces=20; \#reduces个数。设置后会影响生成的文件个数

set hive.exec.parallel=true; \#需要并行计算时设置，与下行参数配合

set hive.exec.parallel.thread.number=1; \#并行度

set hive.cli.print.header=true;\#查询结果显示字段名







add jar /opt/develop/udfs/UDFs.jar;

create temporary function transJie AS 'zuoye.bigdata.hive.TransJie';







json\_tuple  json解析



lateral view  行转列





	







select id,

   createtime,

   get\_json\_object\(smsmessage,'$.smsContent'\) smsContent,

   get\_json\_object\(smsmessage,'$.type'\) type,

   get\_json\_object\(smsmessage,'$.mobile'\) mobile,

   get\_json\_object\(smsmessage,'$.sms\_type'\) sms\_type,

   get\_json\_object\(smsmessage,'$.sendresult'\) sendresult,

   get\_json\_object\(smsmessage,'$.gatewayresponse'\) gatewayresponse,

   get\_json\_object\(smsmessage,'$.gatewaytype'\) gatewaytype

 from fdm.fdm\_mongo\_vox\_sms\_message\_chain where dp='ACTIVE' and substr\(createtime,1,7\)='2015-12'

 

 ALTER TABLE rpt\_english\_student\_homework\_day DROP IF EXISTS PARTITION \(dt='2015-12-30'\);

 

---hive导数据 

 hive -S  -e "select \* from vbawork\_business.vb\_teacher\_homework\_day where dt='2016-01-19' and type\_flag ='ALL'" &gt; /tmp/test\_teacher1.txt





--oracle导数据中文乱码问题处理

在windows上set NLS\_LANG

查询数据库字符集：select property\_value from database\_properties where property\_name like 'NLS\_CHAR%';

比如查询结果是：ZHS16GBK

那你在sqlplus之前要设置：export NLS\_LANG=AMERICAN\_AMERICA.AL32UTF8

然后再登录sqlplus用spool生成数据

 

 

---oracle导数据 

set colsep ,  

set feedback off  

set heading off  

set trimout off  

spool  /tmp/r\_student\_status\_new\_tt.csv 

select '' \|\| user\_id \|\| ',' \|\| min\_auth\_hw\_day \|\| ',' \|\| real\_min\_day \|\| ',' \|\| real\_max\_day \|\|  ''  from r\_Student\_Status;  

spool off  

exit  





相关参数

set pagesize 0

set long 90000

set feedback off

set echo off

set linesize 800









----python脚本删除oracle数据

可以用了，/data/hadoop/workspace/report\_user/vbawork/udf/dao\_oracle.py



清空表：python /data/hadoop/workspace/report\_user/vbawork/udf/dao\_oracle.py -p truncate -t r\_teacher\_status1

删数据：python /data/hadoop/workspace/report\_user/vbawork/udf/dao\_oracle.py -p delete -t english\_tea\_hw\_day\_hive -c createday -d 2016-02-04

或者

python dao\_oracle.py -t english\_tea\_hw\_day\_hive -c createday -d 2016-02-04

日期带不带"-"都行



python /data/hadoop/workspace/report\_user/vbawork/udf/dao\_mongo.py -d vox-schoolmaster -t vox\_school\_situtation -c dt -b 201609 -e 201609

python /data/hadoop/workspace/report\_user/vbawork/udf/dao\_mongo.py -d vox-schoolmaster -t vox\_class\_study\_situtation -p truncate







 rm -rf \*.java

    

 

------过滤文件中的空行输出

 cat teacher\_homework\_used20160229\_1.txt \| awk '{if\($0 !~/^$/\) print $0}' &gt;teacher\_invite\_flag\_20160307\_cp.txt



 awk '{if\(NF&gt;0\)print $0}' test.txt

 

 

1.压缩命令：

　　命令格式：tar  -zcvf   压缩文件名.tar.gz   被压缩文件名

      可先切换到当前目录下。压缩文件名和被压缩文件名都可加入路径。



2.解压缩命令：

　　命令格式：tar  -zxvf   压缩文件名.tar.gz



gunzip filename.gz



gzip -d filename.gz







sed -i '1d' integral\_ts.txt 

sed -i '$d' integral\_ts.txt 

wc -l integral\_ts.txt 





----跨服务器导文件--------

 scp integral\_ts.gz  report\_user@10.0.1.157:/data/hadoop/workspace/report\_user/shuyan.yuan/

 

 

 --上传

  rz -be  files   

 

 

 ----oracle 取中文周

  to\_char\(to\_date\(t.createday, 'yyyyMMdd'\), 'day','NLS\_DATE\_LANGUAGE=''SIMPLIFIED CHINESE'''\) week,

  

  

window.location.href="";



