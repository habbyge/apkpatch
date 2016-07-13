1.编译 ApkPatchLibrary 各个版本(armeabi, armeabi-v7a,x86);
在开始编译时，会报 error: undefined reference to 'err' 和 error: undefined reference to 'errx';
经过查找,是因为我的系统库没有这两个函数,于是直接替换成printf编译; ( http://linux.die.net/man/3/errx )
err: Display the current errno information string and exit;
errx: Display an error message and exit;
所以，我们可以把对应到的地方替换成 printf 和 exit 两个函数组合;
