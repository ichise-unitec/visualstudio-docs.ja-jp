---
title: "方法: CD インストールの自動開始を有効にする |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, AutoStart
- ClickOnce deployment, installation on CD or DVD
- deploying applications [ClickOnce], installation on CD or DVD
ms.assetid: caaec619-900c-4790-90e3-8c91f5347635
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: e830e1be1b7b36e53fd45bc11457452db805ae02
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-autostart-for-cd-installations"></a>方法 : CD インストールの自動開始を有効にする
展開するときに、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] CD-ROM または DVD-ROM などのリムーバブル メディアを使用してアプリケーションを有効にできます`AutoStart`できるように、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]メディアが挿入されると、アプリケーションが自動的に起動します。  
  
 `AutoStart`有効にすることができます、**発行**のページ、**プロジェクト デザイナー**です。  
  
### <a name="to-enable-autostart"></a>自動開始を有効にするには  
  
1.  **ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]**をクリックします。  
  
2.  クリックして、**発行**タブです。  
  
3.  クリックして、**オプション**ボタンをクリックします。  
  
     **発行オプション** ダイアログ ボックスが表示されます。  
  
4.  をクリックして**展開**です。  
  
5.  選択、**の CD からインストール、自動的に開始セットアップ CD が挿入される**チェック ボックスをオンします。  
  
     Autorun.inf ファイルは、アプリケーションを発行するときに、発行場所にコピーされます。  
  
## <a name="see-also"></a>参照  
 [ClickOnce アプリケーションの発行](../deployment/publishing-clickonce-applications.md)   
 [方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)