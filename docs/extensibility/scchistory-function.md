---
title: "SccHistory 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccHistory
helpviewer_keywords: SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cf621b3050382d79fcf44df2ac5d50d9885e03d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="scchistory-function"></a>SccHistory 関数
この関数は、指定されたファイルの履歴を表示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvContext`  
 [in]ソース管理プラグイン コンテキスト構造体。  
  
 `hWnd`  
 [in]ソース管理プラグインで提供されるダイアログ ボックスをすべての親として使用できる IDE ウィンドウへのハンドル。  
  
 `nFiles`  
 [in]指定されたファイルの数、`lpFileName`配列。  
  
 `lpFileName`  
 [in]ファイルの完全修飾名の配列。  
  
 `fOptions`  
 [in]コマンド フラグ (現在使用しません)。  
  
 `pvOptions`  
 [in]ソース管理プラグインに固有のオプションです。  
  
## <a name="return-value"></a>戻り値  
 この関数のソース管理プラグイン実装は、次の値のいずれかを返す考えられます。  
  
|[値]|説明|  
|-----------|-----------------|  
|SCC_OK|バージョン履歴が正常に取得されました。|  
|SCC_I_RELOADFILE|ソース管理システムが実際にはディスク上のファイルを変更 (たとえば、取得することによって、古いバージョンの)、履歴をフェッチ中にため、IDE は、このファイルを再読み込みする必要があります。|  
|SCC_E_FILENOTCONTROLLED|ファイルはソース管理されません。|  
|SCC_E_OPNOTSUPPORTED|ソース管理システムでは、この操作はサポートしません。|  
|SCC_E_NOTAUTHORIZED|この操作を実行するユーザーが許可されていません。|  
|SCC_E_ACCESSFAILURE|ソース管理システムのネットワークや競合の問題の可能性があるためのアクセスに関する問題が発生しました。 再試行することをお勧めします。|  
|SCC_E_PROJNOTOPEN|プロジェクトが開かれました。|  
|SCC_E_NONSPECIFICERROR|不特定のエラーです。 ファイル履歴を取得できませんでした。|  
  
## <a name="remarks"></a>コメント  
 ソース管理プラグインは、各ファイルの履歴を表示する、独自のダイアログ ボックスを表示できますを使用して`hWnd`親ウィンドウとします。 または、省略可能なテキストがコールバックを出力に指定された関数、 [SccOpenProject](../extensibility/sccopenproject-function.md)使用できますが、サポートされている場合。  
  
 特定の状況ではこの呼び出しの実行中に検査するファイルが変更可能性がありますに注意してください。 たとえば、[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)]履歴のコマンドは、ファイルの古いバージョンを取得する機会をユーザーに与えます。 このような場合は、ソース管理プラグインを返します`SCC_I_RELOAD`にファイルを再読み込みする必要があることを IDE に警告します。  
  
> [!NOTE]
>  ソース管理プラグインは、配列の場合、ファイルのこの関数をサポートしていない場合、は、最初のファイルのファイル履歴のみを表示できます。  
  
## <a name="see-also"></a>参照  
 [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)