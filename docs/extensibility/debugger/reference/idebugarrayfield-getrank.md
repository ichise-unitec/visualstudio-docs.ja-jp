---
title: "IDebugArrayField::GetRank |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayField::GetRank
helpviewer_keywords: IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 786f765e684f720c8c29b91331259e772bd5a007
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
ランクまたは配列の次元数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdwRank`  
 [out]順位を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 配列のランクは、ディメンションの数に対応します。 C++ および C# の場合、多次元配列は配列の配列で、実際には、したがって対象となる 1 次元配列のみ (および`GetRank`メソッドは常に 1 を返します)。 [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]、その一方で、多次元配列の異なる方法で処理およびそのような配列のランクがディメンションの数を表します (および`GetRank`メソッドは常にディメンションの数を返します)。  
  
## <a name="see-also"></a>参照  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)