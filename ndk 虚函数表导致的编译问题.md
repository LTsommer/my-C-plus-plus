#
```
������������Ϣ��
 error: undefined reference to 'vtable for CCheatGTASA'
 the vtable symbol may be undefined because the class is missing its key function
 
 �������£�
 cheatI.h�ļ�
 
 class CCheatI
{
public:
	CCheatI(){};
	virtual ~CCheatI(){};
	virtual void printfHelp() = 0;
	virtual void initCheatFun() = 0;
	virtual string& getFunSymByIndex(int index) = 0; 
protected:
	map<int,string> callMap;
};

class CCheatGTASA : public CCheatI
{
public:
	CCheatGTASA() {};
	virtual ~CCheatGTASA() {};
	virtual void printfHelp() {};
	virtual void initCheatFun() {};
	virtual string& getFunSymByIndex(int index) {};
};


cheatMain.cpp���ã�
CCheatI* pCheat = new CCheatGTASA();

���ַ�ʽ��ndk��visual stduio�����Ա���ͨ��
�����CCheatGTASA��printfHelp initCheatFun getFunSymByIndexʵ�ַ���.cpp�У�ndk���벻ͨ����visual stduio����ͨ��
ԭ����������ģ�� ��cheatGTASA.cppֻ���뵽һģ���У�������Ĳ�һ������ʼ��Ϊ��Դ�ļ��������Ⱥ�˳��
include $(BUILD_SHARED_LIBRARY)
include $(BUILD_EXECUTABLE)

�麯��������ʱ�ڣ�����ʱ
���򹹽���Build�����ĸ����̣�Ԥ���롢���롢�������ӣ�
�����̽��C++����ģ�͡�
������е�virtual functions��ַ����α����������ģ�
��C++�У�virtual functions���ɾ�����class object�����ã������ڱ���ʱ�ڻ�֪�����⣬��һ���ַ�ǹ̶�����ģ�ִ���ڲ������������滻֮��
���ڳ���ִ��ʱ�����Ĵ�С�����ݶ�����ı䣬�����佨���ʹ�ȡ�Կ����ɱ�������ȫ�ƿأ�����Ҫִ���ڵ��κν��롣��
https://www.cnblogs.com/xiehongfeng100/p/4678892.html

���ʣ���������pointerӦ������Ե�ַ�������������ڹ��캯����initializer list �����¼��㣿����

```