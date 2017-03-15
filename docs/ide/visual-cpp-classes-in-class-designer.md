---
title: "Visual C++ Classes in Class Designer | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.classdesigner.inheritancelinelabel"
helpviewer_keywords: 
  - "Class Designer [Visual Studio], classes"
ms.assetid: 75e56f8c-11ef-42a3-b7ec-3d2cf25c581b
caps.latest.revision: 19
caps.handback.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Visual C++ Classes in Class Designer
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

クラス デザイナーは C\+\+ クラスをサポートし、Visual Basic および Visual C\# クラスの図形と同じ方法でネイティブ C\+\+ クラスを視覚化します。ただし、C\+\+ クラスは複数の継承関係を持つことができる点が異なります。  クラスの図形を展開して、表示されるクラスのフィールドとメソッドを増やしたり、図形を折りたたんでスペースを広くしたりすることができます。  
  
> [!NOTE]
>  クラス デザイナーは共用体 \(共用体の最大データ メンバーに必要な量のメモリしか割り当てられない特殊なタイプのクラス\) はサポートしていません。  
  
## 単純な継承  
 クラス ダイアグラムに複数のクラスをドラッグするときに、これらのクラスにクラス継承関係があると、矢印によって各クラスが接続されます。  矢印は、基本クラスの方向を指し示します。  たとえば、クラス ダイアグラムに以下のクラスが表示される場合、矢印によって各クラスが接続され、B から A が指し示されます。  
  
```  
class A {};  
class B : A {};  
```  
  
 また、クラス ダイアグラムに B クラスのみをドラッグしてから、B のクラス図形を右クリックして、**\[基本クラスの表示\]** をクリックすることもできます。  このようにすると、基本クラスである A が表示されます。  
  
## 多重継承  
 クラス デザイナーは、複数クラスの継承関係の視覚化をサポートしています。  *多重継承*は、派生クラスが、複数の基本クラスの属性を持つときに使用されます。  次に示すのは、多重継承の例です。  
  
```  
class Bird {};  
class Swimmer {};  
class Penguin : public Bird, public Swimmer {};  
```  
  
 クラス ダイアグラムに複数のクラスをドラッグするときに、これらのクラスに複数クラスの継承関係があると、矢印によって各クラスが接続されます。  矢印は、基本クラスの方向を指し示します。  
  
 クラスの図形を右クリックして **\[基本クラスの表示\]** をクリックすると、選択したクラスの基本クラスが表示されます。  
  
> [!NOTE]
>  **\[派生クラスの表示\]** コマンドは、C\+\+ コードについてはサポートされていません。  派生クラスは、\[クラス ビュー\] を開き、型ノードを展開し、**\[派生型\]** サブフォルダーを展開してからこれらの型をクラス ダイアグラムにドラッグすると表示できます。  
  
 複数クラスの継承の詳細については、「[\(NOTINBUILD\) Multiple Inheritance](http://msdn.microsoft.com/ja-jp/3b74185e-2beb-4e29-8684-441e51d2a2ca)」および「[複数の基本クラス](/visual-cpp/cpp/multiple-base-classes)」を参照してください。  
  
## 抽象クラス  
 クラス デザイナーは、抽象クラス \("抽出基本クラス" とも呼ばれます\) をサポートしています。  これらは、インスタンス化されることはありませんが、他のクラスを派生させることができるクラスです。  このドキュメントで既に説明した「多重継承」の例を使用すると、次のように、`Bird` クラスを個々のオブジェクトとしてインスタンス化できます。  
  
```  
int main()  
{  
   Bird sparrow;  
   Bird crow;  
   Bird eagle;  
}  
```  
  
 ただし、`Swimmer` クラスを個々のオブジェクトとしてインスタンス化するわけではありません。  そこから、`Penguin`、`Whale`、および `Fish` などのその他の種類の動物クラスを派生させるだけです。  この場合、`Swimmer` クラスを抽象基本クラスとして宣言することになります。  
  
 クラスを抽象として宣言するには、`abstract` キーワードを使用できます。  抽象としてマークされているメンバー、または抽象クラスのメンバーは、仮想であり、抽象クラスから派生したクラスを使用して実装する必要があります。  
  
```  
class Swimmer abstract  
{  
   virtual void swim();  
   void dive();  
};  
```  
  
 1 つ以上の純粋仮想関数を含めることで、クラスを抽象として宣言することもできます。  
  
```  
class Swimmer  
{  
   virtual void swim() = 0;  
   void dive();  
};  
```  
  
 これらの宣言をクラス ダイアグラムで表示すると、クラス名の `Swimmer` とその純粋仮想関数である `swim` は、抽象クラスのシェイプで、**\[抽象クラス\]** 表記と共に斜体で表示されます。  抽象クラスの型シェイプは、その境界線が点線であることを除いて、通常のクラスと同じです。  
  
 抽象基本クラスからの派生クラスは、基本クラスの各純粋仮想関数をオーバーライドする必要があります。オーバーライドしない場合、派生クラスをインスタンス化できません。  そのため、たとえば、`Fish` クラスを `Swimmer` クラスから派生させた場合、`Fish` は、`swim` メソッドをオーバーライドする必要があります。  
  
```  
class Fish : public Swimmer  
{  
   void swim(int speed);  
};  
  
int main()  
{  
   Fish guppy;  
}  
```  
  
 このコードをクラス ダイアグラムで表示させると、クラス デザイナーは、`Fish` から `Swimmer` へ継承線を描画します。  
  
## 匿名クラス  
 クラス デザイナーは、匿名クラスをサポートしています。  *匿名クラス型*は、識別子なしで宣言されるクラスです。  これはコンストラクターもデストラクターも持てず、引数として関数に渡すこともできず、関数からの戻り値として戻すこともできません。  匿名クラスを使用して、次の例のように、クラス名を typedef 名に置き換えることができます。  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
 構造体も匿名にできます。  クラス デザイナーは、匿名クラスと匿名構造体を、それぞれの型を表示するのと同じ方法で表示します。  匿名クラスと匿名構造体は宣言および表示が可能できますが、クラス デザイナーはユーザーが指定したタグ名を使用せず、  クラス ビューが生成する名前を使用します。  クラス ビューおよびクラス デザイナーでは、クラスまたは構造体は、**\_\_unnamed** という要素として表示されます。  
  
 匿名クラスの詳細については、「[匿名クラス型](/visual-cpp/cpp/anonymous-class-types)」を参照してください。  
  
## テンプレート クラス  
 クラス デザイナーは、テンプレート クラスの視覚化をサポートしています。  入れ子になった宣言がサポートされています。  次の表は、一般的な宣言を示しています。  
  
|コード要素|\[クラス デザイナー\] ビュー|  
|-----------|-----------------------|  
|`template <class T>`<br /><br /> `class A {};`|`A<T>`<br /><br /> テンプレート クラス|  
|`template <class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> テンプレート クラス|  
|`template <class T, int i>`<br /><br /> `class A {};`|`A<T, i>`<br /><br /> テンプレート クラス|  
|`template <class T, template <class K> class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> テンプレート クラス|  
  
 次の表は、部分的特殊化の例です。  
  
|コード要素|\[クラス デザイナー\] ビュー|  
|-----------|-----------------------|  
|`template<class T, class U>`<br /><br /> `class A {};`|`A<T, U>`<br /><br /> テンプレート クラス|  
|`template<class T>`<br /><br /> `class A<T, T> {};`|`A<T, T>`<br /><br /> テンプレート クラス|  
|`template <class T>`<br /><br /> `class A<T, int> {};`|`A<T, int>`<br /><br /> テンプレート クラス|  
|`template <class T1, class T2>`<br /><br /> `class A<T1*, T2*> {};`|`A<T1*, T2*>`<br /><br /> テンプレート クラス|  
  
 次の表は、部分的特殊化における継承の例です。  
  
|コード要素|\[クラス デザイナー\] ビュー|  
|-----------|-----------------------|  
|`template <class T, class U>`<br /><br /> `class A {};`<br /><br /> `template <class TC>`<br /><br /> `class A<T, int> {};`<br /><br /> `class B : A<int, float>`<br /><br /> `{};`<br /><br /> `class C : A<int, int>`<br /><br /> `{};`|`A<T, U>`<br /><br /> テンプレート クラス<br /><br /> `B`<br /><br /> Class<br /><br /> \(A クラスを指します\)<br /><br /> `C`<br /><br /> Class<br /><br /> \(A クラスを指します\)|  
  
 次の表は、部分的特殊化テンプレート関数の例です。  
  
|コード要素|\[クラス デザイナー\] ビュー|  
|-----------|-----------------------|  
|`class A`<br /><br /> `{`<br /><br /> `template <class T, class U>`<br /><br /> `void func(T a, U b);`<br /><br /> `template <class T>`<br /><br /> `void func(T a, int b);`<br /><br /> `};`|`A`<br /><br /> func\<T, U\> \(\+ 1 overload\)|  
|`template <class T1>`<br /><br /> `class A {`<br /><br /> `template <class T2>`<br /><br /> `class B {};`<br /><br /> `};`<br /><br /> `template<> template<>`<br /><br /> `class A<type>::B<type> {};`|`A<T1>`<br /><br /> テンプレート クラス<br /><br /> `B<T2>`<br /><br /> テンプレート クラス<br /><br /> \(B は、**\[入れ子にされた型\]** の下の A クラスの中に含まれます\)|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `class A : C<int> {};`|`A`<br /><br /> Class<br /><br /> \-\> C\<int\><br /><br /> `C<T>`<br /><br /> テンプレート クラス|  
  
 次の表は、テンプレート継承の例です。  
  
|コード要素|\[クラス デザイナー\] ビュー|  
|-----------|-----------------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {`<br /><br /> `class B {};`<br /><br /> `}`<br /><br /> `class A : C<int>::B {};`|`A`<br /><br /> Class<br /><br /> \-\>B<br /><br /> `C<int>`<br /><br /> Class<br /><br /> \(B は、**\[入れ子にされた型\]** の下の C クラスの中に含まれます。\)<br /><br /> `C<T>`<br /><br /> テンプレート クラス|  
  
 次の表は、標準特殊クラス接続の例です。  
  
|コード要素|\[クラス デザイナー\] ビュー|  
|-----------|-----------------------|  
|`template <class T>`<br /><br /> `class C {};`<br /><br /> `template<>`<br /><br /> `class C<int> {};`<br /><br /> `class A : C<int> {};`<br /><br /> `class D : C<float> {};`|`A`<br /><br /> Class<br /><br /> \-\>C\<int\><br /><br /> `C<int>`<br /><br /> Class<br /><br /> `C<T>`<br /><br /> テンプレート クラス<br /><br /> `D`<br /><br /> Class<br /><br /> \-\>C\<float\>|  
|`class B {`<br /><br /> `template <class T>`<br /><br /> `T min (const T &a, const T &b);`<br /><br /> `};`|`B`<br /><br /> min \<T\>|  
  
## 参照  
 [Working with Visual C\+\+ Code \(Class Designer\)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [クラスと構造体](/visual-cpp/cpp/classes-and-structs-cpp)   
 [匿名クラス型](/visual-cpp/cpp/anonymous-class-types)   
 [\(NOTINBUILD\) Multiple Inheritance](http://msdn.microsoft.com/ja-jp/3b74185e-2beb-4e29-8684-441e51d2a2ca)   
 [複数の基本クラス](/visual-cpp/cpp/multiple-base-classes)   
 [テンプレート](/visual-cpp/cpp/templates-cpp)