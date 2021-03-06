---
title: "Idiadatasource::loaddatafrompdb |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::loadDataFromPdb method
ms.assetid: 02159073-8144-47f8-a0b0-aa0edcb92b5b
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 01348d666b4e6a3b9333a242bb285eff44f5b7c5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="idiadatasourceloaddatafrompdb"></a>IDiaDataSource::loadDataFromPdb
開き、デバッグ データ ソースとしてのプログラム データベース (.pdb) ファイルを用意します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT loadDataFromPdb (  
   LPCOLESTR pdbPath  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pdbPath  
 [in].Pdb ファイルへのパス。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。 次の表は、このメソッドの戻り値を示します。  
  
|[値]|説明|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|開くには、ファイルが失敗したか、ファイル、無効な形式であることを確認します。|  
|E_PDB_FORMAT|旧形式のファイルにアクセスしようとしています。|  
|E_INVALIDARG|無効なパラメーター。|  
|E_UNEXPECTED|データ ソースは、既に準備されています。|  
  
## <a name="remarks"></a>コメント  
 このメソッドは、.pdb ファイルから直接デバッグ データを読み込みます。  
  
 特定の条件に対して .pdb ファイルを検証するを使用して、 [idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)メソッドです。  
  
 アクセスするデータの読み込みプロセス (コールバック機構) を通じてを使用して、 [idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)メソッドです。  
  
 メモリから直接読み込む .pdb ファイルを使用して、 [idiadatasource::loaddatafromistream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)メソッドです。  
  
## <a name="example"></a>例  
  
```C++  
HRESULT hr = pSource->loadDataFromPdb( L"myprog.pdb" );  
if (FAILED(hr))  
{  
    // report error  
}  
```  
  
## <a name="see-also"></a>参照  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiadatasource::loadandvalidatedatafrompdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)