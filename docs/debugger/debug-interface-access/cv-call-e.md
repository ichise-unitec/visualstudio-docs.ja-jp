---
title: "CV_call_e |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 54447dac0f070ae97cf5b4c6b421c8d6a0e2d44a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="cvcalle"></a>CV_call_e
関数の呼び出し規約を指定します。  
  
> [!NOTE]
>  最も一般的な列挙値のみを次に示します。 完全な列挙体は cvconst.h ヘッダー ファイルで使用できます。  
  
## <a name="syntax"></a>構文  
  
```C++  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## <a name="elements"></a>Elements  
 CV_CALL_NEAR_C  
 Near の右から左へプッシュを使用して関数呼び出し規約を指定します。 呼び出し元の関数では、スタックをクリアします。  
  
 CV_CALL_NEAR_FAST  
 レジスタに近い左から右へプッシュを使用して関数呼び出し規約を指定します。 呼び出された関数では、パラメーターのバイト数の合計を使用して、スタックをクリアします。  
  
 CV_CALL_NEAR_STD  
 Near の標準的な呼び出し (右から左へプッシュ) を使用して関数呼び出し規約を指定します。  
  
 CV_CALL_NEAR_SYS  
 Near のシステム コールを使用して関数呼び出し規約を指定します。  
  
 CV_CALL_THISCALL  
 関数呼び出し規約を使用して、指定`this`呼び出し (`this`レジスタに渡されるポインター)。  
  
 CV_CALL_CLRCALL  
 共通言語ランタイム (CLR) (とも呼ばれる、マネージ コード呼び出し規約) によって使用される関数呼び出し規約を指定します。  
  
## <a name="remarks"></a>コメント  
 この列挙体の値がへの呼び出しによって返される、 [idiasymbol::get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)メソッドです。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: cvconst.h  
  
## <a name="see-also"></a>参照  
 [列挙体と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)