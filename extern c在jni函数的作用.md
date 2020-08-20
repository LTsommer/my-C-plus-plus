# extern "C"

```
extern "C"����Ҫ���þ���Ϊ���ܹ���ȷʵ��C++�����������C���Դ��롣
����extern "C"�󣬻�ָʾ�������ⲿ�ִ��밴C���ԣ�������C++���ķ�ʽ���б��롣
����C++֧�ֺ������أ���˱��������뺯���Ĺ����лὫ�����Ĳ�������Ҳ�ӵ������Ĵ����У����������Ǻ���������C���Բ���֧�ֺ������أ���˱���C���Դ���ĺ���ʱ������Ϻ����Ĳ������ͣ�һ��ֻ������������

hello-gl2	�������so ��IDA�п�����jni��������������
jni������								JNIEXPORT void JNICALL Java_com_android_gl2jni_GL2JNILib_init(JNIEnv * env, jobject obj,  jint width, jint height);
�����ĺ������ƣ�						Java_com_android_gl2jni_GL2JNILib_init	
(gl_code.cpp����c++�ķ�ʽ���룬����extern "C"�ĺ��� ��ָʾ���������������C���ԣ�������C++���ķ�ʽ���б���)
�������extern "C"�����ĺ���������		_Z38Java_com_android_gl2jni_GL2JNILib_initP7_JNIEnvP8_jobjectii

hello-jni���ӱ������so ��IDA�п�����jni��������������
jni������						jstring Java_com_example_hellojni_HelloJni_stringFromJNI( JNIEnv* env, jobject thiz )
�����ĺ������ƣ�				Java_com_example_hellojni_HelloJni_stringFromJNI
```

```
ndk samples: hello-gl2
gl_code.cpp

extern "C" {
    JNIEXPORT void JNICALL Java_com_android_gl2jni_GL2JNILib_init(JNIEnv * env, jobject obj,  jint width, jint height);
    JNIEXPORT void JNICALL Java_com_android_gl2jni_GL2JNILib_step(JNIEnv * env, jobject obj);
};

JNIEXPORT void JNICALL Java_com_android_gl2jni_GL2JNILib_init(JNIEnv * env, jobject obj,  jint width, jint height)
{
    setupGraphics(width, height);
}

JNIEXPORT void JNICALL Java_com_android_gl2jni_GL2JNILib_step(JNIEnv * env, jobject obj)
{
    renderFrame();
}

��1��JNIEXPORT ����Jni��������б�������ʵ��Jni�ӿڵķ���ǰ�涼��һ��"JNIEXPORT",������Կ�����Jni��һ����־������Ϊֹû��������ʲô������ô���
��3��JNICALL ������������ΪJni ��Call�������֣�����������˼���� Jni����XXX�������XXX����JAVA�ķ���������


ndk samples: native-codec
native-codec-jni.cpp

extern "C" {

jboolean Java_com_example_nativecodec_NativeCodec_createStreamingMediaPlayer(JNIEnv* env,
        jclass clazz, jstring filename)
{
    LOGV("@@@ create");

    return JNI_TRUE;
}

// set the playing state for the streaming media player
void Java_com_example_nativecodec_NativeCodec_setPlayingStreamingMediaPlayer(JNIEnv* env,
        jclass clazz, jboolean isPlaying)
{
    LOGV("@@@ playpause: %d", isPlaying);

}

}
��������õ��ǽ�jni����ֱ�Ӱ��� extern "C" ��
û��дJNIEXPORT��JNICALL
```

```
ndk samples: hello-jni
hello-jni.c

jstring
Java_com_example_hellojni_HelloJni_stringFromJNI( JNIEnv* env,
                                                  jobject thiz )
{
	#define ABI "armeabi-v7a"
    return (*env)->NewStringUTF(env, "Hello from JNI !  Compiled with ABI " ABI ".");
}
```


