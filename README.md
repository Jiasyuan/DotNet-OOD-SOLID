# SOLID Principles Of  Object-Oriented Design in C#.Net
SOLID Principles Of  Object-Oriented Design

## Table of Contents  
+ [ OOP 四個特性 ](#oop4pillars)  
+ [內聚力與耦合力](#CohesionandCoupling)  
+ [SOLID 物件導向設計原則](#SOLIDPrinciplesOOD)  
+ [單一功能原則(SRP)](#SRP)  
+ [開放封閉原則(OCP)](#OCP)  
+ [里氏替換原則(LSP)](#LSP)  
+ [介面隔離原則(ISP)](#ISP)
+ [相依反轉原則(DIP)](#DIP)

<a name="oop4pillars"></a>
## OOP 四個特性  
+ 抽象(Abstraction)	
	+ 將真實世界的需求(物件)轉為程式中的類別
	+ 類別可包含狀態(屬性)與行為(方法)
+ 封裝(Encapsulation)  
	+ 隱藏/保護內部實作細節，並對屬性或方法進行[存取範圍層級](https://docs.microsoft.com/zh-tw/dotnet/csharp/language-reference/keywords/accessibility-levels)的設定  	
	> 朕賜給你的，才是你的﹐朕不給﹐你不能搶。  
+ 繼承(Inheritance)  
	+ 可建立新類別來重複使用與擴充和修改其他類別中定義的行為  
+ 多型(Polymorphism)
	+ 在相同介面下，可用不同類別實現
	+ 多型有分成多種不同類型
	> 被抽象化的東西，可以有多樣表現   

### 多型
+ 在設計時期(Design Time)
	+ 基底類別可以定義和實作"虛擬"([virtual](https://docs.microsoft.com/zh-tw/dotnet/csharp/language-reference/keywords/virtual))屬性和方法
	+ 衍生類別可以"覆寫"([override](https://docs.microsoft.com/zh-tw/dotnet/csharp/language-reference/keywords/override))屬性和方法  
+ 在執行時期(Runtime)
	+ 當呼叫基底類別的虛擬方法時，會改呼叫子類別覆寫的方法
+ 在C#中，所有類型都是多型類型
	+ 因為所有類型都是繼承[Object](https://docs.microsoft.com/zh-tw/dotnet/api/system.object?view=netcore-3.1)
<a name="CohesionandCoupling"></a>
## 內聚力與耦合力    
### 何謂模組(Module)  
在C#中可能是  
+ 類別(Class)  
+ 方法(Method)  
+ 組件(Assembly)  
### 內聚力(Cohesion)  
一個模組內完成一件工作的度量指標  
+ 高內聚力
	+ 一個模組只完成一件工作  
	+ 內聚力高就代該模組可以獨立運作，也更容易重複利用
	+ 例如:一個Class只負責一件事情(ex:寄送郵件)  
+ 低內聚力
	+ 一個模組只完成多件工作  
	+ 內聚力低就代表該模組難以維護/測試/重複利用/理解
+ 提高內聚力方式
	+ 若要在一模組內完成多件工作，最好拆成多個不同類別  
	+ 實踐[SRP](#SRP)

### 耦合力(Coupling)  
模組與模組之間的關聯強度  
+ 模組之間互相依賴的程度
+ 衡量兩個模組的緊密程度  
+ 高耦合力
	+ 修改模組A時，相關聯的模組B可能受影響
+ 低耦合力
	+ 當模組修改時，越少的模組被影響就代表耦合力較低
+ 降低耦合力方式
	+ 實踐[DIP](#DIP)  
	+ 耦合是無可避免的  

> 理論上程式要高內聚，低耦合，但現實沒有那麼簡單    
> 內聚力越高，類別越多，代表耦合越高  

<a name="SOLIDPrinciplesOOD"></a>
## SOLID 物件導向設計原則  
+ 單一功能原則(Single Responsibility Principle)  
+ 開放封閉原則(Open-Closed Principle)  
+ 里氏替換原則(Liskov Substitution Principle)  
+ 介面隔離原則(Interface-Segregation Principles)  
+ 相依反轉原則(Dependency inversion Principle)
### SOLID原則的好處
+ 降低程式碼複雜程度  
+ 程式碼具有較佳可讀性  
+ 提升程式碼的可重複利用性  
+ 讓模組有合理的高內聚力、低耦合力  
+ 面對變更需求時，可減少破壞現有模組的風險(改A壞B)  
> + 依循SOLID原則，可寫出較好的Code  
> + 依循SOLID原則，可判斷程式碼的好壞([Code Smell](https://zh.wikipedia.org/wiki/%E4%BB%A3%E7%A0%81%E5%BC%82%E5%91%B3))  

<a name="SRP"></a>
## 單一功能原則(SRP)

<a name="OCP"></a>
## 開放封閉原則(OCP)  

<a name="LSP"></a>
## 里氏替換原則(LSP)

<a name="ISP"></a>
## 介面隔離原則(ISP)  

<a name="DIP"></a>
## 相依反轉原則(DIP)  