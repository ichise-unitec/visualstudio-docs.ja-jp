---
title: "方法 : プロジェクトを構成して複数の対象プラットフォームを設定する | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], targeting platforms
- platforms, changing target platforms
ms.assetid: affa2392-7aed-45ac-9ffa-1d8e0496d590
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7686e792d804af85bb8f9588f3ae78fd6b6ec3e3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-projects-to-target-multiple-platforms"></a>方法 : プロジェクトを構成して複数の対象プラットフォームを設定する
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] では、ソリューションは同時に複数の異なる CPU アーキテクチャまたはプラットフォームを対象にすることができます。 これを設定するプロパティには、**[構成マネージャー]** ダイアログ ボックスからアクセスします。  
  
## <a name="targeting-a-platform"></a>プラットフォームを対象にする  
 **[構成マネージャー]** ダイアログ ボックスでは、ソリューション レベルおよびプロジェクト レベルの構成とプラットフォームを作成して設定できます。 ソリューション レベルの構成とターゲットの各組み合わせには一意のプロパティ セットが関連付けられており、簡単に切り替えることができます。たとえば、[!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)] プラットフォームを対象とするリリース構成、x86 プラットフォームを対象とするリリース構成、x86 プラットフォームを対象とするデバッグ構成などです。  
  
#### <a name="to-set-your-configuration-to-target-a-different-platform"></a>異なるプラットフォームを対象とするように構成を設定するには  
  
1.  **[ビルド]** メニューの **[構成マネージャー]** をクリックします。  
  
2.  **[アクティブ ソリューション プラットフォーム]** ボックスでソリューションの対象にするプラットフォームを選ぶか、**[\<新規作成>]** を選んで新しいプラットフォームを作成します。 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] は、**[構成マネージャー]** ダイアログ ボックスでアクティブ プラットフォームとして設定されているプラットフォームを対象とするようにアプリケーションをコンパイルします。  
  
## <a name="removing-a-platform"></a>プラットフォームを削除する  
 対象とする必要がなくなったプラットフォームは、[構成マネージャー] ダイアログ ボックスを使って削除できます。 その構成と対象の組み合わせに対して構成されているすべてのソリューションとプロジェクトの設定が削除されます。  
  
#### <a name="to-remove-a-platform"></a>プラットフォームを削除するには  
  
1.  **[ビルド]** メニューの **[構成マネージャー]** をクリックします。  
  
2.  **[アクティブ ソリューション プラットフォーム]** ボックスで、**[\<編集>]** を選びます。 **[ソリューション プラットフォームの編集]** ダイアログ ボックスが表示されます。  
  
3.  削除するプラットフォームをクリックし、**[削除]** をクリックします。  
  
## <a name="targeting-multiple-platforms-with-one-solution"></a>1 つのソリューションで複数のプラットフォームを対象にする  
 構成とプラットフォームの設定の組み合わせに基づいて設定を変更できるので、複数のプラットフォームを対象とするソリューションを設定することができます。  
  
#### <a name="to-target-multiple-platforms"></a>複数のプラットフォームを対象にするには  
  
1.  **[構成マネージャー]** を使って、少なくとも 2 つの対象プラットフォームをソリューションに追加します。  
  
2.  **[アクティブ ソリューション プラットフォーム]** ボックスの一覧から、対象にするプラットフォームを選びます。  
  
3.  ソリューションをビルドします。  
  
#### <a name="to-build-multiple-solution-configurations-at-once"></a>一度に複数のソリューション構成をビルドするには  
  
1.  **[構成マネージャー]** を使って、少なくとも 2 つの対象プラットフォームをソリューションに追加します。  
  
2.  一度に複数のソリューション構成をビルドするには、**[バッチ ビルド]** ウィンドウを使います。  
  
 ソリューション レベルのプラットフォームをたとえば [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)] に設定し、そのソリューション内のプロジェクトでは同じプラットフォームを対象としない、といったことができます。 また、ソリューション内の複数のプロジェクトで、それぞれ異なるプラットフォームを対象とすることもできます。 いずれかの状況の場合は、混乱を避けるためにわかりやすい名前で新しい構成を作成することをお勧めします。  
  
## <a name="see-also"></a>参照  
 [方法 : 構成を作成および編集する](../ide/how-to-create-and-edit-configurations.md)   
 [ビルド構成について](../ide/understanding-build-configurations.md)   
 [Visual Studio でのプロジェクトとソリューションのビルドおよびクリーン](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)