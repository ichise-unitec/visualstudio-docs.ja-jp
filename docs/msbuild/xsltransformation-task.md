---
title: "XslTransformation タスク | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ac5070e874551aea3880428b106ccb13c7c76c4c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="xsltransformation-task"></a>XslTransformation タスク
XSLT またはコンパイルされた XSLT を利用して XML 入力を変換し、出力デバイスまたはファイルに出力します。  
  
## <a name="parameters"></a>パラメーター  
 `XslTransformation` タスクのパラメーターの説明を次の表に示します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`OutputPaths`|必須の <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型のパラメーターです。<br /><br /> XML 変換の出力ファイルを指定します。|  
|`Parameters`|省略可能な `String` 型のパラメーターです。<br /><br /> XSLT 入力ドキュメントにパラメーターを指定します。|  
|`XmlContent`|省略可能な `String` 型のパラメーターです。<br /><br /> XML 入力を文字列として指定します。|  
|`XmlInputPaths`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型のパラメーターです。<br /><br /> XML 入力ファイルを指定します。|  
|`XslCompiledDllPath`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem> 型のパラメーターです。<br /><br /> コンパイルされた XSLT を指定します。|  
|`XslContent`|省略可能な `String` 型のパラメーターです。<br /><br /> XSLT 入力を文字列として指定します。|  
|`XslInputPath`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem> 型のパラメーターです。<br /><br /> XSLT 入力ファイルを指定します。|  
  
## <a name="remarks"></a>コメント  
 表に示されているパラメーターを使用できるだけでなく、このタスクは <xref:Microsoft.Build.Tasks.TaskExtension> クラスからパラメーターを継承します。このクラス自体は <xref:Microsoft.Build.Utilities.Task> クラスから継承されます。 これらの追加のパラメーターの一覧とその説明については、「 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [タスク](../msbuild/msbuild-tasks.md)   
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)