---
title: "UsedCommand 要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 06375b45e21e0b83c62f2509d666b786479ff2b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="usedcommand-element"></a>UsedCommand 要素
他の .vsct ファイルで定義されているコマンドにアクセスする VSPackage を有効にします。 たとえば、VSPackage は、標準を使用して**コピー**で定義されているコマンド、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]シェル、ことができます、コマンドを追加するメニューまたはツールバー再実装しなくてもします。  
  
## <a name="syntax"></a>構文  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|guid|必須。 コマンドを識別する GUID ID のペアの GUID です。|  
|ID|必須。 コマンドを識別する GUID ID のペアの ID。|  
|条件|任意。 参照してください[条件付き属性](../extensibility/vsct-xml-schema-conditional-attributes.md)です。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|なし||  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[UsedCommands 要素](../extensibility/usedcommands-element.md)|UsedCommand 要素をグループ化と他の UsedCommands グループ化します。|  
  
## <a name="remarks"></a>コメント  
 コマンドを追加することによって、`<UsedCommands>`要素、VSPackage に通知、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]環境、VSPackage にコマンドが必要です。 追加する必要があります、`<UsedCommand>`すべてのバージョンと Visual Studio の構成に、パッケージが必要とする任意のコマンドの要素は含まれません可能性があります。 などの場合は、パッケージは、Visual C に固有であるコマンドを呼び出し、コマンドは、するには Visual Web Developer のユーザーが利用できる含める、`<UsedCommand>`コマンドの要素。  
  
## <a name="example"></a>例  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>参照  
 [UsedCommands 要素](../extensibility/usedcommands-element.md)   
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)