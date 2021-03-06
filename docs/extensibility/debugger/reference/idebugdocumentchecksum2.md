---
title: "IDebugDocumentChecksum2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugDocumentChecksum2 interface
ms.assetid: 6d22fa94-21aa-46cb-b5b5-32a6399ebb20
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 50fbee2dbdb30873c97f1ca465d99161add90a19
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentchecksum2"></a>IDebugDocumentChecksum2
デバッグ ドキュメントのチェックサムを表し、コンポーネント間で、チェックサムをやり取りできるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugDocumentChecksum2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 このインターフェイスを公開するすべてのコンポーネントで実装することができます、 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)インターフェイスです。 ただし、主に実装するもののデバッグ エンジン シンボル ファイル (*.pdb) に埋め込まれているチェックサムは、IDE に戻されますしたり、ソースを検索するときに使用できるようにします。  
  
## <a name="methods"></a>メソッド  
 次の表は、メソッドの`IDebugDocumentChecksum2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetChecksumAndAlgorithmId](../../../extensibility/debugger/reference/idebugdocumentchecksum2-getchecksumandalgorithmid.md)|使用するバイトの最大数を指定されたドキュメントのチェックサムおよびアルゴリズム識別子を取得します。|  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll