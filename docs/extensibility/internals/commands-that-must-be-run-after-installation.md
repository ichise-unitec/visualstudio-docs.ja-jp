---
title: "インストール後に実行する必要がありますコマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: post-install commands
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2ff4b1e572fd1e0c5c500fbd756d01063665bd1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="commands-that-must-be-run-after-installation"></a>インストール後に実行する必要がありますコマンド
実行する必要があります、.msi ファイルを使用して拡張機能を展開する場合`devenv /setup`で Visual Studio 拡張機能を検出するために、インストールの一部として。  
  
> [!NOTE]
>  このトピックの情報は、Visual Studio 2008 以前のバージョンと DevEnv の検索に適用されます。 以降のバージョンの Visual Studio を DevEnv を検出する方法については、次を参照してください。[システム要件の検出](../../extensibility/internals/detecting-system-requirements.md)です。  
  
## <a name="finding-devenvexe"></a>Devenv.exe を検索します。  
 各バージョンを見つけることができます値をレジストリから devenv.exe [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] RegLocator テーブルと AppSearch テーブルを使用して、プロパティとしてレジストリ値を格納する、インストーラーを記述します。 詳細については、次を参照してください。[システム要件の検出](../../extensibility/internals/detecting-system-requirements.md)です。  
  
### <a name="reglocator-table-rows-to-locate-devenvexe-from-different-versions-of-visual-studio"></a>RegLocator テーブルの行から別のバージョンの Visual Studio の devenv.exe を検索するには  
  
|Signature_|ルート|キー|name|型|  
|-----------------|----------|---------|----------|----------|  
|RL_DevenvExe_2002|2|SOFTWARE\Microsoft\VisualStudio\7.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2003|2|SOFTWARE\Microsoft\VisualStudio\7.1\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2005|2|SOFTWARE\Microsoft\VisualStudio\8.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2008|2|SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS|EnvironmentPath|2|  
  
### <a name="appsearch-table-rows-for-corresponding-reglocator-table-rows"></a>対応する RegLocator テーブル行の AppSearch テーブル行  
  
|プロパティ|Signature_|  
|--------------|-----------------|  
|DEVENV_EXE_2002|RL_DevenvExe_2002|  
|DEVENV_EXE_2003|RL_DevenvExe_2003|  
|DEVENV_EXE_2005|RL_DevenvExe_2005|  
|DEVENV_EXE_2008|RL_DevenvExe_2008|  
  
 たとえば、Visual Studio インストーラーがのレジストリ値を書き込む**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS\EnvironmentPath**として**C:\VS2008\Common7\IDE\devenv.exe**、インストーラーを実行する必要があります実行可能ファイルの完全なパスです。  
  
 **注**RegLocator 型の列は、2 であるために、シグネチャの表に、追加のバージョン情報を指定する必要はありません。  
  
## <a name="running-devenvexe"></a>Devenv.exe を実行しています。  
 インストーラーで標準的なアクションが実行されます AppSearch 後、は、AppSearch テーブル内の各プロパティは、対応するバージョンの Visual Studio の devenv.exe ファイルを指している値を持ちます。 指定されたレジストリ値のいずれかが存在しないかどうか: そのバージョンの Visual Studio がインストールされていないため — 指定したプロパティが設定を null にします。  
  
 カスタム アクションを使用して、プロパティが指している実行可能ファイルを実行する Windows インストーラーのサポートは、50 を入力します。 カスタム アクションに統合する前に、VSPackage が正常にインストールされていることを確認するには、スクリプトの実行オプション、msidbCustomActionTypeInScript (1024) および msidbCustomActionTypeCommit (512) を含める必要があります[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]です。 詳細については、CustomAction テーブルとカスタム アクション スクリプトの実行オプションを参照してください。  
  
 50 の種類のカスタム動作では、ソース列と対象列でコマンドライン引数の値として、実行可能ファイルを含むプロパティを指定します。  
  
### <a name="customaction-table-rows-to-run-devenvexe"></a>Devenv.exe を実行する CustomAction テーブルの行  
  
|アクション|型|ソース|ターゲット|  
|------------|----------|------------|------------|  
|CA_RunDevenv2002|1586|DEVENV_EXE_2002|/setup|  
|CA_RunDevenv2003|1586|DEVENV_EXE_2003|/setup|  
|CA_RunDevenv2005|1586|DEVENV_EXE_2005|/setup|  
|CA_RunDevenv2008|1586|DEVENV_EXE_2008|/setup|  
  
 カスタム アクションは、インストール中に実行するためにスケジュールする InstallExecuteSequence テーブルに記述する必要があります。 場合は、その実行されているカスタム動作を防ぐために、[条件] 列の各行に対応するプロパティを使用してバージョンの[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]システムにインストールされていません。  
  
> [!NOTE]
>  `Null`プロパティに評価される`False`条件で使用するとします。  
  
 各カスタム アクションのシーケンス列の値は、Windows インストーラー パッケージには、その他のシーケンス値に依存します。 シーケンス値は、devenv.exe のカスタム アクションとして実行にできるだけ近い installfinalize が標準的な操作の前にすぐになるようにする必要があります。  
  
### <a name="installexecutesequence-table-to-schedule-the-devenvexe-custom-actions"></a>Devenv.exe のカスタム アクションをスケジュールする InstallExecuteSequence テーブル  
  
|アクション|条件|シーケンス|  
|------------|---------------|--------------|  
|CA_RunDevenv2002|DEVENV_EXE_2002|6602|  
|CA_RunDevenv2003|DEVENV_EXE_2003|6603|  
|CA_RunDevenv2005|DEVENV_EXE_2005|6605|  
|CA_RunDevenv2008|DEVENV_EXE_2008|6608|  
  
## <a name="see-also"></a>参照  
 [Windows インストーラーによる VSPackage のインストール](../../extensibility/internals/installing-vspackages-with-windows-installer.md)