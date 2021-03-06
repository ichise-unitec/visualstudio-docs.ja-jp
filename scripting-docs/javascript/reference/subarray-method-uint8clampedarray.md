---
title: "subarray メソッド (Uint8ClampedArray) |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 309ed9e8-5805-47ab-b3ed-501cae1323dd
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76cda8b123b02b4c19a7fd162f3bfbce4540d149
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="subarray-method-uint8clampedarray"></a>subarray メソッド (Uint8ClampedArray)
新しい取得[Uint8ClampedArray](../../javascript/reference/uint8array-object.md)の表示、 [ArrayBuffer](../../javascript/reference/arraybuffer-object.md)サブ配列の最初と最後のメンバーを指定し、この配列に格納します。  
  
## <a name="syntax"></a>構文  
  
```JavaScript  
var newUint8ClampedArray = uint8ClampedArray.subarray(begin, end);  
```  
  
## <a name="parameters"></a>パラメーター  
 `newUint8ClampedArray`  
 必須です。 このメソッドによって返されるサブ配列。  
  
 `begin`  
 省略可能です。 配列の先頭のインデックス。  
  
 `end`  
 省略可能です。 配列の末尾のインデックス。 これは、内包的ではありません。  
  
## <a name="remarks"></a>コメント  
 `begin` または `end` が負の場合は、配列の先頭からではなく配列の末尾からのインデックスを参照します。 `end` が指定されていない場合、サブ配列には、型指定された配列の `begin` から末尾までのすべての要素が含まれます。 `begin` 値および `end` 値で指定された範囲は、現在の配列の有効なインデックスの範囲に固定されます。 新しい型指定された配列の計算された長さが負の場合は、ゼロに固定されます。 返される配列は、このメソッドが呼び出される配列と同じ型になります。  
  
## <a name="example"></a>例  
 次の例は、配列の先頭の要素から開始して、長さが要素 2 つ分のサブ配列を取得する方法を示しています。  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>要件  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [Uint8Array オブジェクト](../../javascript/reference/uint8array-object.md)   
 [ArrayBuffer オブジェクト](../../javascript/reference/arraybuffer-object.md)   
 [Uint8ClampedArray オブジェクト](../../javascript/reference/uint8clampedarray-object-javascript.md)