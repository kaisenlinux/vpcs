
    ��ӭʹ�� VPCS, ���°汾Ϊ 0.8.

    VPCS ������������� BSD ��ɵ�����ַ���
    Դ��������Э��������Դ� vpcs.sf.net ��ȡ����
    ������Ϣ������� wiki.freecode.com.cn.
   
    VPCS ����ģ����� 9 ������� PC������� ping/traceroute ��Щ PC������
����Щ PC �� ping/traceroute ������������·��������Ȼ��Щ����� PC������
��ȫ�����ϵ� PC����ֻ��һ�������� Linux �� Windows �ϵ�Ӧ�ó��򣬽�����
ʹ�����������й����������ڽ��� Dynamips ѧϰ Cisco �豸�Ĺ����У���
�𵽷ǳ���İ����������������ʵ���г䵱 PC ��·��������ʹ�� Vmware ����
�� PC��ͨ������Щ������߻�ռ�ô������ڴ�� CPU ��Դ��

   VPCS ���������� UDP ������̫ģʽ���� UDP ��ʽ�£�VPCS ͨ�� UDP ���ͺͽ�
�����ݰ�����̫��ʽ�£�ʹ�� /dev/tapx ���ͺͽ������ݰ����� Windows ��ֻ֧
�� UDP ��ʽ��

   �� VPCS ������ ȱʡ������ 20000 �� 20008 �� UDP �˿ڣ����� 30000 �� 
30008 �������ݰ������û��ָ�������ļ����ҵ�ǰĿ¼�´���ȱʡ�������ļ�
���ļ���Ϊ��startup.vpc����VPCS �ͻ��Զ����������ļ�����ִ�а��������
startup.vpc ���԰��������Ϊ VPCS ���ڲ����

   VPCS ��������ѡ��
   usage: vpcs [OPTIONS] [FILENAME]
   OPTIONS:
     -h             print this help then exit
     -v             print version information then exit
   
     -i num         number of vpc instances to start (default is 9)
     -p port        run as a daemon listening on the tcp port
     -m num         start byte of ether address, default from 0
     [-r] FILENAME  load and execute script file FILENAME
   
     -e             tap mode, using /dev/tapx by default (linux only)
     [-u]           udp mode, default
   
   udp mode options:
     -s port        local udp base port, default from 20000
     -c port        remote udp base port (dynamips udp port), default from 30000
     -t ip          remote host IP, default 127.0.0.1
   
   tap mode options:
     -d device      device name, works only when -i is set to 1
   
   hypervisor mode option:
     -H port        run as the hypervisor listening on the tcp port
   
     If no FILENAME specified, vpcs will read and execute the file named
     startup.vpc if it exists in the current directory.

   ע�⣺
   1. VPCS ʹ�õ� cygwin1.dll ���������� cygwin1.dll �����ݡ�������һϵͳ
      ��ֻ�������°汾�ġ�
   2. ��̨����ģʽʱ��������telnet LINEMODEΪ'һ�δ���һ�ַ�'��
      'telnet> mode character'

վ�㣺http://wiki.freecode.com.cn �� http://mirnshi.cublog.cn

��ʷ�汾��
   0.8     ֧��IPv6��Ƭ����
           ֧��DNS IPv6 AAAA
           ����������ѡ��--��ֹrelay����
           
   0.6     �����޶���
             1. ��̨Ӧ������ʱ��δʹ�����ص�MAC��ַ
             2. �����20�����������±���
             3. ��ʷ������������±���
           ���������޶���
             1. �Ƴ�'ip mtu'���滻Ϊ'set mtu'
             2. ֧�ֽ�relay�����ݰ�ת�����ļ����ļ���ʽΪpcap��
                ���Զ�̬������˲��ɷ������ڵ�������������ݡ�
             3. dhcp4�����Զ�����
             4. ֧��IP��Ƭ/����
             5. ping����֧��'-D'ѡ�ǿ�Ʋ���Ƭ
             6. �������ݺͽ������ݰ����ȶ�MTU������MTU����Ӧ��ʾ����
             7. �ػ���ַ���鲥��ַ�����ַ���ж�Ϊ�Ƿ���ַ��������������ʹ��
             8. ���¸�ʽ������
             9. echo����֧�ֲ�ɫ������ʾ������'@'������ʾ
             10. ���ӱ���dns��������relay��
              
   0.5b2   �����޶���ʹ��getenv+access��ʽ��ȡVPCS����ʵ·��
           Debian GNU/kFreeBSD�Ĳ�����Daniel Lintott��
           ����echo����ʱ��ˢ�����
           ����tcp�Ự������Сtcp����ʱ��
           �����޶���ԴMAC��ַδ���浽arp����

   0.5b1   ֧������vpc����������
           ֧������TAP�豸������ֻ����1��VPC��
           load��save����֧��ȱʡ�ļ���

   0.5b0   ֧��hypervisor
   
   0.4b2   ֧��DNS
           ֧�����ݰ�Э�������ʾ
           ֧��Զ�̵�¼�����豸���ȼ�����
           ������ǿ���޶�
           
   0.4a    ���Ӻ�̨����ģʽ
   0.3     BSD���
   0.20a   ��һ����ǿIPv6��֧��LinkLocal����״̬�Զ����ã��ֹ�eui-64
           ֧�ָ��������ping��ʵ����tcp�����ӵ��رյ�����״̬
           ֧�ֱ���/��������
           ֧����ʷ�����Զ�����/����
           
   0.16a   ֧��IPv6
   0.15a   ����DHCP��ȡIP��ַ����
           ����������ַʱ�����Բ���ָ�����ص�ַ
   0.14g   �޶�traceroute����ѭ������
   0.14f   �޶�traceroute����TTL�������
   0.14e   �޶�echo��traceroute�����д������
   0.14d   �޶�Arp������󣬴���ؽ��㲥��ַ��ΪԴ��ַӦ��Arp����  
   0.14c   �޶�TTLΪ64  
   0.14b   �޶� I/O ���д���
   0.14a   ���� arp ���������ʾ��ǰ�� arp ��120��Ĺ���ˢ��
           ���� echo ���������Զ���������� udp/tcp ���ݰ�������ڲ���
           ACL �ǱȽ����õġ�
           �޶�ͬ�����Ƚϴ���
   0.13a   ���� ping/tracert ���� IP ��Ӧ
           �޶� ping �κ� IP�������ڴ���
   0.12s   �޶� tracert �����������
   0.10s   ֧�� udp ��ʽ
   0.02s   �޶���һ���ַ�����������
   0.01s   ��ʼ�汾
   