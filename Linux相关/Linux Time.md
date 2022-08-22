- 写在前面
  - 因为最近在写一个需求希望能够判断现在的时间和某个标准时间相比较进行判断时间差。发现对于Linux的time操作不太清晰，所以就写一下。


#### step1 time获取时间戳
```c++
#include<time.h>
time_t time(time_t* tmt)
```
- 调用
```c++
int main()
{
    time_t curTime;
    curTime = time(NULL);
    cout<<curTime<<endl;
    return 0;
}
```

#### step2 将time_t转换为tm结构体
- function1 struct tm* gmtime(const time_t* timep)
- function2 struct tm* localtime(const time_t* timep)

#### step3 采用上述两个function后可以利用tm结构体的变量来实现逻辑。
**注意两个要点**
1. month 需要+1
2. year  需要+1900

