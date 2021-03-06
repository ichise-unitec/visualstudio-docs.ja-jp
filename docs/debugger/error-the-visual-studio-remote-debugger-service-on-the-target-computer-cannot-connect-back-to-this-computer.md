---
title: "エラー: 対象のコンピューター上の Visual Studio リモート デバッガー サービスは、このコンピューターに接続できない |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.service_access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f4553bceb8757b49c6d21f4bbe85e47f90e5b4dc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>エラー : 対象コンピューター上の Visual Studio リモート デバッガーが、このコンピューターに接続できません。
このエラーは、Visual Studio リモート デバッガー サービスがデバッグを開始したコンピューターに接続するときに、このサービスを実行しているユーザー アカウントを認証できないことを示します。  
  
 コンピューターにアクセスできるアカウントは、次の表のとおりです。  
  
|||||  
|-|-|-|-|  
||LocalSystem アカウント|ドメイン アカウント|両方のコンピューターに同じユーザー名とパスワードを持つローカル アカウント|  
|両方のコンピューターが同じドメインにある場合|[はい]|はい|[はい]|  
|両方のコンピューターが双方向の信頼関係を持つドメインにある場合|×|Ｘ|[はい]|  
|一方または両方のコンピューターがワークグループにある場合|×|Ｘ|[はい]|  
|コンピューターが異なるドメインにある場合|×|Ｘ|[はい]|  
  
 また、次の条件を満たす必要があります。  
  
-   Visual Studio リモート デバッガー サービスを実行するアカウントは、すべてのプロセスをデバッグできるように、リモート コンピューターの管理者アカウントであることが必要です。  
  
-   アカウントがありますを許可する、`Log on as a service`特権を使用しているリモート コンピューター上、**ローカル セキュリティ ポリシー**管理ツールです。  
  
-   ローカル アカウントを使用してコンピューターにアクセスしている場合は、ローカル アカウントで Visual Studio リモート デバッガー サービスを実行する必要があります。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  リモート コンピューターに Visual Studio リモート デバッガー サービスが正しく設定されていることを確認します。 詳細については、次を参照してください。[リモート デバッグ](../debugger/remote-debugging.md)です。  
  
2.  上の表に示した、デバッガー ホスト コンピューターにアクセスできる適切なアカウントを使用して、リモート デバッガー サービスを実行します。  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>"サービスとしてログオンする" 特権を追加するには  
  
1.  **開始** メニューの選択**コントロール パネルの** です。  
  
2.  コントロール パネルで、次のように選択します。**クラシック表示**必要に応じて、します。  
  
3.  **［管理ツール］** をダブルクリックします。  
  
4.  管理ツールウィンドウでダブルクリック**ローカル セキュリティ ポリシー**です。  
  
5.  **ローカル セキュリティ設定**ウィンドウで、展開、**ローカル ポリシー**フォルダーです。  
  
6.  をクリックして**ユーザー権利の割り当て**です。  
  
7.  **ポリシー**列をダブルクリックして**サービスとしてログオン**で現在のローカル グループ ポリシー割り当てを表示する、**サービスとしてログオン** ダイアログ ボックス。  
  
8.  新しいユーザーを追加するをクリックして、 **ユーザーまたはグループ**ボタンをクリックします。  
  
9. ユーザーの追加が完了したら、をクリックして**OK**です。  
  
### <a name="to-work-around-this-error"></a>このエラーを回避するには  
  
-   リモート デバッグ モニターをサービスとして実行する代わりに、アプリケーションとして実行します。  
  
## <a name="see-also"></a>参照  
 [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)