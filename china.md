# ���Ľ���

Golangȫ�Զ�����ѷȫ���ֲ�ʽ���棨�������ձ����¹���Ӣ����

�����̨�������������̨�������������������������������IP�����ģ��Ͷ������л�ģ�飬���redis��mysql���зֲ�ʽ�߲���ץȡ�ձ�/Ӣ��/����/�¹�����ѷ��Ʒ���ݣ�ʵ��IP�ص��������أ����ݿ����ӵ������ƣ���д���룩�ȹ��ܣ�������Dashboard��̨������ɸѡ��Ʒ������excel�Ͳ鿴��Ʒ��ʷ����/�۸�ȹ켣������crontab��ʱҹ�俪��������IP�Զ�ѭ�����롣����߶��Զ�������ά�ɱ��ϵͣ�ÿ���м��������ݲ����������������벢��Դ��

���������������ѷ������Ȼ���ܣ���������[https://www.github.com/hunterhug/GoSpider](https://www.github.com/hunterhug/GoSpider)

�������ã�������������ã���Centos7���ã��鿴��[http://www.lenggirl.com/tool/centos7.html](http://www.lenggirl.com/tool/centos7.html)

����ѷ����֧��

1. �б�ҳ������ҳ��ѡ�����ʽ
2. �����������cookie����
3. �����˼��ﵽ��ֵ�Զ�������
4. ������ڹ����Զ�ֹͣ����
5. IP��ɨ������������IP
6. ֧�ֲַ�ʽ��ƽ̨ץȡ
7. �߲�����������ץȡ
8. Ĭ����ҳ��ȡȥ��
9. ��־��¼����
10. ���׿��ӻ���վ��֧�ֶ�ǶȲ鿴���ݣ�С�����ݣ��������ݣ�Asin���ݺ���Ŀ���ݣ�֧�ֲ鿴ÿ��Asin��Ʒ����ʷ��¼�����������۸񣬴�֣�reviews�仯����������֧�ֵ���������վ֧��RBACȨ�ޣ��ɷ���ÿ�������ݵĲ鿴��ʹ��Ȩ�ޡ�
11. ����˼�����棬�ɲ鿴���浱ǰʱ������ץȡ״̬����ȡ�Ľ��ȣ�IP�����ĳ̶ȡ�   **��֧�������������ֹͣ���棬���׳�ΪSaas**��������
12. ���Զ�������IP����������������IP��վAPI��ȡ��IP
13. ��ѡ��HTML�ļ����汾��

�ֲ�ʽ���߲�������ƽ̨����վ�㣬�����Զ������ã���ǿ���ݴ����������������ص㡣����������IP�����㹻����£�ÿ��ÿ��վ�������ץȡ���������Ʒ���ݡ�

## 2016.12.15

1. ���ݿ��ʼ���ű��Ż�
2. IP�����ļ��Ż�
3. ����WEB���Զ���IP

�����޸�GOPATH������׺Ϊ?_config.json�����ã�Ĭ�ϲ���Ҫ�ģ�����ע��˵����Ҫɾ����

```
{
  "Type": "USA",     //����վ���ͣ�������usa,jp,uk,de
  "Datadir": "/data/db/usa",   // �ļ�����λ�ã���ѡ�񱣴棬/�����ڱ�����
  "Proxymaxtrytimes": 40,     // �����˴�����������������IP
  "Rank": 80000,               // ֻ�����������������֮ǰ����Ʒ
  "Listtasknum": 30,        // ץ�б�ҳ�����������鲻Ҫ̫�󣬲����������50
  "Asintasknum": 30,      // ץ����ҳ�����������鲻Ҫ̫�󣬲����������50
  "Localtasknum": 150,  // �����ļ���������������鲻Ҫ̫�󣬲����������50���ɲ���
  "Proxypool": "USAIPPOOL",   // Redis IP���������
  "Proxyhashpool": "USAIPPOLLHASH",  // Redis IP���ó�����
  "Proxyloophours": 24,        // �ص�IPʱ�䣨Сʱ,Redis IP�����꣩
  "Proxyasin": true,         // ����ҳʹ�ô���
  "Proxycategory": false,    //�б�ҳʹ�ô���
  "Proxyinit": false,   // IP�س���ÿ�������Ƿ�׷�ӣ��ɲ���
  "Urlpool": "USAURLPOOL",  //�б�ҳ��ץ������
  "Urldealpool": "USAURLDEALPOOL", //�б�ҳ�����г�
  "Urlhashpool": "USAURLHASHPOOL",  //�б�ҳ��ץ��
  "Asinpool": "USAAsinPOOL",       // ͬ��
  "Asindealpool": "USAAsinDEALPOOL",
  "Asinhashpool": "USAAsinHASHPOOL",
  "Otherhashpool": "USAOtherHashPOOL",  // С�����ݶ���redis�أ��������������ݣ�������ExtraFromRedis,����أ���������������С�����ݿ⣬�������»ᵼ����
  "Asinautopool": true,   //�б�ҳץȡ���ݺ��Զ���Asin��������Asinpool,�������Ϊfalse����Ҫ�ֶ�����asinpool.exe
  "ExtraFromRedis": true,  //����Otherhashpool
  "Asinlocalkeep": false,   //��������ҳ��Datadir
  "Categorylocalkeep": false, //�����б�ҳ��Datadir
  "Urlsql": "SELECT distinct url,id,bigpid ,name,bigpname,page FROM smart_category where isvalid=1 order by bigpid limit 100000",  //ץȡ��Щ�б�ҳ���ɸ�
  "Asinsql": "SELECT distinct asin as id FROM `{?}` order by bigname limit 1000000", //ץȡ��ЩAsin��{?}�ǳ���Ԥ��ռλ���������������������ȥ��
  "Spidersleeptime": 3, // ����
  "Spidertimeout": 35,  //����ץȡ��ʱʱ��
  "Spiderloglevel": "DEBUG",  //������־��¼���ɲ���,��������ΪERROR��ע�⣡����
  "Redisconfig": {  // redis����
    "Host": "14.215.177.40:6379",  //����
    "Password": "smart2016",   //����
    "DB": 0
  },
  "Redispoolsize": 100,  // redis��������ӳ����������Ӧ�ñ�Listtasknum��Asintasknum����
  "Basicdb": {   // �������ݿ�����
    "Ip": "14.215.177.38",
    "Port": "3306",
    "Username": "root",
    "Password": "smart2016",
    "Dbname": "smart_base"
  },
  "Hashdb": {   //��ʷ���ݿ�����
    "Ip": "14.215.177.38",
    "Port": "3306",
    "Username": "root",
    "Password": "smart2016",
    "Dbname": "smart_hash"
  },
  "Hashnum": 500,   //��ʷ���ݿⰴhashcode�ֱ��ֱ�����
  "Datadb": {     // �������ݿ⣬����ֱ�
    "Ip": "14.215.177.38",
    "Port": "3306",
    "Username": "root",
    "Password": "smart2016",
    "Dbname": "smartdb"
  },
  "Ipuse": {   //Ҫ�õ�IP��
    "d": {    //�˿ں����룬��������գ��������ڵ�IP������
      "Port": "808",
      "Secret": "smart:smart2016"
    },
    "e": {
      "Port": "808",
      "Secret": "smart:smart2016"
    },
    "f": {
      "Port": "808",
      "Secret": "smart:smart2016"
    },
    "h": {
      "Port": "808",
      "Secret": "smart:smart2016"
    }
  },
  "Ips": {
    "d": [   //����Ϊd��IP��
      "146.148.149.203-254",   // ����Ip,Ҳ���Բ���������146.148.149.203
    ]
  }
}
```

���г���

Windows��ʽ��

��spiders�ļ�����,��ȥ����վ�㣬����go build *.go��õ�exe�ļ�

1. ���initsql.exe��ʼ�����ݿ�
2. SQL�ļ��������ݿ⣬�б�URL
3. ���ippool.exe������IP
4. ���urlpool.exe�����ĿURL
5. ���listmain.exeץȡ�б�ҳ
6. ���asinmain.exeץȡ����ҳ
7. ���������Asinautopool����Ϊfalse����ô��Ҫ�Լ���Asin����Redis,����asinpool.exe

## MYSQL����

http://blog.csdn.net/faye0412/article/details/6280761


Master��������
```
1.vim /etc/my.cnf

[mysqld]
log-bin=mysql-bin
server-id=1
binlog-ignore-db=information_schema
binlog-ignore-db=beauty
binlog-ignore-db=mysql

2.service mysqld restart

3.grant all privileges on *.* to 'smart'@'%' identified by '123456';

4.flush tables with read lock;

5.show master status;

 mysql-bin.000001 |     6503 |              | information_schema,beauty,mysql |

6.unlock tables;
```

Slave�����ƴӷ�����

```
1.vim /etc/my.cnf
[mysqld]
server-id=2

2.stop slave ;
3.change master to master_host='192.168.2.119',master_user='smart',master_password='123456',master_log_file='mysql-bin.000001', master_log_pos=6503;
4.start slave ;
5.show slave status
```