---
title: "ClickOnce アプリケーションにおけるローカル データおよびリモート データへのアクセス | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 配置, データ"
  - "データ アクセス, ClickOnce アプリケーション"
ms.assetid: be5cbe12-6cb6-49c9-aa59-a1624e1eef3d
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce アプリケーションにおけるローカル データおよびリモート データへのアクセス
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ほとんどのアプリケーションはデータを使用または作成します。[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] には、データをローカルとリモートの両方で読み書きするための各種のオプションがあります。  
  
## ローカル データ  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] では、次のいずれかの方法を使用してデータを読み込んでローカルに格納できます。  
  
-   [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] データ ディレクトリ  
  
-   分離ストレージ  
  
-   その他のローカル ファイル  
  
### ClickOnce データ ディレクトリ  
 ローカル コンピューターにインストールされている各 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションには、データ ディレクトリがあります。このデータ ディレクトリは、ユーザーの "Documents and Settings" フォルダーにあります。[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションに含まれていて、"データ" ファイルとしてマークされているすべてのファイルは、アプリケーションのインストール時にこのディレクトリにコピーされます。 どのような種類のファイルでもデータ ファイルとして指定できます。最もよく使用されるのは、テキスト ファイルや XML ファイル、データベース ファイル \(Microsoft Access の .mdb ファイルなど\) です。  
  
 データ ディレクトリは、アプリケーションで管理するデータ、つまり、アプリケーションによって明示的に格納および保守されるデータ用のディレクトリです。 アプリケーション マニフェストで "データ" のマークが付けられていない静的で非依存のすべてのファイルは、アプリケーション ディレクトリに格納されます。 このディレクトリには、アプリケーションの実行可能ファイル \(.exe\) とアセンブリがあります。  
  
> [!NOTE]
>  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションをアンインストールすると、そのアプリケーションのデータ ディレクトリも削除されます。 文書ファイルなど、エンド ユーザーが管理するデータを格納するためには、データ ディレクトリを使用しないでください。  
  
#### ClickOnce で配布するデータ ファイルのマーク付け  
 既存のファイルをデータ ディレクトリに格納するには、そのファイルを [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションのアプリケーション マニフェスト ファイル内でデータ ファイルとしてマークする必要があります。 詳細については、「[方法 : ClickOnce アプリケーションにデータ ファイルを含める](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)」を参照してください。  
  
#### データ ディレクトリからの読み取りとデータ ディレクトリの書き込み  
 データ ディレクトリからデータを読み込むには、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションで読み取りアクセス許可を要求することが必要です。同じように、データ ディレクトリにデータを書き込むには、書き込みのアクセス許可が必要です。 完全な信頼を得て実行するようにアプリケーションが構成されている場合、これらのアクセス許可は自動的にアプリケーションに与えられます。 アクセス許可の昇格機能または信頼されたアプリケーションの配置を使用してアプリケーションのアクセス許可を昇格する方法の詳細については、「[ClickOnce アプリケーションのセキュリティ](../deployment/securing-clickonce-applications.md)」を参照してください。  
  
> [!NOTE]
>  組織が信頼されたアプリケーションの配置を使用しておらず、アクセス許可の昇格機能をオフにしている場合は、アクセス許可のアサートは失敗します。  
  
 アプリケーションにこれらのアクセス許可が与えられると、アプリケーションは <xref:System.IO> に属する各クラスのメソッド呼び出しを使用して、データ ディレクトリにアクセスできます。 Windows フォーム [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーション内のデータ ディレクトリのパスを取得するには、<xref:System.Deployment.Application.ApplicationDeployment> の <xref:System.Deployment.Application.ApplicationDeployment.CurrentDeployment%2A> プロパティで定義された <xref:System.Deployment.Application.ApplicationDeployment.DataDirectory%2A> プロパティを使用できます。 これは、データにアクセスする最も便利な方法として推奨されています。 次のコード例では、配置にデータ ファイルとして組み込んだ CSV.txt というテキスト ファイルに対してこの操作を実行する方法を示します。  
  
 [!CODE [ClickOnce.OpenDataFile#1](../CodeSnippet/VS_Snippets_Winforms/ClickOnce.OpenDataFile#1)]  
  
 配置内のファイルをデータ ファイルとしてマークする方法の詳細については、「[方法 : ClickOnce アプリケーションにデータ ファイルを含める](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)」を参照してください。  
  
 <xref:System.Windows.Forms.Application> クラスにある <xref:System.Windows.Forms.Application.LocalUserAppDataPath%2A> など、関連する変数を使用してデータ ディレクトリのパスを取得することもできます。  
  
 他の種類のファイルを扱うには、アクセス許可の追加が必要になる場合があります。 たとえば、Access データベース \(.mdb\) ファイルを使用するには、関連する <xref:System.Data> クラスを使用するために、アプリケーションから完全な信頼をアサートする必要があります。  
  
#### データ ディレクトリとアプリケーションのバージョン  
 アプリケーションの各バージョンのデータはそれぞれ別のデータ ディレクトリに格納され、バージョンごとに分離されます。[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] では、配置にデータ ファイルが含まれていてもいなくても、アプリケーションが実行時にデータ ファイルを新規作成する場所として使用できるように、このデータ ディレクトリが作成されます。 アプリケーションの新しいバージョンをインストールすると、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] により、前のバージョンのデータ ディレクトリから新しいバージョンのデータ ディレクトリに、既存のデータ ファイルがすべてコピーされます。このとき、そのデータ ファイルが元の配置に含まれていたデータ ファイルであるか、アプリケーションによって作成されたデータ ファイルであるかは区別されません。  
  
 データ ファイルのハッシュ値がアプリケーションの古いバージョンと新しいバージョンとで異なる場合、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] は、古いバージョンのファイルをサーバーにある新しいバージョンのファイルで置き換えます。 また、以前のバージョンのアプリケーションで作成された新しいファイルの名前が、新しいバージョンの配置に含まれているファイルと同じ名前の場合、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] は、古いバージョンのファイルを新しいファイルで上書きします。 どちらの場合にも、古いファイルはデータ ディレクトリの `.pre` という名前のサブディレクトリに保存されるため、アプリケーションは移行時にそれらの古いデータにアクセスできます。  
  
 データをより細かく移行する必要がある場合は、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Deployment API を使用して、古いデータ ディレクトリから新しいデータ ディレクトリへのカスタム移行を実行できます。 利用可能なダウンロードを <xref:System.Deployment.Application.ApplicationDeployment.IsFirstRun%2A> を使用してテストし、<xref:System.Deployment.Application.ApplicationDeployment.Update%2A> または <xref:System.Deployment.Application.ApplicationDeployment.UpdateAsync%2A> を使用して更新プログラムをダウンロードし、更新が完了した後に各自のカスタム データ移行タスクを実行する必要があります。  
  
### 分離ストレージ  
 分離ストレージには、簡単な操作でファイルを作成したりアクセスしたりできる API が用意されています。 格納したファイルの実際の場所は、開発者からもユーザーからも隠されます。  
  
 分離ストレージは、[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] のすべてのバージョンで動作します。 分離ストレージは、部分的に信頼されたアプリケーション内でも、アクセス許可を追加せずに動作します。 アプリケーションを部分的に信頼された状態で実行する必要がある場合に、アプリケーション固有のデータを保守する必要があるときは、分離ストレージを使用する必要があります。  
  
 詳細については、「[分離ストレージ](../Topic/Isolated%20Storage.md)」を参照してください。  
  
### その他のローカル ファイル  
 アプリケーションでレポート、画像、音楽などのエンド ユーザー データを処理し、保存する必要がある場合は、アプリケーションにおいて、<xref:System.Security.Permissions.FileIOPermission> によりローカル ファイル システムに対するデータの読み込みと書き込みを実行することが必要になります。  
  
## リモート データ  
 アプリケーションでは、実行時に、顧客データや市場情報などの情報をリモートの Web サイトから取得する必要が生じることがあります。 このセクションでは、リモート データを取得するための最も一般的な手法について説明します。  
  
### HTTP によるファイル アクセス  
 <xref:System.Net> 名前空間にある <xref:System.Net.WebClient> クラスまたは <xref:System.Net.HttpWebRequest> クラスを使用すると、Web サーバー上のデータにアクセスできます。 アクセスできるデータは、静的なファイルか、未加工のテキストまたは XML データを返す [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリケーションのいずれかです。 データが XML 形式の場合には、<xref:System.Xml.XmlDocument> クラスを使用してデータを取得すると、最も高速です。このクラスの <xref:System.Xml.XmlDocument.Load%2A> メソッドには引数として URL を渡します。 例については、「[XML ドキュメントの DOM への読み取り](../Topic/Reading%20an%20XML%20Document%20into%20the%20DOM.md)」を参照してください。  
  
 アプリケーションから HTTP 経由でリモート データにアクセスする場合は、セキュリティを考慮する必要があります。 既定では、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションによるネットワーク リソースへのアクセスは、アプリケーションが配置された方法に応じて制限される場合があります。 この制限は、悪意のあるプログラムが特権の必要なリモート データへのアクセスを取得したり、ユーザーのコンピューターを使用してネットワーク上の他のコンピューターを攻撃したりすることを防ぐ目的で適用されます。  
  
 次の表は、採用できる配置の方法と、それぞれの既定の Web アクセス許可の一覧です。  
  
|配置の種類|既定のネットワーク アクセス許可|  
|-----------|----------------------|  
|Web インストール|アプリケーションのインストール元の Web サーバーにのみアクセスできます。|  
|ファイル共有インストール|どの Web サーバーにもアクセスできません。|  
|CD\-ROM インストール|任意の Web サーバーにアクセスできます。|  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションがセキュリティ上の制限のために Web サーバーにアクセスできない場合は、アプリケーションから対象の Web サイトに <xref:System.Net.WebPermission> をアサートする必要があります。[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションに与えるセキュリティ アクセス許可を高める方法の詳細については、「[ClickOnce アプリケーションのセキュリティ](../deployment/securing-clickonce-applications.md)」を参照してください。  
  
### XML Web サービス経由でのデータ アクセス  
 データを XML Web サービスとして公開する場合は、XML Web サービス プロキシを使用してデータにアクセスできます。 このプロキシは、どちらかの [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] を使用して作成した [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] クラスです。 顧客の検索、注文の発注など、XML Web サービスを使用して実行する操作は、このプロキシのメソッドとして公開されます。 このため、Web サービスは未加工のテキスト ファイルや XML ファイルより簡単に使用できます。  
  
 HTTP 経由で動作する XML Web サービスには、<xref:System.Net.WebClient> および <xref:System.Net.HttpWebRequest> クラスと同じセキュリティ制限が課されます。  
  
### データベースへの直接アクセス  
 <xref:System.Data> 名前空間にあるクラスを使用すると、SQL Server などネットワーク上のデータベース サーバーとの直接接続を確立できますが、セキュリティの問題を考慮する必要があります。 HTTP 要求とは異なり、部分的な信頼の場合、データベース接続要求は既定で常に禁止されています。[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションを CD\-ROM からインストールした場合にだけ、既定でデータベース接続のアクセス許可を得ることができます。 これにより、アプリケーションには完全信頼が与えられます。 特定の SQL Server データベースへのアクセスを有効にするには、アプリケーションからデータベースに対して <xref:System.Data.SqlClient.SqlClientPermission> を要求する必要があります。SQL Server 以外のデータベースへのアクセスを有効にするには、<xref:System.Data.OleDb.OleDbPermission> を要求する必要があります。  
  
 ほとんどの場合、データベースに直接アクセスする必要はありません。代わりに、[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] で記述された Web サーバー アプリケーションまたは XML Web サービスを経由してデータベースにアクセスします。 Web サーバーから [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] アプリケーションを配置した場合は、この方法でデータベースにアクセスするのが、多くの場合に最良の方法です。 部分的に信頼されたサーバーに、アプリケーションのアクセス許可を昇格せずにアクセスできます。  
  
## 参照  
 [方法 : ClickOnce アプリケーションにデータ ファイルを含める](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)