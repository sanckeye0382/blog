---
title: a738最大公約數

---

# a738最大公約數

[![hackmd-github-sync-badge](https://hackmd.io/nbe2VcgGSqKebWM571DTvg/badge)](https://hackmd.io/nbe2VcgGSqKebWM571DTvg)

---
#### 短除法
1. 準備
確定兩個數 𝑎 和 𝑏（假設 𝑎 > 𝑏）。取較小數 𝑏 作為質數範圍的上限。

2. 從最小質數開始短除
* 從最小質數2 開始檢查：如果 𝑎 和 𝑏都能被質數 𝑝 整除，記錄下 𝑝 ，並將 𝑎 和 𝑏 分別除以 𝑝，繼續短除。
* 如果 𝑝 不能整除，則嘗試下一個質數。

3. 停止條件當質數超過 𝑏 或 𝑎 和 𝑏無法再繼續短除時，結束。

4. 計算最大公約數
將所有能整除 𝑎和𝑏的質數累乘，得到最大公約數（GCD）。
---
#### 輾轉相除法
1. 初始化
給定兩個非負整數 𝑎 和 𝑏，假設 𝑎 ≥ 𝑏。
2. 迭代過程
* 如果 𝑏 = 0，那麼最大公約數就是 𝑎，結束。
* 否則，計算 𝑎 mod 𝑏 的餘數 𝑟，並更新 𝑎 = 𝑏 ， 𝑏 = 𝑟。
3. 重複步驟 2 直到 𝑏 = 0 時停止，最後的 𝑎 就是最大公約數。
---

短除法代碼
```c
#include <stdio.h>

int main()
{
  int a=24 , b=30 ;
  int mul=1 ;
  for(int i=2 ; i<=a ; i++)
  {
     while(a%i==0 && b%i==0)
     {
         mul *= i ;
         a/=i , b/=i ;
     }
  }
    printf("%d",mul);

  return 0 ;
}
```
輾轉相除法：
```c
#include <stdio.h>

int main()
{
  int a=24 , b=30 ;
  if(a<b)
  {
      int tmp = a;
      a = b ;
      b = tmp ;
  }
  
  while(b!=0)
  {
      int r = a%b ;
      a=b , b=r ;
  }
  if(a==1) 
  puts("1");
  else {
  printf("%d",a) ;     
  }
  return 0 ;
}
```
此處原本的交換邏輯可以省略掉,因為遇到while()裡面的邏輯會在第一次跑迴圈時,將a,b兩數交換# a738最大公約數

[![hackmd-github-sync-badge](https://hackmd.io/nbe2VcgGSqKebWM571DTvg/badge)](https://hackmd.io/nbe2VcgGSqKebWM571DTvg)

---
#### 短除法
1. 準備
確定兩個數 𝑎 和 𝑏（假設 𝑎 > 𝑏）。取較小數 𝑏 作為質數範圍的上限。

2. 從最小質數開始短除
* 從最小質數2 開始檢查：如果 𝑎 和 𝑏都能被質數 𝑝 整除，記錄下 𝑝 ，並將 𝑎 和 𝑏 分別除以 𝑝，繼續短除。
* 如果 𝑝 不能整除，則嘗試下一個質數。

3. 停止條件當質數超過 𝑏 或 𝑎 和 𝑏無法再繼續短除時，結束。

4. 計算最大公約數
將所有能整除 𝑎和𝑏的質數累乘，得到最大公約數（GCD）。
---
#### 輾轉相除法
1. 初始化
給定兩個非負整數 𝑎 和 𝑏，假設 𝑎 ≥ 𝑏。
2. 迭代過程
* 如果 𝑏 = 0，那麼最大公約數就是 𝑎，結束。
* 否則，計算 𝑎 mod 𝑏 的餘數 𝑟，並更新 𝑎 = 𝑏 ， 𝑏 = 𝑟。
3. 重複步驟 2 直到 𝑏 = 0 時停止，最後的 𝑎 就是最大公約數。
---

短除法代碼
```c
#include <stdio.h>

int main()
{
  int a=24 , b=30 ;
  int mul=1 ;
  for(int i=2 ; i<=a ; i++)
  {
     while(a%i==0 && b%i==0)
     {
         mul *= i ;
         a/=i , b/=i ;
     }
  }
    printf("%d",mul);

  return 0 ;
}
```
輾轉相除法：
```c
#include <stdio.h>

int main()
{
  int a=24 , b=30 ;
  if(a<b)
  {
      int tmp = a;
      a = b ;
      b = tmp ;
  }
  
  while(b!=0)
  {
      int r = a%b ;
      a=b , b=r ;
  }
  if(a==1) 
  puts("1");
  else {
  printf("%d",a) ;     
  }
  return 0 ;
}
```
此處原本的交換邏輯可以省略掉,因為遇到while()裡面的邏輯會在第一次跑迴圈時,將a,b兩數交換