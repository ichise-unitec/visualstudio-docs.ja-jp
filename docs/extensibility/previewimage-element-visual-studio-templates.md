---
title: "PreviewImage 要素 (Visual Studio テンプレート) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<PreviewImage> 要素 (Visual Studio テンプレート)"
  - "PreviewImage 要素 (Visual Studio テンプレート)"
ms.assetid: d1796f20-523b-4e0d-8ac3-ca87f3b5a9b6
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# PreviewImage 要素 (Visual Studio テンプレート)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**\[新しいプロジェクト\]** ダイアログ ボックスまたは **\[新しい項目の追加\]** ダイアログ ボックスに表示されるプレビュー イメージをファイル名で指定します。  
  
## 構文  
  
```  
<PreviewImage>"filename"</PreviewImage>  
```  
  
## 属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### 属性  
 なし。  
  
### 子要素  
 なし。  
  
### 親要素  
  
|要素|説明|  
|--------|--------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必須の要素。<br /><br /> テンプレートをカテゴリに分類し、**\[新しいプロジェクト\]** ダイアログ ボックス、または **\[新しい項目の追加\]** ダイアログ ボックスでどのように表示させるかを定義します。|  
  
## テキスト値  
 テキスト値が必要です。  
  
 このテキストはファイル名を表す文字列である必要があります。  
  
## 解説  
 `PreviewImage` は、省略可能な要素です。  
  
## 参照  
 [Visual Studio テンプレート スキーマ参照](../extensibility/visual-studio-template-schema-reference.md)   
 [カスタム プロジェクトと項目テンプレートの作成](../ide/creating-project-and-item-templates.md)