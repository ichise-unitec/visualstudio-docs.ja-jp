---
title: MarkProfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MarkProfile
ms.assetid: 54dac8c8-c8ee-4023-af27-b25466e3a6ec
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: b6c88abbca3ba47d4c23d8a60a3643b30669baa6
ms.lasthandoff: 02/22/2017

---
# <a name="markprofile"></a>MarkProfile
`MarkProfile` メソッドは、.vsp ファイルにプロファイル マークを挿入します。 `MarkProfile` 関数を含むスレッドのプロファイル実行は、挿入されるマークについてオンにしておく必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI MarkProfile( long lMarker );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lMarker`  
  
 挿入するマーカー。 マーカーは 0 以上の値にする必要があります。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 関数の成功または失敗は、**PROFILE_COMMAND_STATUS** 列挙型を使って表されます。 戻り値は次のいずれかになります。  
  
|列挙子|説明|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|パラメーターは 0 以下です。 これらの値は予約済みです。 マークとコメントは記録されません。|  
|MARK_ERROR_MODE_NEVER|関数が呼び出されたときに、プロファイル モードが NEVER に設定されました。 マークとコメントは記録されません。|  
|MARK_ERROR_MODE_OFF|関数が呼び出されたときに、プロファイル モードが OFF に設定されました。 マークとコメントは記録されません。|  
|MARK_ERROR_NO_SUPPORT|このコンテキストでマークがサポートされていません。 マークとコメントは記録されません。|  
|MARK_ERROR_OUTOFMEMORY|メモリ不足のため、このイベントを記録できません。 マークとコメントは記録されません。|  
|MARK_TEXTTOOLONG|文字列の長さが最大値の 256 文字を超えています。 コメント文字列は切り詰められ、マークとコメントが記録されます。|  
|MARK_OK|成功した場合は MARK_OK が返されます。|  
  
## <a name="remarks"></a>コメント  
 MarkProfile 関数を含むスレッドにプロファイルが実行される場合、コードが実行されるたびに .vsp ファイルにマーク値が挿入されます。 MarkProfile は複数回呼び出すことができます。  
  
 プロファイル マークは、スコープ内でグローバルです。 たとえば、あるスレッドに挿入したプロファイルマークを、.vsp ファイル内の任意のスレッドで使用し、データ セグメントの開始または終了をマークできます。  
  
 Mark コマンドまたは API 関数 (CommentMarkAtProfile、CommentMarkProfile、または MarkProfile) でマークとコメントが挿入されたとき、マークのプロファイル関数を含むスレッドでは、プロファイル状態をオンにする必要があります。  
  
> [!IMPORTANT]
>  MarkProfile メソッドは、インストルメンテーション プロファイリングでのみ使用してください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>関数の情報  
 ヘッダー : VSPerf.h で宣言  
  
 インポート ライブラリ : VSPerf.lib  
  
## <a name="example"></a>例  
 次のコードは、MarkProfile 関数の使用例を示しています。  
  
```  
void ExerciseMarkProfile()  
{  
    // Declare and initialize variables to pass to   
    // MarkProfile.  The values of these parameters   
    // are assigned based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variables are assigned arbitrary values.  
    int markId = 03;  
  
    // Declare enumeration to hold return value of   
    // call to MarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    markResult = MarkProfile(markId);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("MarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio プロファイラー API リファレンス (ネイティブ)](../profiling/visual-studio-profiler-api-reference-native.md)