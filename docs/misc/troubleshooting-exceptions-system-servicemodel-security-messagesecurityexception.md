---
title: "例外のトラブルシューティング : System.ServiceModel.Security.MessageSecurityException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.ServiceModel.Security.MessageSecurityException 例外"
  - "MessageSecurityException 例外"
ms.assetid: 61ad69a1-ac50-49de-9a7c-8454a84ec5bd
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 例外のトラブルシューティング : System.ServiceModel.Security.MessageSecurityException
<xref:System.ServiceModel.Security.MessageSecurityException> 例外は、メッセージが適切に保護されていない、または改ざんされていると [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] が判断した場合にスローされます。 このエラーが最も発生しやすいのは、次の条件がすべて該当する場合です。  
  
-   リモート デスクトップ接続やターミナル サービスなどのリモート接続を介した WCF サービス参照を使用して、Web サイトまたは Web アプリケーション プロジェクト内の WCF サービス \(.svc\) と通信している。  
  
-   リモート サイトに管理者のアクセス許可がない。  
  
-   リモート サイトの localhost に対する要求が [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 開発サーバーによって処理されている。  
  
## 関連するヒント  
 **ASP.Net 開発サーバーを使用している場合は、NTLM 認証の問題を解決してください。**  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 開発サーバーでは、通常、Windows NT チャレンジ\/レスポンス \(NTLM: Windows NT Challenge\/Response\) セキュリティがオフになっており、匿名アクセスが許可されています。 既定では、ターミナル サービス セッションを実行するか、リモート接続を使用すると、NTLM セキュリティが有効になります。 NTLM が有効である場合、すべての localhost 要求が [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 開発サーバーを起動したユーザーまたはプロセスの資格情報に対して検証されます。 これにより、セキュリティ上の脅威が軽減されます。 ただし、WCF は独自の認証も行い、管理者以外のアカウントに WCF サービスの利用を許可しません。  
  
 リモート ユーザーが [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 開発サーバーを使用して Web サイトを実行し、さらに Web サービスまたは WCF サービスを使用する可能性がある場合は、カスタム サービス バインディングを作成するか、NTLM セキュリティをオフにすることができます。  
  
> [!IMPORTANT]
>  セキュリティが脆弱になる可能性があるため、NTLM セキュリティをオフにすることはお勧めしません。  
  
 カスタム サービス バインディングを作成した場合でも、引き続き NTLM 認証によって保護されます。  
  
 WCF サービスのカスタム サービス バインディングを作成するには、次の手順を実行します。  
  
#### ASP.NET 開発サーバー内でホストされている WCF サービスのカスタム サービス バインディングを作成するには  
  
1.  例外が発生した WCF サービスの Web.config ファイルを開きます。  
  
2.  Web.config ファイルに次の情報を入力します。  
  
    ```  
    <bindings> <customBinding> <binding name="Service1Binding"> <transactionFlow /> <textMessageEncoding /> <httpTransport authenticationScheme="Ntlm" /> </binding> </customBinding> </bindings>  
    ```  
  
3.  Web.config ファイルを保存して閉じます。  
  
4.  WCF サービスまたは Web サービスのコードで、エンドポイント値を次のように変更します。  
  
    ```  
    <endpoint address="" binding="customBinding" bindingConfiguration="Service1Binding" contract="IService1" />  
    ```  
  
     これにより、サービスがカスタム バインディングを使用するようになります。  
  
5.  サービスにアクセスする Web アプリケーションにサービスへの参照を追加します  \(**\[サービス参照の追加\]** ダイアログ ボックスで、例外が発生した元のサービスで行ったようにサービスへの参照を追加します\)。  
  
 WCF サービス参照を使用する場合に NTLM セキュリティをオフにするには、次の手順を実行します。  
  
> [!IMPORTANT]
>  セキュリティが脆弱になる可能性があるため、NTLM セキュリティをオフにすることはお勧めしません。  
  
#### NTLM セキュリティをオフにするには  
  
1.  **\[ソリューション エクスプローラー\]** で Web サイト名を右クリックして、**\[プロパティ ページ\]** をクリックします。  
  
2.  **\[開始オプション\]** をクリックし、**\[NTLM 認証\]** チェック ボックスをオフにします。  
  
3.  **\[OK\]** をクリックします。  
  
## 参照  
 <xref:System.ServiceModel.Security.MessageSecurityException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)