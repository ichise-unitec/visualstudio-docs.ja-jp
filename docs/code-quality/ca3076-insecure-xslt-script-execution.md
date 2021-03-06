---
title: "Ca 3076: 安全ではない XSLT スクリプトの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53cb7a46-c564-488f-bc51-0e210a7853c9
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 09cf5533bff2eb2254f3ca70d4dea275c9354201
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: 安全ではない XSLT スクリプトの実行
|||  
|-|-|  
|TypeName|InsecureXSLTScriptExecution|  
|CheckId|CA3076|  
|カテゴリ|Microsoft.Security|  
|互換性に影響する変更点|中断なし|  
  
## <a name="cause"></a>原因  
 実行する場合[XSLT Extensible Stylesheet Language Transformation ()](https://support.microsoft.com/en-us/kb/313997) .NET アプリケーションでセキュリティ上の危険なプロセッサが参照を解決する信頼されていない URI につながる攻撃者に機密情報を漏えいする可能性サービスやクロスサイト攻撃の拒否します。  
  
## <a name="rule-description"></a>規則の説明  
 **XSLT** XML データを変換するための World Wide Web Consortium (W3C) 標準です。 通常 XSLT は、XML データを他の形式 (HTML、固定長のテキスト、コンマ区切りのテキスト、または別の XML 形式など) に変換するために、スタイル シートを書き込むのに使用します。 既定では禁止になっていますが、プロジェクトに応じて有効にもできます。  
  
 攻撃にさらされないようにするため、悪意あるスクリプトの処理を許してしまうような、<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> と <xref:System.Xml.Xsl.XsltSettings> のインスタンスの安全ではない組み合わせを XslCompiledTransform. <xref:System.Xml.XmlResolver>が受け取った場合には常に、このルールがトリガーされます。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
  
-   安全ではない XsltSettings 引数を XsltSettings.<xref:System.Xml.Xsl.XsltSettings.Default%2A> と置き換えます。または、document 関数とスクリプトの実行を無効にしたインスタンスに置き換えます。  
  
-   <xref:System.Xml.XmlResolver> 引数を null または <xref:System.Xml.XmlSecureResolver> インスタンスに置き換えます。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 入力が信頼できるソースからのものとわかっているのでない限り、この警告からのルールを抑制しないでください。  
  
## <a name="pseudo-code-examples"></a>疑似コードの例  
  
### <a name="violation"></a>違反  
  
```csharp  
using System.Xml;  
using System.Xml.Xsl;  
  
namespace TestNamespace   
{   
    class TestClass   
    {  
         void TestMethod()   
        {    
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
             var settings = XsltSettings.TrustedXslt;   
             var resolver = new XmlUrlResolver();   
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
        }  
    }   
}   
```  
  
### <a name="solution"></a>ソリューション  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        void TestMethod()   
        {   
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
            var settings = XsltSettings.Default;   
            var resolver = new XmlUrlResolver();   
            xslCompiledTransform.Load("testStylesheet", settings, resolver);   
        }   
    }   
}  
```  
  
### <a name="violation"></a>違反  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)   
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
                var resolver = new XmlUrlResolver();   
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
            }   
            catch { throw; }   
            finally { }   
        }   
    }   
}  
```  
  
### <a name="solution"></a>ソリューション  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)   
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
                settings.EnableDocumentFunction = false;   
                settings.EnableScript = false;   
                var resolver = new XmlUrlResolver();   
                xslCompiledTransform.Load("testStylesheet", settings, resolver);   
            }   
            catch { throw; }   
            finally { }   
        }   
    }   
}  
```