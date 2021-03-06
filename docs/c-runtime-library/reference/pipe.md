---
title: _pipe
ms.date: 11/04/2016
api_name:
- _pipe
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- pipe
- _pipe
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
ms.openlocfilehash: bd0107fac28deef94716ff0ce65dd5423a1ececa
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951006"
---
# <a name="_pipe"></a>_pipe

创建用于读取和写入的管道。

> [!IMPORTANT]
> 此 API 不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅[通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。

## <a name="syntax"></a>语法

```C
int _pipe(
   int *pfds,
   unsigned int psize,
   int textmode
);
```

### <a name="parameters"></a>参数

*pfds*<br/>
指向两个**int**的数组的指针，该数组包含读取和写入文件说明符。

*psize*<br/>
要保留的内存量。

*textmode*<br/>
文件模式。

## <a name="return-value"></a>返回值

如果成功，则返回 0。 返回-1 表示错误。 出现错误时， **errno**设置为以下值之一：

- **EMFILE**，指示不再有可用的文件描述符。

- **ENFILE**，指示系统文件-表溢出。

- **EINVAL**，指示数组*pfds*为 null 指针，或传入的*textmode*值无效。

有关这些代码及其他返回代码的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**_Pipe**函数创建一个管道，该*管道*是程序用于将信息传递给其他程序的人工 i/o 通道。 管道类似于文件，因为它具有文件指针或文件描述符，或者两者兼具，并且可以通过使用标准库输入和输出函数读取或写入。 但是，管道不表示特定的文件或设备。 相反，它表示存储器中独立于程序自身内存的临时存储，并且完全由操作系统控制。

**_pipe**类似于 **_open** ，但会打开用于读取和写入的管道，并返回两个文件描述符而不是一个。 程序可以使用管道的两端或关闭它不需要的一端。 例如，Windows 中的命令处理器会在执行命令时（如**PROGRAM1** | **program2.c**）创建管道。

**PROGRAM1**的标准输出描述符附加到管道的写入描述符。 **Program2.c**的标准输入描述符附加到管道的读取描述符。 这消除了创建临时文件以将信息传递给其他程序的需要。

**_Pipe**函数将两个文件描述符返回到*pfds*参数中的管道。 元素*pfds*[0] 包含读取描述符，而元素*pfds*[1] 包含写入描述符。 管道文件描述符的使用方式与其他文件描述符相同。 （低级别的输入和输出函数 **_read**和 **_write**可以读取和写入管道。）若要检测管道终止条件，请检查是否有返回0的 **_read**请求作为读取的字节数。

*Psize*参数指定要为管道预留的内存量（以字节为单位）。 *Textmode*参数指定管道的转换模式。 清单常量 **_O_TEXT**指定文本转换，常量 **_O_BINARY**指定二进制转换。 （有关文本和二进制模式的说明，请参阅 [fopen、_wfopen](fopen-wfopen.md)。）如果*textmode*参数为0，则 **_pipe**将使用默认模式变量[_fmode](../../c-runtime-library/fmode.md)指定的默认转换模式。

在多线程程序中，未执行任何锁定。 返回的文件描述符是新打开的，并且在 **_pipe**调用完成后，任何线程都不应引用这些说明符。

若要使用 **_pipe**函数在父进程和子进程之间进行通信，每个进程必须在管道上只有一个描述符处于打开状态。 描述符必须是相对的：如果父级打开了一个读取描述符，那么子级必须打开一个写入描述符。 要执行此操作，最简单的方法是将 **|** **_O_NOINHERIT**标志与*textmode*进行位或（）。 然后，使用 **_dup**或 **_dup2**创建要传递给子项的管道描述符的可继承副本。 关闭原始描述符，然后生成子进程。 从生成调用返回时，关闭父进程中的重复描述符。 有关详细信息，请参见本文后续部分的示例 2。

在 Windows 操作系统中，关闭管道的所有描述符时，该管道也就被损坏了。 （如果管道上的所有读取描述符都已关闭，则写入该管道操作将导致错误。）管道上的所有读取和写入操作都需要等待，直到有足够的数据或足够的缓冲区空间来完成 I/O 请求。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|可选标头|
|-------------|---------------------|---------------------|
|**_pipe**|\<io.h>|\<fcntl.h>,1 \<errno.h>2|

1表示 **_O_BINARY**和 **_O_TEXT**定义。

2 **errno**定义。

有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

[C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。

## <a name="example-1"></a>示例 1

```C
// crt_pipe.c
/* This program uses the _pipe function to pass streams of
* text to spawned processes.
*/

#include <stdlib.h>
#include <stdio.h>
#include <io.h>
#include <fcntl.h>
#include <process.h>
#include <math.h>

enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */
#define NUMPROBLEM 8

int main( int argc, char *argv[] )
{

   int fdpipe[2];
   char hstr[20];
   int pid, problem, c;
   int termstat;

   /* If no arguments, this is the spawning process */
   if( argc == 1 )
   {

      setvbuf( stdout, NULL, _IONBF, 0 );

      /* Open a set of pipes */
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )
          exit( 1 );

      /* Convert pipe read descriptor to string and pass as argument
       * to spawned program. Program spawns itself (argv[0]).
       */
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],
            hstr, NULL ) ) == -1 )
          printf( "Spawn failed" );

      /* Put problem in write pipe. Since spawned program is
       * running simultaneously, first solutions may be done
       * before last problem is given.
       */
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)
      {

         printf( "Son, what is the square root of %d?\n", problem );
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );

      }

      /* Wait until spawned program is done processing. */
      _cwait( &termstat, pid, WAIT_CHILD );
      if( termstat & 0x0 )
         printf( "Child failed\n" );

      _close( fdpipe[READ] );
      _close( fdpipe[WRITE] );

   }

   /* If there is an argument, this must be the spawned process. */
   else
   {

      /* Convert passed string descriptor to integer descriptor. */
      fdpipe[READ] = atoi( argv[1] );

      /* Read problem from pipe and calculate solution. */
      for( c = 0; c < NUMPROBLEM; c++ )
      {

        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );
        printf( "Dad, the square root of %d is %3.2f.\n",
                 problem, sqrt( ( double )problem ) );

      }
   }
}
```

```Output
Son, what is the square root of 1000?
Son, what is the square root of 2000?
Son, what iDad, the square root of 1000 is 31.62.
Dad, the square root of 2000 is 44.72.
s the square root of 3000?
Dad, the square root of 3000 is 54.77.
Son, what is the square root of 4000?
Dad, the square root of 4000 is 63.25.
Son, what is the square root of 5000?
Dad, the square root of 5000 is 70.71.
Son, what is the square root of 6000?
SonDad, the square root of 6000 is 77.46.
, what is the square root of 7000?
Dad, the square root of 7000 is 83.67.
Son, what is the square root of 8000?
Dad, the square root of 8000 is 89.44.
```

## <a name="example-2"></a>示例 2

这是一个基本的筛选器应用程序。 它在创建了一个将生成的应用程序的 stdout 指向筛选器的管道后，会生成应用程序 crt_pipe_beeper。 筛选器删除 ASCII 7（蜂鸣）字符。

```C
// crt_pipe_beeper.c

#include <stdio.h>
#include <string.h>

int main()
{
   int   i;
   for(i=0;i<10;++i)
      {
         printf("This is speaker beep number %d...\n\7", i+1);
      }
   return 0;
}
```

实际的筛选器应用程序：

```C
// crt_pipe_BeepFilter.C
// arguments: crt_pipe_beeper.exe

#include <windows.h>
#include <process.h>
#include <memory.h>
#include <string.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>

#define   OUT_BUFF_SIZE 512
#define   READ_FD 0
#define   WRITE_FD 1
#define   BEEP_CHAR 7

char szBuffer[OUT_BUFF_SIZE];

int Filter(char* szBuff, ULONG nSize, int nChar)
{
   char* szPos = szBuff + nSize -1;
   char* szEnd = szPos;
   int nRet = nSize;

   while (szPos > szBuff)
   {
      if (*szPos == nChar)
         {
            memmove(szPos, szPos+1, szEnd - szPos);
            --nRet;
         }
      --szPos;
   }
   return nRet;
}

int main(int argc, char** argv)
{
   int nExitCode = STILL_ACTIVE;
   if (argc >= 2)
   {
      HANDLE hProcess;
      int fdStdOut;
      int fdStdOutPipe[2];

      // Create the pipe
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)
         return   1;

      // Duplicate stdout file descriptor (next line will close original)
      fdStdOut = _dup(_fileno(stdout));

      // Duplicate write end of pipe to stdout file descriptor
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)
         return   2;

      // Close original write end of pipe
      _close(fdStdOutPipe[WRITE_FD]);

      // Spawn process
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],
       (const char* const*)&argv[1]);

      // Duplicate copy of original stdout back into stdout
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)
         return   3;

      // Close duplicate copy of original stdout
      _close(fdStdOut);

      if(hProcess)
      {
         int nOutRead;
         while   (nExitCode == STILL_ACTIVE)
         {
            nOutRead = _read(fdStdOutPipe[READ_FD],
             szBuffer, OUT_BUFF_SIZE);
            if(nOutRead)
            {
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);
               fwrite(szBuffer, 1, nOutRead, stdout);
            }

            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))
               return 4;
         }
      }
   }
   return nExitCode;
}
```

```Output
This is speaker beep number 1...
This is speaker beep number 2...
This is speaker beep number 3...
This is speaker beep number 4...
This is speaker beep number 5...
This is speaker beep number 6...
This is speaker beep number 7...
This is speaker beep number 8...
This is speaker beep number 9...
This is speaker beep number 10...
```

## <a name="see-also"></a>请参阅

[进程和环境控制](../../c-runtime-library/process-and-environment-control.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
