---
title: "プロジェクトの種類を展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2171a940951d828df358d09dae5fec68b6475e4d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-project-types"></a>プロジェクトの種類を展開します。
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]新しいプロジェクトの種類アグリゲーター (ProjectAggregator2.dll) とも再配布 (ProjectAggregator2.msi) 用の Windows インストーラー パッケージをインストールします。 マネージ コード プロジェクトの種類に対して、新しいアグリゲーターを使用する必要があります。 ProjectAggregator2 で策制限の動作、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]プロジェクトのマネージ コード プロジェクトの種類が正しく動作するを防ぐアグリゲーター。 次の手順では、新しいアグリゲーターを使用する VSPackage を変更する方法について説明します。  
  
1.  NativeHierarchyWrapper プロジェクトをソリューションから削除します。  
  
2.  セットアップから NativeHierarchyWrapper バイナリを削除します。  
  
3.  セットアップに ProjectAggregator2.msi を追加します。