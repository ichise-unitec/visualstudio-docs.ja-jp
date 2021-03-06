---
title: "要素の分離シェル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: f8d68c3d-9134-4a8f-b566-485956cd321e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 82379a840010ebae434f8ad1a03c12793fe10ec5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="elements-of-the-isolated-shell"></a>Isolated Shell の要素
レジストリ設定、実行時の設定、および分離シェル アプリケーション、およびその .vsct、.pkgdef、and.pkgundef ファイルのアプリケーションのエントリ ポイントを変更することができます。  
  
## <a name="registry-settings"></a>レジストリ設定  
 .Pkgdef、および .pkgundef ファイルの両方は、分離シェル アプリケーションのレジストリ設定を変更します。 このアプリケーションを実行すると、次の順序では、レジストリ設定が定義されています。  
  
 このアプリケーションを実行すると、次の順序では、レジストリ設定が定義されています。  
  
1.  アプリケーションのレジストリ キーが作成されます。  
  
2.  指定したキーとエントリを定義することで、アプリケーションの .pkgdef ファイルから、レジストリが更新されます。  
  
3.  アプリケーションの一部であるパッケージごとに、そのパッケージの .pkgdef ファイルから、レジストリを更新します。 各パッケージは $RootKey$ \Packages によって、アプリケーションの .pkgdef ファイルで定義されている\\{*vsPackageGuid*} パッケージのキー。  
  
4.  AppEnvConfig.pkgdef と BaseConfig.pkgdef 内から、レジストリを更新、 *Visual Studio SDK インストール パス*\Common7\IDE\ShellExtensions\Platform ディレクトリ。 これらのファイルは、Visual Studio の一部も、Visual Studio Shell (分離モード) の再頒布可能パッケージの一部です。  
  
5.  指定したキーとエントリを削除することで、アプリケーションの .pkgundef ファイルから、レジストリが更新されます。  
  
## <a name="run-time-settings"></a>実行時の設定  
 ユーザーは、分離シェル アプリケーションを起動するときに、Visual Studio シェルの開始のエントリ ポイントを呼び出します。 アプリケーションの設定は、アプリケーションの起動時に、次のように定義されています。  
  
1.  Visual Studio シェルは、特定のキーのアプリケーションのレジストリをチェックします。 キーの設定が、開始のエントリ ポイントへの呼び出しで指定されている場合、その値は、レジストリの値をオーバーライドします。  
  
2.  レジストリにも、エントリ ポイントと、パラメーター、設定の値を指定し、設定の既定値を使用します。  
  
 ユーザーは、コマンドラインから、アプリケーションを起動するときに、すべてのコマンド ライン スイッチは、Visual Studio シェル、Devenv は同じ方法で扱うに渡されます。 Devenv のスイッチの詳細については、次を参照してください。 [Devenv コマンド ライン スイッチ](../../ide/reference/devenv-command-line-switches.md)と[VSPackage の開発の Devenv コマンド ライン スイッチ](../devenv-command-line-switches-for-vspackage-development.md)です。 コマンド ライン スイッチ用のパッケージを登録する方法の詳細については、次を参照してください。[コマンド ライン スイッチを追加する](../adding-command-line-switches.md)です。  
  
## <a name="the-start-entry-point"></a>開始のエントリ ポイント  
 Appenvstub.dll ファイルには、分離シェルにアクセスするためのエントリ ポイントが含まれています。 アプリケーションの起動時に Appenvstub.dll の開始のエントリ ポイントを呼び出します。  
  
 アプリケーションの動作を変更するには、開始のエントリ ポイントに渡される最後のパラメーターの値を変更します。 詳細については、次を参照してください。[分離シェルのエントリ ポイントのパラメーター (C++)](isolated-shell-entry-point-parameters-cpp.md)です。  
  
## <a name="the-vsct-file"></a>します。Vsct ファイル  
 .Vsct ファイルでは、どの標準的な Visual Studio の UI 要素は、アプリケーションで使用可能なを指定できます。 詳細については、次を参照してください。[です。Vsct ファイル](modifying-the-isolated-shell-by-using-the-dot-vsct-file.md)です。  
  
## <a name="the-pkgundef-file"></a>します。Pkgundef ファイル  
 アプリケーションが Visual Studio が既にインストールされているコンピューターにインストールされている場合は、アプリケーションの Visual Studio のレジストリ エントリのコピーが行われます。 既定では、アプリケーションは、コンピューターに既にインストールされている Vspackage を使用します。 .Pkgundef ファイルでは、アプリケーションから Visual Studio シェルまたは拡張機能の特定の要素を削除するためにレジストリ エントリを除外できます。 詳細については、次を参照してください。[です。Pkgundef ファイル](modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)です。  
  
 .Pkgundef ファイルでは、アプリケーションから Visual Studio シェルまたは拡張機能の特定の要素を削除するためにレジストリ エントリを除外できます。 詳細については、次を参照してください。[です。Pkgundef ファイル](modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)です。  
  
 パッケージを除外する Guid のセットは、「[パッケージ Guid の Visual Studio の機能](package-guids-of-visual-studio-features.md)します。  
  
## <a name="the-pkgdef-file"></a>します。Pkgdef ファイル  
 .Pkgdef ファイルを使用して、アプリケーションがインストールされているときに設定されているアプリケーションのレジストリ エントリを定義できます。 .Pkgdef ファイルの説明と、Visual Studio シェルを使用するレジストリ エントリの一覧は、次を参照してください。[です。Pkgdef ファイル](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)です。  
  
## <a name="substitution-strings"></a>代替文字列  
 .Pkgdef および .pkgundef ファイルで使用される代替文字列は、「[で置換文字列を使用します。Pkgdef およびです。Pkgundef ファイル](substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md)です。  
  
## <a name="other-settings"></a>その他の設定  
 分離シェル アプリケーションは、Microsoft.VisualStudio.GraphModel.dll に依存する場合は、分離シェル アプリケーションの .config ファイルに次のバインド リダイレクトを追加する必要があります。  
  
```  
<dependentAssembly>  
    <assemblyIdentity name="Microsoft.VisualStudio.GraphModel" publicKeyToken="b03f5f7f11d50a3a" culture="neutral" />  
    <bindingRedirect oldVersion="11.0.0.0" newVersion="12.0.0.0"/>  
</dependentAssembly>  
  
```