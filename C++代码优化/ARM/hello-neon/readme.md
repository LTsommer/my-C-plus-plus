#˵��
```
��NDK samples����hello-neon���и��죬BUILD_EXECUTABLE
���ɵĿ�ִ�г��򿽱����ֻ���/data/local/tmpĿ¼����ִ�У��������

dipper:/data/local/tmp # ./helloneonElf
main exit.
buffer: FIR Filter benchmark:
C version          : 89.3337 ms
Neon version   : 20.4885 ms (x4.36018 faster)

ARM�ٷ����ĵ� DEN0018A_neon_programmers_guide_en.pdf����8��������NEON Code Examples with Optimization
Converting color depth
Median filter
FIR filter����NDK�����ӱȽ���
```

```
ʹ��neon�ķ�ʽ��
1��ʹ��neno intrinsics������C������		NDK�������������õ�neno intrinsics����
2��ʹ��neon���ָ��
3��ʹ�õ������Ŀ⣬OpenMAx
```

```
�ٷ��ĵ�
2.5 NEON libraries
There is free open source software which makes use of NEON, for example:
? Ne10 library functions, the C interfaces to the functions provide assembler and NEON
implementations. See http://projectne10.github.com/Ne10/.
? OpenMAX, a set of APIs for processing audio, video, and still images. It is part of a
standard created by the Khronos group. There is a free ARM implementation of the
OpenMAX DL layer for NEON. See http://www.khronos.org/openmax/.
? ffmpeg, a collection of codecs for many different audio and video standards under LGPL
license at http://ffmpeg.org/.
? Eigen3, a linear algebra, matrix math C++ template library at eigen.tuxfamily.org/.
? Pixman, a 2D graphics library (part of Cairo graphics) at http://pixman.org/.
? x264, a rights-free GPL H.264 video encoder at
http://www.videolan.org/developers/x264.html.
? Math-neon at http://code.google.com/p/math-neon/.
```