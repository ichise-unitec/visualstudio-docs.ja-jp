---
title: "VSIX パッケージへの署名 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ec875e6877b1c3ff1edf38b29c5e72b757021085
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2018
---
# <a name="signing-vsix-packages"></a>VSIX パッケージに署名します。
拡張機能アセンブリは、Visual Studio で実行することができますが、これを行うことをお勧めする前に署名する必要はありません。  
  
 拡張機能をセキュリティで保護し、改ざんされていないことを確認する場合は、VSIX パッケージにデジタル署名を追加できます。 VSIX は署名済み、VSIX インストーラーには署名されていること、さらの詳細については、署名自体を示すメッセージが表示されます。 VSIX の内容が変更された、VSIX が再度署名されていない場合は、署名が無効である VSIX インストーラーが表示されます。 インストールは停止されませんが、ユーザーに警告が表示されます。  
  
> [!IMPORTANT]
>  2015 以降で、VSIX パッケージには SHA256 暗号化以外のものを使用して署名が無効なシグネチャを持つものとして示されます。 VSIX のインストールはブロックされませんが、ユーザーに警告が表示されます。  
  
## <a name="signing-a-vsix-with-vsixsigntool"></a>VSIXSignTool で VSIX の署名  
 署名ツールから利用可能な SHA256 暗号化が[VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility)で nuget.org に[VsixSignTool](http://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool)です。  
  
#### <a name="to-use-the-vsixsigntool"></a>VSIXSignTool を使用するには  
  
1.  プロジェクトに、VSIX を追加します。  
  
2.  ソリューション エクスプ ローラーでプロジェクト ノードを右クリックを選択すると**追加 &#124;です。NuGet パッケージの管理**です。  NuGet と NuGet パッケージの参照の追加の詳細についてを参照してください。、 [NuGet のドキュメント](/NuGet)と[パッケージ マネージャー UI](/NuGet/Tools/Package-Manager-UI)トピックです。  
  
3.  VisualStudioExtensibility から VSIXSignTool を検索し、NuGet パッケージをインストールします。  
  
4.  プロジェクトのローカル パッケージの場所から、VSIXSignTool を実行できます。 署名のシナリオでは、ツールのコマンド ライン ヘルプを参照してください (VSIXSignTool.exe/?) です。  
  
 たとえば、パスワードでサインインするために証明書ファイルを保護しました。  
  
 VSIXSignTool.exe 記号/f \<certfile >/p\<パスワード > \<VSIXfile >  
  
## <a name="see-also"></a>参照  
 [Visual Studio 拡張機能の配布](../extensibility/shipping-visual-studio-extensions.md)