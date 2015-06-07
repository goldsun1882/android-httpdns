## android-httpdns

��дandroidӦ��ʱ����������Ҫͨ���������http Api����Զ�̼���ͼƬ�ȡ�
�������Ǿ���������������������ʱ�ܾõ�����, �����������ٳַ��ʵ��˴����IP�ϡ�
Ϊ�˹�����������������[DNSPod](https://www.dnspod.cn)Ϊapp�������Ƴ���[D+(http dns)](https://www.dnspod.cn/httpdns)�ķ��������������⡣
������һ��ͼƬappʱҲ�������������������⣬���÷�װ��һ�¡�

- [Դ��������](https://github.com/onlytiancai/android-httpdns/blob/master/HttpDNS/app/src/main/java/com/ihuhao/app/httpdns/HttpDNS.java), ֱ�ӿ�������Ŀ���þ���
- [���Դ���](https://github.com/onlytiancai/android-httpdns/blob/master/HttpDNS/app/src/main/java/com/ihuhao/app/httpdns/MainActivity.java)
- �����ļ���������Android Studio�Զ����ɵģ�����Ŀ����Cloneֱ��������ԡ�

### ʹ�÷���

����

	String ip = HttpDNS.getAddressByName("www.dnspod.cn");
	Log.i("httpdns", String.format("getAddressByName: %s", ip));

	String json = HttpDNS.getStrWithHttpDNS("http://image.baidu.com/user/msg");
	Log.i("httpdns", String.format("getStrWithHttpDNS: %s", json));

	Bitmap img = HttpDNS.getBitmapWithHttpDNS("http://img0.bdstatic.com/static/common/widget/search_box_search/logo/logo_3b6de4c.png");
	Log.i("httpdns", String.format("getBitmapWithHttpDNS: %d", img.getByteCount()));

### Ч������

���Դ�������

	String host = url.getHost();

	Log.i("HttpDNS resove:", "begin:" + host);
	String ip = HttpDNS.getAddressByName(host);
	Log.i("HttpDNS resove:", "end:" + host + " " + ip);

	Log.i("dns resove:", "begin:" + host);
	InetAddress address = InetAddress.getByName(host);
	Log.i("dns resove:", "end:" + host + " " + address.getAddress());

���Խ������

	06-07 20:05:18.264  23990-24418/com.ihuhao.app.myapplication I/HttpDNS resove:�s begin:e.hiphotos.baidu.com
	06-07 20:05:18.354  23990-24418/com.ihuhao.app.myapplication I/getips�s getips: e.hiphotos.baidu.com 121.15.253.48
	06-07 20:05:18.354  23990-24418/com.ihuhao.app.myapplication I/cachedns�s add ips to cache:e.hiphotos.baidu.com
	06-07 20:05:18.354  23990-24418/com.ihuhao.app.myapplication I/cachedns�s get ips:e.hiphotos.baidu.com 1
	06-07 20:05:18.354  23990-24418/com.ihuhao.app.myapplication I/HttpDNS resove:�s end:e.hiphotos.baidu.com 121.15.253.48
	06-07 20:05:18.354  23990-24418/com.ihuhao.app.myapplication I/dns resove:�s begin:e.hiphotos.baidu.com
	06-07 20:05:38.454  23990-24418/com.ihuhao.app.myapplication I/dns resove:�s end:e.hiphotos.baidu.com [B@435f8ec0

���Կ���ʹ��http dns�ڱ���û�л��������£������������˲���1�룬����InetAddress.getByName����20�룬����������Եģ�������ʽ��wifi��
���õ���3G��ʽ���ԣ�http dns��ϵͳ�Դ��Ľ�����300����ɣ��ҷ�װ�Ŀ�Ỻ���������ӣ������������ܶ�, �پ������ڵ���3Gģʽ��
��ʱ��Ҳ��������10�����ϣ�����http dns����û�㶴����������������������http dns���Ǻ������Ƶġ�


	06-07 20:14:40.444  28905-29173/com.ihuhao.app.myapplication I/HttpDNS resove:�s begin:c.hiphotos.baidu.com
	06-07 20:14:40.444  28905-29173/com.ihuhao.app.myapplication I/cachedns�s soft reference miss
	06-07 20:14:40.824  28905-29173/com.ihuhao.app.myapplication I/getips�s getips: c.hiphotos.baidu.com 121.15.253.48
	06-07 20:14:40.824  28905-29173/com.ihuhao.app.myapplication I/cachedns�s add ips to cache:c.hiphotos.baidu.com
	06-07 20:14:40.824  28905-29173/com.ihuhao.app.myapplication I/cachedns�s get ips:c.hiphotos.baidu.com 1
	06-07 20:14:40.824  28905-29173/com.ihuhao.app.myapplication I/HttpDNS resove:�s end:c.hiphotos.baidu.com 121.15.253.48
	06-07 20:14:40.824  28905-29173/com.ihuhao.app.myapplication I/dns resove:�s begin:c.hiphotos.baidu.com
	06-07 20:14:40.904  28905-29173/com.ihuhao.app.myapplication I/dns resove:�s end:c.hiphotos.baidu.com [B@435da0a0


### ����˵��

- �̰߳�ȫ�Ժ�֧��
- ��ӭ��ҸĽ�
