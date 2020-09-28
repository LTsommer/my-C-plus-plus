#
```
tag 1.2.1
ext/natvie/threadĿ¼����
thread.h
���ͷ�ļ���ʵ����c++��׼�������thread

#define THREAD_HANDLE HANDLE
#define THREAD_HANDLE pthread_t
typedef THREAD_HANDLE native_handle_type;
native_handle_type m_handle;

	template <typename F>
	void StartThread(F* param)
	{
#ifdef USE_BEGINTHREADEX
		m_handle = (HANDLE)_beginthreadex(NULL, 0, &RunAndDelete<F>, param, 0, &m_id.m_thread);
#elif defined(_WIN32)
		m_handle = CreateThread(NULL, 0, &RunAndDelete<F>, param, 0, &m_id.m_thread);
#else
		pthread_attr_t attr;
		pthread_attr_init(&attr);
		pthread_attr_setstacksize(&attr, 1024 * 1024);
		if (pthread_create(&m_id.m_thread, &attr, &RunAndDelete<F>, param))
			m_id = id();
#endif
	}
	
	���Կ�����ͬƽ̨�����̵߳ľ���ʵ��
	����ʹ��c11������̣߳�������ǿ�ƽ̨��
```

```
����ֵ��һ��

threadpool
prioritizedworkqueue
threadutil ��װ��һ��event��
executor
```

```
1.4.1֮���threadֱ������c++��׼���е�
1.2.1 base/mutex.h����event�Ŀ�ƽ̨��װ
```