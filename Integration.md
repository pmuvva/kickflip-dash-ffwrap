FFMPEG-DASH Integration

Download the source code from https://github.com/pmuvva/kickflip-dash-ffwrap or git clone 
https://github.com/pmuvva/kickflip-dash-ffwrap.git

Download Android NDK from https://developer.android.com/ndk/downloads/index.html

FFMPEG Compilation:

1. Select the architecture either arm or x86
2. open build.sh file set in —-arch = arm or x86
3. In build.sh file Set the NDK location in your computer.
4.run ./build.sh then it starts to compile the ffmpeg source library with specific NDK. I compiled ffmpeg 3.3.4 version  with NDK-R15C

5. Out put files are located under android/arm (for x86 it will be under android/x86/)

6. Out files contain libraries under lib folder and header files under include folder


FFmpegWrapper Generation:

1. Goto FFmpegWrapper-Android folder
2.Go to FFmpegWrapper/Jni folder
3. Create include folder and place include files from FFMPEG Compilation (android/arm/include) to here

4. Goto FFmpegWrapper/libs folder then create ‘arm’ directory and place all library
files from android/arm/libs/*-57.so files(files which has number like 57,56 or 3…etc) to here

5.Export your NDK path in ~/.bash_profile then run source .bash_profile(for Mac) 

6. go to FFmpegWrapper/Jni folder then run ./ndk-build.sh 

7. After compilation the output files are located at FFmpegWrapper/libs/armeabi folder
8. armeabi contains gdb.setup, gdbserver,libFFmpegWrapper.so,libavcodec-57.so,libavdevice-57.so,libavfilter-6.so,libavformat-57.so,libavutil-55.so,libswresample-2.so,libswscale-4.so files	


FFMPEG Integration for KickPlay:

1. Copy FFmpegWrapper/libs/armeabi files into kickflip-android-sdk/sdk/src/main/jniLibs/armeabi

2. Open kickflip-android-example app through Android studio then Run the App and it will download into Asus Phone.




 

