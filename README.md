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

## 什麼是原則
A basic idea or rule that explains or controls how something happens or works
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

使用SOLID原則  
 + *原則須依據專案情況使用*  
 + *夠不夠了解需求*  

<a name="SRP"></a>

## 單一功能原則(SRP)
A class should have one, and only one, reason to change.    
### SRP基本精神  
一個類別可有太多reason to change時，代表該類別可被切割
+ 定義一個新類別，將部分程式碼分出去  
+ 對類別進行適度切割，方便日後管理與維護!  

*SRP就是提高內聚力*  

常見問題  
+ 將所有功能都寫在同一類別  
	+ 類別複雜度過高  
	+ 不容易找到問題點(bug)  
	+ 不易維護  
	+ 使用該類別時不知道該用哪個方法  

SRP使用時機  
+ 類別中有一段Code有*重複利用*的需求
+ 多reason to change在不同時間點產生變更需求
	+ 範例
+ 有非必要功能(未來需求)需要實作

**SRP套用越多，耦合性越高**  
+ 不用急於第一時間就專注於分離責任
+ 尚未出現需求(未來需求)不需要預先分離責任
+ 當需求變更時，在分割

**SRP最簡單也卻最難最好**


<a name="OCP"></a>

## 開放封閉原則(OCP)  
Softweare entities(Class, Module, Funtion, etc) should be *open for extension* but *close for modification*  
> Curtis: 易於擴充，不利於修改  

藉由新增程式碼來擴充系統功能，而不是修改已存在的程式碼來擴充系統功能   

### OCP基本精神  
一個Class需要開放，代表該類別可被擴充
+ 透過*繼承*可輕鬆做到  
+ C#還有*擴充方法*可以擴充既有Class  
一個Class需要封閉，代表有其他人正在使用該class
+ 封閉修改可以有效避免未知問題發生  
+ 只有編譯後的結果，沒有Source Code  

常見問題  
+ 耦合力過高，擴充不易  

OCP實作方式
+ 採用分離與相依技巧(*相依於抽象*)  
	+ 缺點:需針對原有的code進行重構  

OCP使用時機  
+ 既有Class*已被清楚定義*，處於*強調穩定*的狀態  
+ *需擴充*現有Class，*加入新需求*的屬性和方法  
+ 擔心修改現有code會破壞現有系統的運作  
+ 系統剛開始設計時就決定採用OCP，可透過*介面*或*抽象類別*進行實作  

**Interface vs Abstract**
+ Interface:不可包含實作，耦合度較低  
+ Abstract:可包含實作，耦合度較高  


<a name="LSP"></a>

## 里氏替換原則(LSP)
Subtypes *must* be *substitutable* for their *base* *types*.  

子類別必須可以替換為他的基底類別  

### LSP基本精神  
+ 當實作繼承時，必須確保型別轉換後還能得到正確的結果  
	+ 每個*衍生類別*都可以正確替換為*基底類別*，且程式再執行時不會有異常  
	+ 必須正確實作*繼承*與*多型*  

常見問題  
+ 不正確實做*繼承*與*多型*  
+ 實作繼承時，在特定情況下發生Runtime Error  
+ 違反LSP有時候較難被發現  

LSP實作方式  
+ 採用*類別繼承方式*來進行開發
	+ 需注意繼承的實作方式  
+ 採用*合約設計方式*來進行開發
	+ 利用*Iterface*來定義基底型別  

LSP使用時機  
+ 當需要透過*基底型別*對*多型*物件進行操作時

> 保哥:把Warring看完，很多問題都解決了，盡量讓Warring為0  

<a name="ISP"></a>

## 介面隔離原則(ISP)  
+ Many *client specific interfaces* are *batter than* one general purpose interface.  

+ Clients *should not* be *forced* to depend upon interface that they don't use.  

針對不同的需求，僅開放其對應需求的介面就好  

### ISP基本精神  
+ 不同需求的屬性與方法，放在不同介面中
	+ 不要讓Interface包山包海  
	+ 特定需求沒用到的方法，不要加到介面中  
	+ 可以拿interface當成群組來用(屬性與方法)  

+ 使系統更易達成*鬆散耦合*、*安全重構*、*功能擴充*

> 在實現ISP後，介面會變小、變多

常見問題  
+ 將所有API需求都定義於一個超大介面中  
+ 相依於一堆用不到的介面方法  


<a name="DIP"></a>

## 相依反轉原則(DIP)  
High-level modules should not depend on low-level modules; both should depend on abstractions.
