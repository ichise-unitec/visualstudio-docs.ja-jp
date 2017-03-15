---
title: "作成して、モーダル ダイアログ ボックスを管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dialog boxes, managing in Visual Studio
ms.assetid: 491bc0de-7dba-478c-a76b-923440e090f3
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 1bb0372ab217847f91b1cdeeb8cf2915379e2f66
ms.lasthandoff: 02/22/2017

---
# <a name="creating-and-managing-modal-dialog-boxes"></a>作成して、モーダル ダイアログ ボックスを管理します。
Visual Studio 内のモーダル ダイアログ ボックスを作成するときに、ダイアログ ボックスが表示されている間に、ダイアログ ボックスの親ウィンドウが無効になっていることを確認し、ダイアログ ボックスを閉じた後に、親ウィンドウを再度有効にする必要があります。 これを行わないと、エラーが表示される場合があります:"Microsoft Visual Studio をシャット ダウンできないモーダル ダイアログ ボックスがアクティブであるためです。 アクティブなダイアログ ボックスを閉じてやり直します。"  
  
 これを行う&2; つの方法があります。 派生するは、WPF ダイアログ ボックスがある場合、ことをお勧め<xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>、まず<xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.ShowModal%2A>ダイアログ ボックスを表示します</xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.ShowModal%2A></xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>。 これを行う場合は、親ウィンドウのモーダルの状態を管理する必要はありません。  
  
 ダイアログ ボックスが、WPF ではない場合や、その他のクラスからのダイアログ ボックスを派生できない理由<xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>を呼び出して、ダイアログ ボックスの親を取得する必要がありますし、<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.GetDialogOwnerHwnd%2A>呼び出すことによって、自分でモーダルの状態を管理し、 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.EnableModeless%2A> ダイアログ ボックスを表示し、ダイアログ ボックスを閉じた後 1 (true) のパラメーターを使用してメソッドを呼び出す前に 0 (false) のパラメーターを持つメソッドです</xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.EnableModeless%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.GetDialogOwnerHwnd%2A></xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>。  
  
## <a name="creating-a-dialog-box-derived-from-dialogwindow"></a>ダイアログ ウィンドウから派生したダイアログ ボックスの作成  
  
1.  という名前の VSIX プロジェクトを作成する**OpenDialogTest**という名前のメニュー コマンドを追加および**ダイアログ**します。 これを行う方法の詳細については、次を参照してください。[メニュー コマンドを使用して拡張機能の作成](../extensibility/creating-an-extension-with-a-menu-command.md)します。  
  
2.  使用する、<xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>クラスでは、次のアセンブリへの参照を追加する必要があります (の フレームワーク タブで、**参照の追加** ダイアログ ボックス):</xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   System.Xaml  
  
3.  次のコードを追加で OpenDialog.cs、`using`ステートメント。  
  
    ```c#  
    using Microsoft.VisualStudio.PlatformUI;  
    ```  
  
4.  という名前のクラスを宣言**TestDialogWindow** <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>::</xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>から派生しました。  
  
    ```c#  
    class TestDialogWindow : DialogWindow  
    {. . .}  
    ```  
  
5.  最小化し、ダイアログ ボックスを最大化するには、次のように設定します<xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMaximizeButton%2A>と<xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMinimizeButton%2A>true:</xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMinimizeButton%2A> </xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasMaximizeButton%2A> 。  
  
    ```c#  
    internal TestDialogWindow()  
    {  
        this.HasMaximizeButton = true;  
        this.HasMinimizeButton = true;  
    }  
    ```  
  
6.  **OpenDialog.ShowMessageBox**メソッドを次に、既存のコードを置き換えます。  
  
    ```c#  
    TestDialogWindow testDialog = new TestDialogWindow();  
    testDialog.ShowModal();  
    ```  
  
7.  アプリケーションをビルドして実行します。 Visual Studio の実験用インスタンスが表示されます。 **ツール**実験用インスタンスのメニューという名前のコマンドを表示する必要があります**呼び出すダイアログ**します。 このコマンドをクリックすると、ダイアログ ウィンドウが表示されます。 最小化し、ウィンドウを最大化することができます。  
  
## <a name="creating-and-managing-a-dialog-box-not-derived-from-dialogwindow"></a>作成と管理ダイアログ ウィンドウから派生していないダイアログ ボックス  
  
1.  この手順で使用することができます、 **OpenDialogTest**は同じアセンブリの参照に、前の手順で作成したソリューションです。  
  
2.  次の追加`using`宣言します。  
  
    ```c#  
    using System.Windows;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    ```  
  
3.  という名前のクラスを作成する**TestDialogWindow2** <xref:System.Windows.Window>::</xref:System.Windows.Window>から派生しました。  
  
    ```c#  
    class TestDialogWindow2 : Window  
    {. . .}  
    ```  
  
4.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>::</xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>にプライベートの参照を追加します。  
  
    ```  
    private IVsUIShell shell;  
    ```  
  
5.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>::</xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>への参照を設定するコンス トラクターを追加します。  
  
    ```c#  
    public TestDialogWindow2(IVsUIShell uiShell)  
    {  
        shell = uiShell;  
    }  
    ```  
  
6.  **OpenDialog.ShowMessageBox**メソッドを次に、既存のコードを置き換えます。  
  
    ```c#  
    IVsUIShell uiShell = (IVsUIShell)ServiceProvider.GetService(typeof(SVsUIShell));  
  
    TestDialogWindow2 testDialog2 = new TestDialogWindow2(uiShell);  
    //get the owner of this dialog  
    IntPtr hwnd;  
    uiShell.GetDialogOwnerHwnd(out hwnd);  
    testDialog2.WindowStartupLocation = System.Windows.WindowStartupLocation.CenterOwner;  
    uiShell.EnableModeless(0);  
    try  
    {  
        WindowHelper.ShowModal(testDialog2, hwnd);  
    }  
    finally  
    {  
        // This will take place after the window is closed.  
        uiShell.EnableModeless(1);  
    }  
    ```  
  
7.  アプリケーションをビルドして実行します。 **ツール**メニューという名前のコマンドを表示する必要があります**呼び出すダイアログ**します。 このコマンドをクリックすると、ダイアログ ウィンドウが表示されます。