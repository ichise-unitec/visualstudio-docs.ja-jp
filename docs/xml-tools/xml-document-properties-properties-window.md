---
title: "XML ドキュメントのプロパティ、プロパティ ウィンドウ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ceabc30399871c7bbe7fef737e7ecbd87187257d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="xml-document-properties-properties-window"></a>XML ドキュメント プロパティと [プロパティ] ウィンドウ
**プロパティ**ウィンドウは、XML エディターでアクティブになっているドキュメントに関する基本的な情報を提供します。 使用可能なプロパティは、現在アクティブになっている XML ドキュメントの種類によって異なります。  
  
> [!NOTE]
>  XML ドキュメントのプロパティは、すべてソリューション内に保存されます。 このため、ソリューションを次に開いたときにプロパティの値を再入力する必要はありません。  
  
 **エンコーディング**  
 ファイルの文字エンコードです。 このプロパティを変更すると、XML 宣言の encoding 属性も変更されます。逆に、encoding 属性を変更すれば、このプロパティも変更されます。 新しいエンコードは、ファイルを保存する際にファイルをエンコードするために使用されます。  
  
 **入力**  
 XSLT スタイル シートに関連付けられた入力ドキュメントです。 によって使用されている、 **ShowXSLT 出力**コマンド。 参照ボタンを使用してドキュメントを選択することができます (**.**) ボタンをクリックします。  
  
 このプロパティが表示されるのは、XSLT ファイルが現在エディター ウィンドウでアクティブになっている場合のみになります。  
  
 **出力**  
 XML ドキュメントを変換するときに生成されるファイルです。  
  
 ファイルが指定されていない場合は、ファイル拡張子を決定する `method` 要素の `xsl:output` 属性に基づいて既定のファイル名が生成されます。 既定のファイルは、現在のユーザーの一時ディレクトリに置かれます。  
  
 **スキーマ**  
 検証に使用するスキーマです。 ボタンが表示されます、 **XSD スキーマ**ダイアログ ボックスで使用するスキーマを選択するために使用できます。  
  
 スキーマへのパスを入力することもできます。 複数のスキーマを指定する場合は、スキーマのパスをそれぞれ二重引用符で囲む必要があります。  
  
 **スタイル シート**  
 XSLT ファイル、ドキュメントの変換に使用されるときに、 **Show XSLT Output**コマンドを使用します。 このフィールドが空白の場合場合に、 **Show XSLT Output**コマンドを使用して、エディターで指定された値を使用して、`xml-stylesheet`ファイル名の入力を求め、ドキュメントの命令を処理します。  
  
 異なるスタイル シートがであることを指定するこのプロパティを使用する XSLT ファイルを編集するには、際に使用される、 **Show XSLT Output**または**XSLT のデバッグ**コマンドを選択します。 たとえば、親のスタイル シートにインクルードされるスタイル シートを編集しているときに、そのように指定することができます。  
  
## <a name="see-also"></a>参照  
 [XML エディター](../xml-tools/xml-editor.md)   
 [XML エディターのコンポーネント](../xml-tools/xml-editor-components.md)