---
title: "カスタム プロパティを依存関係のダイアグラムに追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: dependency diagrams, adding custom properties
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 71214e948fcf39d1cf3814ae120eb8f5e42a140a
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2018
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>カスタム プロパティを依存関係のダイアグラムに追加します。
依存関係図の拡張機能のコードを記述するときに、依存関係図の要素と値を格納できます。 値は、図が保存され、再び開かれたときに保持されます。 これらのプロパティに表示することもできます、**プロパティ**ウィンドウのユーザーが表示して編集できるようにします。 たとえば、ユーザーが各レイヤーに正規表現を指定できるようにすることや、各レイヤーのクラスの名前がユーザーが指定したパターンに準拠していることを確認するための検証コードをユーザーが記述できるようにすることができます。  
  
## <a name="properties-not-visible-to-the-user"></a>ユーザーに表示されないプロパティ  
 だけの場合、依存関係ダイアグラム内の要素の値をアタッチするコード、MEF コンポーネントを定義する必要はありません。 `Properties` には <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> という名前のディクショナリがあります。 マーシャリング可能な値を任意のレイヤー要素のディクショナリに単純に追加します。 これらは、依存関係ダイアグラムの一部として保存されます。 詳細については、次を参照してください。[移動し、更新プログラムは、プログラム コード内のモデルをレイヤー](../modeling/navigate-and-update-layer-models-in-program-code.md)です。  
  
## <a name="properties-that-the-user-can-edit"></a>ユーザーが編集できるプロパティ  
 **最初の準備**  
  
> [!IMPORTANT]
>  プロパティが表示されるようにするには、レイヤーのプロパティが表示されるようにする必要のある各コンピューターで、次の変更を行う必要があります。  
>   
>  1.  メモ帳を使用して実行**管理者として実行**です。 `%ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest` を開きます  
> 2.  `Content` 要素内で、次を追加します。  
>   
>     ```xml  
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>  
>     ```  
> 3.  下にある、 **Visual Studio Tools** 、Visual Studio アプリケーション スタート メニューの開いているセクション**開発者コマンド プロンプト**です。  
>   
>      次のように入力します。  
>   
>      `devenv /rootSuffix /updateConfiguration`  
>   
>      `devenv /rootSuffix Exp /updateConfiguration`  
> 4.  Visual Studio を再起動します。  
  
 **コードが VSIX プロジェクトに確認してください。**  
  
 プロパティがコマンド、ジェスチャ、または検証プロジェクトの一部である場合は、何も追加する必要はありません。 カスタム プロパティのコードは、MEF コンポーネントとして定義された Visual Studio 機能拡張プロジェクトで定義する必要があります。 詳細については、次を参照してください。[コマンドおよびジェスチャを図に追加の依存関係](../modeling/add-commands-and-gestures-to-layer-diagrams.md)または[カスタム アーキテクチャ検証を図に追加の依存関係](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)です。  
  
 **カスタム プロパティを定義します。**  
  
 カスタム プロパティを作成するには、次のようなクラスを定義します。  
  
```  
[Export(typeof(IPropertyExtension))]  
public class MyProperty   
      : PropertyExtension<ILayerElement>  
{  
  // Implement the interface.  
}  
```  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> のプロパティまたはその任意の派生クラスのプロパティを定義できます。これには、次のものが含まれます。  
  
-   `ILayerModel` - モデル  
  
-   `ILayer` - 各レイヤー  
  
-   `ILayerDependencyLink` - レイヤー間のリンク  
  
-   `ILayerComment`  
  
-   `ILayerCommentLink`  
  
## <a name="example"></a>例  
 次のコードは、標準的なカスタム プロパティ記述子です。 この例では、Boolean プロパティがレイヤー モデル (`ILayerModel`) で定義されており、ユーザーはこれを使用してカスタム検証メソッドに値を提供できます。  
  
```  
using System;  
using System.ComponentModel.Composition;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
  
namespace MyNamespace  
{  
  /// <summary>  
  /// Custom properties are added to the Layer Designer via a custom  
  /// Property Descriptor. We have to export this Property Descriptor  
  /// using MEF to make it available in the Layer Designer.  
  /// </summary>  
  [Export(typeof(IPropertyExtension))]  
  public class AllTypesMustBeReferencedProperty   
      : PropertyExtension<ILayerModel>  
  {  
    /// <summary>  
    /// Each custom property must have a unique name.   
    /// Usually we use the full name of this class.  
    /// </summary>  
    public static readonly string FullName =  
      typeof(AllTypesMustBeReferencedProperty).FullName;  
  
    /// <summary>  
    /// Construct the property. Notice the use of FullName.  
    /// </summary>  
    public AllTypesMustBeReferencedProperty()  
            : base(FullName)  
    {  }  
  
    /// <summary>  
    /// The display name is shown in the Properties window.  
    /// We therefore use a localizable resource.  
    /// </summary>  
    public override string DisplayName  
    {  
      get { return Strings.AllTypesMustBeReferencedDisplayName; }  
    }  
  
    /// <summary>  
    /// Description shown at the bottom of the Properties window.  
    /// We use a resource string for easier localization.  
    /// </summary>  
    public override string Description  
    {  
      get { return Strings.AllTypesMustBeReferencedDescription; }  
    }  
  
    /// <summary>  
    /// This is called to set a new value for this property. We must  
    /// throw an exception if the value is invalid.  
    /// </summary>  
    /// <param name="component">The target ILayerElement</param>  
    /// <param name="value">The new value</param>  
    public override void SetValue(object component, object value)  
    {  
      ValidateValue(value);  
      base.SetValue(component, value);  
    }  
    /// <summary>  
    /// Helper to validate the value.  
    /// </summary>  
    /// <param name="value">The value to validate</param>  
    private static void ValidateValue(object value)  
    {  }  
  
    public override Type PropertyType  
    { get { return typeof(bool); } }  
  
    /// <summary>  
    /// The segment label of the properties window.  
    /// </summary>  
    public override string Category  
    {   
      get  
      {  
        return Strings.AllTypesMustBeReferencedCategory;  
      }  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>参照  
 [依存関係図の拡張](../modeling/extend-layer-diagrams.md)
