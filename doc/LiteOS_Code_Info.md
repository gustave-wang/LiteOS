

## LiteOS代码入口

LiteOS入口在工程对应的main.c中，基本流程如下：

```c

int main(void)
{
    UINT32 uwRet = LOS_OK;
    HardWare_Init();			//首先进行硬件初始化
    uwRet = LOS_KernelInit();		//初始化LiteOS内核
    if (uwRet != LOS_OK)
    {
        return LOS_NOK;
    }
    LOS_Inspect_Entry();		//初始化内核例程
    LOS_Start();			//调用LOS_Start();开始task调度，LiteOS开始正常工作;
}

```

## LiteOS的代码目录结构说明

关于代码树中各个目录存放的源代码的相关内容简介如下：

+ arch
    + arm
        + arm-m M核中断、调度、tick相关代码
        + common arm核公用的cmsis core接口


