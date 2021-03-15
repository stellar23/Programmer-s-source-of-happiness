命令提示符代码：（0-1） 

@echo off

title 黑客帝国

setlocal ENABLEDELAYEDEXPANSION

color 0a

for /l %%i in (1,1,80) do (

set Down%%i=0

)

:loop

for /l %%j in (1,1,80) do (

set /a Down%%j-=1

if !down%%j! LSS 0 (

set /a Arrow%%j=!random!%%4

set /a Down%%j=!random!%%15+10

)

if "!Arrow%%j!" == "1" (

set /a chr=!random!%%2

set /p=!chr!<nul

) else (

set /p= <nul

)

)

goto loop

goto :eof

 

 

命令提示符代码：（0-9）

 

 

@echo off

title 黑客帝国

color 0a

setlocal ENABLEDELAYEDEXPANSION

for /l %%i in (0) do (

set "line="

for /l %%j in (1,1,80) do (

set /a Down%%j-=2

set "x=!Down%%j!"

if !x! LSS 0 (

set /a Arrow%%j=!random!%%3

set /a Down%%j=!random!%%15+10

)

set "x=!Arrow%%j!"

if "!x!" == "2" (

set "line=!line!!random:~-1! "

) else (set "line=!line! ")

)

set /p=!line!<nul

)

 

补充上C++代码：（0-9）

 

 

#include "stdafx.h"

#include "stdlib.h"

#include "windows.h"

int main(int argc, char* argv[])

{

system("color 0a");

while(1){

printf("%c",(rand()%10>5?'0'+rand()%10:' '));

if(