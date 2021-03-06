---
title: "記号のオブジェクト (JavaScript) |Microsoft ドキュメント"
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
ms.assetid: 2ad059f1-4b7f-4758-882a-c74ce1283ab0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd755d5b753eb91b89b869645287685a97f8f571
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="symbol-object-javascript"></a>Symbol オブジェクト (JavaScript)
一意の識別子を作成することができます。  
  
## <a name="syntax"></a>構文  
  
```  
obj = Symbol(desc)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `desc`  
 省略可能です。 シンボルの説明です。  
  
## <a name="remarks"></a>コメント  
 Symbol オブジェクトを使用して既存のオブジェクトにプロパティを追加すると、既存のオブジェクトのプロパティと干渉する可能性がなく、意図せずに可視になる可能性もなく、他のコードから整合性のない追加が実行される可能性もありません。  
  
 Symbol はプリミティブ データ型です。 Symbol オブジェクトは、`new` 演算子を使用して作成することはできません。  
  
 Symblo オブジェクトをグローバル シンボル レジストリに追加するには、`Symbol.for` 関数と `Symbol.keyFor` 関数を使用します。 シンボルを文字列としてシリアル化する場合は、グローバル シンボル レジストリを使用して、すべての参照で特定の文字列が適正なシンボルに対応するようにします。  
  
 JavaScript には、グローバル スコープで使用できる次の組み込みのシンボル値が含まれています。  
  
|シンボル|説明|  
|------------|-----------------|  
|`Symbol.hasInstance`|このメソッドは、コンス トラクター オブジェクトが、コンス トラクターのインスタンスの 1 つとしてオブジェクトを認識するかどうかを判断します。 これは `instanceof` 演算子によって内部的に使用されます。|  
|`Symbol.isConcatSpreadable`|このプロパティは、オブジェクトが `Array.concat` によって配列要素にフラット化される必要があるかどうかを示すブール値を返します。|  
|`Symbol.iterator`|このメソッドは、オブジェクトの既定の反復子を返します。 これは `for...of` ステートメントによって内部的に使用されます。|  
|`Symbol.toPrimitive`|このメソッドは、オブジェクトを変換して、対応するプリミティブ型の値にします。 これは `ToPrimitive` 抽象化操作で内部的に使用されます。|  
|`Symbol.toStringTag`|このプロパティは、オブジェクトの既定の文字列説明を作成するために使用する文字列値を返します。 これは `Object.toString` 組み込みメソッドによって内部的に使用されます。|  
|`Symbol.unscopables`|このプロパティは、関連オブジェクトの `with` 環境のバインドから除外するプロパティを持つオブジェクトを返します。|  
  
## <a name="functions"></a>Functions  
 `Symbol` オブジェクトの関数を次の表に示します。  
  
|||  
|-|-|  
|プロパティ|説明|  
|[Symbol.for](../../javascript/reference/symbol-for-function-javascript.md)|指定したキーのシンボルを返します。キーが存在しない場合は、新しいキーで新しい symbol オブジェクトを作成します。|  
|[Symbol.keyFor](../../javascript/reference/symbol-keyfor-function-javascript.md)|指定されたシンボルのキーを返します。|  
|||  
  
## <a name="example"></a>例  
  
```JavaScript  
(function() {  
  
    // module-scoped symbol  
    var key = Symbol("description");  
  
    function MyClass(privateData) {  
      this[key] = privateData;  
    }  
  
    MyClass.prototype = {  
      someFunc: function() {  
        return "data: " + this[key];  
      }  
    };  
  
    var c = new MyClass("private data")  
    console.log(key);  
    console.log(c["key"]);  
    console.log(c.someFunc());  
  
})();  
  
// Output:  
// undefined  
// undefined  
// data: private data  
```  
  
## <a name="requirements"></a>要件  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]