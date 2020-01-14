> #### ����01:��C++Ϊһ����������  
> ��Ҫ�����ĸ�����:C;Object-Oriented C++;Template C++;STL  

> #### ����02:������const,enum,inline���#define  
> ��const�滻#define��ʾ����(����class������Ա)
> 
> ��inline�����滻#define��������ƺ����ĺ�  

> #### ����03:������ʹ��const  
> const��Ա����:������Ա����������Ϊ�����Բ�ͬ��������,const��������ִ��const��Ա����(���ı��Ա����),
> bitwise constness(������������)��logical constness:��Ҫ��̽������ָ���Ա���������ı䵫��ָ֮�������ı�����������Ƿ�����const��Ա����������
> ��������ǿ��ʵʩbitwise constness�����ʱӦʹ��logical constness��˼��  
> mutable�ؼ���:�����εĳ�Ա�������ǻᱻ�ı��,��ʹ��const��Ա������
> Ϊ��������ظ�������,������const��Ա����ʵ��non-const��Ա����(ʾ������)
```
Class TextBlock{
public:
...
	const char& operator[](std::size_t position) const
	{
	...
		return text[position];
	}
	char& operator[](std::size_t position)
	{
		return const_cast<char&>(static_cast<const TextBlock&>(*this)[position]);
		//����ת�Ͳ���(��һ��Ϊ*this���const,�ڶ����Ǵ�const operator[]����ֵ�Ƴ�const)
	}
}
```

> #### ����04:ȷ������ʹ��ǰ���ȱ���ʼ��  
> �����������Ͷ���,Ӧ��ʹ�ö���֮ǰ�����ʼ��
> ���ڷ��������Ͷ���,Ӧ���乹�캯������ʹ�ó�ʼ���б�(Ч�ʸ���)
> ����ͨ��ָ��������Ϊ��ʼ��ʵ�εĳ�ʼ���б����Ա����(ʾ������)
```
ABEntry:ABEntry():thName(), theAddress(), thePhones(), numTimesConsulted(0) {}
//����Ա����Ϊconst��reference,��һ����Ҫ��ֵ�����ܸ�ֵ
//��������Ҳ��ʹ��
```

> #### ����05:�˽�C++ĬĬ��д��������Щ����
> ��û����,���������Զ�����Ĭ�Ϲ��캯�������ƹ��캯����copy assignment����������������  
> 

> #### ����06:������ʹ�ñ������Զ����ɵĺ���,Ӧ��ȷ�ܾ�
> �ɽ���Ӧ�ĳ�Ա��������Ϊprivate������ʵ��

