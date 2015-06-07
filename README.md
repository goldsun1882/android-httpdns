## android-httpdns

��дandroidӦ��ʱ����������Ҫͨ���������http Api����Զ�̼���ͼƬ�ȡ�
�������Ǿ���������������������ʱ�ܾõ�����, �����������ٳַ��ʵ��˴����IP�ϡ�
Ϊ�˹�����������������[DNSPod](https://www.dnspod.cn)Ϊapp�������Ƴ���[D+(http dns)](https://www.dnspod.cn/httpdns)�ķ��������������⡣
������һ��ͼƬappʱҲ�������������������⣬���÷�װ��һ�¡�

### ʹ��

����

	String ip = HttpDNS.getAddressByName("www.dnspod.cn");
	Log.i("httpdns", String.format("getAddressByName: %s", ip));

	String json = HttpDNS.getStrWithHttpDNS("http://image.baidu.com/user/msg");
	Log.i("httpdns", String.format("getStrWithHttpDNS: %s", json));

	Bitmap img = HttpDNS.getBitmapWithHttpDNS("http://img0.bdstatic.com/static/common/widget/search_box_search/logo/logo_3b6de4c.png");
	Log.i("httpdns", String.format("getBitmapWithHttpDNS: %d", img.getByteCount()));

### ����˵��

- �̰߳�ȫ�Ժ�֧��
- ��ӭ��ҸĽ�
