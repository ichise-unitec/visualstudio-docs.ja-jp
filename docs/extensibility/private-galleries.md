---
title: "プライベート ギャラリー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX galleries, private
- private galleries, VSIX
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5226ff7a4ed77333d2a6f9287f129c6a6d754cac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="private-galleries"></a>Private Galleries
コントロール、テンプレート、および投稿することにで開発したツールを共有することができます、*プライベート ギャラリー*次のように、組織のイントラネット上。  
  
-   Atom (RSS) フィードをイントラネット上の適切に構成されているの一元化された場所 (リポジトリ) を作成します。 詳細については、次を参照してください。[する方法: プライベート ギャラリー用の Atom フィードを作成](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md)です。  
  
-   プライベート ギャラリーを記述する .pkgdef ファイルを配布します。 プライベート ギャラリーを同時に多数のコンピューターに接続する管理者向けのこの構成はお勧めします。  
  
## <a name="adding-a-private-gallery-to-extensions-and-updates-in-visual-studio"></a>拡張機能と Visual Studio での更新プログラムへのプライベート ギャラリーの追加  
 プライベート ギャラリーを使用できる場合にそれを追加できます**拡張機能と更新プログラム**Visual Studio でします。  
  
 ![[追加] ダイアログの拡張機能マネージャー](../extensibility/media/em_adddialog.png "EM_AddDialog")  
  
#### <a name="to-add-a-private-gallery-to-extensions-and-updates"></a>プライベート ギャラリーの拡張機能と更新プログラムを追加するには  
  
1.  メニュー バーの **[ツール]**、 **[オプション]**の順にクリックします。  
  
2.  **環境**ノード、**拡張機能と更新プログラム**です。  
  
3.  **[追加]** ボタンをクリックします。  
  
4.  **名前**フィールドに、たとえば、プライベート ギャラリーの名前を入力`My Gallery`です。  
  
5.  **URL**フィールドに、Atom フィードまたはプライベート ギャラリーをホストしている SharePoint サイトの URL を入力します。  
  
    1.  プライベート ギャラリーに接続するホストが Atom フィードである場合は、この URL のようになります: http://www.mywebsite/mygallery/atom.xml です。  この URL は、ファイルまたはネットワーク パスを参照できます。  
  
    2.  ホストが、SharePoint サイトの場合は、URL はのようにこのいずれか: http://mysharepoint/sites/mygallery/forms/AllItems.aspx です。  
  
### <a name="managing-private-galleries"></a>プライベート ギャラリーの管理  
 管理者ことができますをプライベート ギャラリーを使用できるように複数のコンピューター、同時に各コンピューターでシステム レジストリを変更します。 これを実現するには、新しいレジストリ キーとその値を記述する .pkgdef ファイルを作成します。  このファイルの形式は次のとおりです。  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 詳細については、次を参照してください。[する方法:、プライベート ギャラリーを使用してレジストリ設定を管理](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md)です。  
  
## <a name="installing-extensions-from-a-private-gallery"></a>プライベート ギャラリーから拡張機能をインストールします。  
 検索およびプライベート ギャラリーから Visual Studio 拡張機能をインストールすることができます**拡張機能と更新プログラム**です。 次の手順がという名前のプライベート ギャラリーを使用して`My Gallery`です。  
  
 ![プライベート ギャラリーをインストールする拡張機能マネージャー](../extensibility/media/em_.png "EM_")  
  
#### <a name="to-search-for-and-install-extensions-from-a-private-gallery"></a>検索し、プライベート ギャラリーから拡張機能のインストール  
  
1.  メニュー バーで、**[ツール]**、**[拡張機能と更新プログラム]** の順にクリックします。  
  
2.  左のペインで選択**オンラインの拡張機能**、し、**マイ ギャラリー**です。  
  
3.  右側のウィンドウで、拡張機能を選択し、、**ダウンロード**ボタンをクリックします。  
  
## <a name="updating-extensions-from-a-private-gallery"></a>プライベート ギャラリーから拡張機能の更新  
 Visual Studio 拡張機能の新しいバージョンは、プライベート ギャラリーにポストされて、インストールされている拡張機能を更新できます。 次の手順がという名前のプライベート ギャラリーを使用して`My Repository`です。  
  
 ![拡張機能マネージャーのプライベート ギャラリーの更新](../extensibility/media/em_update.png "EM_Update")  
  
#### <a name="to-update-an-installed-extension-from-a-private-gallery"></a>プライベート ギャラリーからインストールされている拡張機能を更新するには  
  
1.  メニュー バーで、**[ツール]**、**[拡張機能と更新プログラム]** の順にクリックします。  
  
2.  左のペインで選択**更新**、し、**マイ リポジトリ**です。  
  
3.  右側のウィンドウで、拡張機能を選択し、、**更新**ボタンをクリックします。  
  
## <a name="see-also"></a>参照  
 [検索と Visual Studio 拡張機能の使用](../ide/finding-and-using-visual-studio-extensions.md)   
 [Visual Studio 拡張機能の配布](../extensibility/shipping-visual-studio-extensions.md)