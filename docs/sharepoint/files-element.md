---
title: "要素のファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Files element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 609bd9e590362efefbabcc79fd910eef3653ff92
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="files-element"></a>Files 要素
  フィーチャー要素ファイルなど、SharePoint プロジェクト項目と依存する以外の SharePoint プロジェクトの出力を配置するファイルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>型  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|省略可能な**ProjectItemFileType**要素。<br /><br /> フィーチャー要素ファイルが SharePoint に展開するときに、プロジェクト項目に含めるなどの SharePoint ファイルを表します。|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|省略可能な**ProjectOutputFileType**要素。<br /><br /> SharePoint に配置されるときに、プロジェクト項目に含めるプロジェクトの出力を表します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|SharePoint プロジェクト項目を表します。 .Spdata ファイルの必要なルート要素です。|  
  
## <a name="element-information"></a>要素情報  
  
|||  
|-|-|  
|**名前空間**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**スキーマ名**|SharePoint プロジェクト項目のスキーマ|  
|**検証ファイル**|ProjectItemModelSchema.xsd|  
|**空にすることができます。**|×|  
  
## <a name="see-also"></a>参照  
 [SharePoint プロジェクト項目スキーマのリファレンス](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  