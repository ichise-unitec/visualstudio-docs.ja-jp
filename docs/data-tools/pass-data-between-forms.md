---
title: "フォーム間でデータを渡す |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- walkthroughs [Windows Forms], data
- walkthroughs [Visual Studio], data
- data [Visual Studio], passing between forms
- forms, passing data between
- Windows Forms, walkthroughs
ms.assetid: 78bf038b-9296-4fbf-b0e8-d881d1aff0df
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 7704b8f4af9f6858e476f4075c6f38cda3052118
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="pass-data-between-forms"></a>フォーム間でデータを渡す
このチュートリアルでは、フォーム間でデータを渡す手順について説明します。 顧客と Northwind の orders テーブルを使用して、1 つの形式により、ユーザー、顧客を選択して、2 番目のフォームには、選択した顧客の注文が表示されます。 このチュートリアルでは、最初のフォームからデータを受信する 2 番目のフォームにメソッドを作成する方法を示します。  
  
> [!NOTE]
>  このチュートリアルでは、フォーム間でデータを渡す 1 つの方法についてのみ説明します。 データを受信する 2 番目のコンス トラクターを作成するなど、フォームにデータを渡すには、他のオプションがあるか、最初のフォームからデータを使用するパブリック プロパティを作成するを設定できます。  
  
 このチュートリアルでは、以下のタスクを行います。  
  
-   新たに作成する**Windows フォーム アプリケーション**プロジェクト。  
  
-   作成と構成を含むデータセット、[データ ソース構成ウィザード](../data-tools/media/data-source-configuration-wizard.png)です。  
  
-   項目をドラッグしたときに、フォームに作成するコントロールを選択すると、**データソース**ウィンドウです。 詳細については、次を参照してください。[セットのデータ ソース ウィンドウからドラッグしたときに作成する制御](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)です。  
  
-   項目をドラッグして、データ バインド コントロールを作成する、**データソース**ウィンドウからフォームにします。  
  
-   データを表示するグリッドのある 2 番目のフォームを作成します。  
  
-   特定の顧客の注文をフェッチする TableAdapter クエリを作成します。  
  
-   フォーム間でデータを渡します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
このチュートリアルでは、SQL Server Express LocalDB と、Northwind サンプル データベースを使用します。  
  
1.  SQL Server Express LocalDB をお持ちでない場合は、インストールのいずれかから、 [SQL Server のエディションのダウンロード ページ](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx)、または、 **Visual Studio インストーラー**です。 一部として、Visual Studio インストーラーで、SQL Server Express LocalDB をインストールすることができます、**データ ストレージと処理**ワークロード、または個々 のコンポーネントとして。  
  
2.  次の手順に従って、Northwind サンプル データベースをインストールします。  

    1. Visual Studio で開く、 **SQL Server オブジェクト エクスプ ローラー**ウィンドウです。 (の一部として SQL Server オブジェクト エクスプ ローラーがインストールされている、**データ ストレージと処理**Visual Studio インストーラーでのワークロードです)。展開して、 **SQL Server**ノード。 LocalDB インスタンスを右クリックし、選択**新しいクエリしています.**.  

       クエリ エディター ウィンドウが開きます。  

    2. コピー、 [Northwind TRANSACT-SQL スクリプト](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true)をクリップボードにします。 この T-SQL スクリプトは、最初から、Northwind データベースを作成し、データを設定します。  

    3. T-SQL スクリプトをクエリ エディターに貼り付けを選択し、 **Execute**ボタンをクリックします。  

       短期間のうち、クエリの実行が終了し、Northwind データベースを作成します。  
  
## <a name="create-the-windows-forms-application"></a>Windows フォーム アプリケーションを作成します。  
  
#### <a name="to-create-the-new-windows-project"></a>新しい Windows プロジェクトを作成するには  
  
1. Visual Studio での**ファイル**メニューの **新規**、**プロジェクト.**.  
  
2. いずれかを展開**Visual c#**または**Visual Basic**左側のペインでを選択し、 **Windows クラシック デスクトップ**です。  

3. 中央のペインで、 **Windows フォーム アプリ**プロジェクトの種類。  

4. プロジェクトに名前を**PassingDataBetweenForms**を選択し**OK**です。 
  
     **PassingDataBetweenForms**プロジェクトが作成され、追加する**ソリューション エクスプ ローラー**です。  
  
## <a name="create-the-data-source"></a>データ ソースを作成します。  
  
#### <a name="to-create-the-data-source"></a>データ ソースを作成するには  
  
1.  **[データ]** メニューの **[データ ソースの表示]**をクリックします。  
  
2.  **データソース**ウィンドウで、**新しいデータ ソースの追加**を開始する、**データ ソース構成**ウィザード。  
  
3.  **[データソースの種類を選択]** ページで、 **[データベース]** をクリックし、 **[次へ]**をクリックします。  
  
4.  **データベース モデルの選択**ことを確認 ページで、**データセット**が指定され、をクリックして**次**です。  
  
5.  **データ接続の選択** ページで、次のいずれかの操作します。  
  
    -   Northwind サンプル データベースへのデータ接続がドロップダウン リストに表示されている場合は選択します。  
  
    -   選択**新しい接続**を起動する、**接続接続の追加/変更** ダイアログ ボックス。  
  
6.  データベース パスワードが必要な場合、および機密データを含めるためのオプションが有効になっている場合は、オプションを選択し、をクリックして**次**です。  
  
7.  **接続文字列をアプリケーション構成ファイルに保存** ページで、をクリックして**次**です。  
  
8.  **データベース オブジェクトの選択** ページで、展開、**テーブル**ノード。  
  
9. 選択、**顧客**と**注文**テーブル、およびクリック**完了**です。  
  
     **NorthwindDataSet**をプロジェクトに追加され、**顧客**と**注文**に表示されるテーブル、**データ ソース**ウィンドウです。  
  
## <a name="create-the-first-form-form1"></a>最初のフォーム (Form1) の作成します。  
 データ バインド グリッドを作成することができます (、<xref:System.Windows.Forms.DataGridView>コントロール)、ドラッグして、**顧客**ノードから、**データ ソース**ウィンドウからフォームにします。  
  
#### <a name="to-create-a-data-bound-grid-on-the-form"></a>フォームにデータ バインド グリッドを作成するには  
  
-   メインをドラッグして**顧客**ノードから、**データ ソース**ウィンドウ**Form1**です。  
  
     A<xref:System.Windows.Forms.DataGridView>とツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) レコードを移動するために表示されます。 **Form1**です。 A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、 <xref:System.Windows.Forms.BindingSource>、および<xref:System.Windows.Forms.BindingNavigator>コンポーネント トレイに表示されます。  
  
## <a name="create-the-second-form-form2"></a>2 番目のフォーム (Form2) の作成します。  
  
#### <a name="to-create-a-second-form-to-pass-the-data-to"></a>データの渡し先となる 2 番目のフォームを作成するには  
  
1.  **[プロジェクト]** メニューの **[Windows フォームの追加]** を選択します。  
  
2.  既定の名前のままにして**Form2**、 をクリック**追加**です。  
  
3.  メインをドラッグして**注文**ノードから、**データ ソース**ウィンドウ**Form2**です。  
  
     A<xref:System.Windows.Forms.DataGridView>とツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) レコードを移動するために表示されます。 **Form2**です。 A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md)、CustomersTableAdapter、 <xref:System.Windows.Forms.BindingSource>、および<xref:System.Windows.Forms.BindingNavigator>コンポーネント トレイに表示されます。  
  
4.  削除、 **OrdersBindingNavigator**コンポーネント トレイからです。  
  
     **OrdersBindingNavigator**から消えます**Form2**です。  
  
## <a name="add-a-tableadapter-query-to-form2-to-load-orders-for-the-selected-customer-on-form1"></a>TableAdapter クエリを Form1 で選択した顧客の注文を読み込む Form2 を追加します。  
  
#### <a name="to-create-a-tableadapter-query"></a>TableAdapter クエリを作成するには  
  
1.  ダブルクリックして、 **NorthwindDataSet.xsd**ファイル**ソリューション エクスプ ローラー**です。  
  
2.  右クリックし、 **OrdersTableAdapter**を選択して**クエリの追加**です。  
  
3.  既定のオプションのまま**SQL ステートメントを使用**、順にクリック**次**です。  
  
4.  既定のオプションのまま**を行を返す SELECT**、順にクリック**次**です。  
  
5.  返すクエリに WHERE 句を追加`Orders`に基づいて、`CustomerID`です。 クエリは次のようになります。  
  
    ```  
    SELECT OrderID, CustomerID, EmployeeID, OrderDate, RequiredDate, ShippedDate, ShipVia, Freight, ShipName, ShipAddress, ShipCity, ShipRegion, ShipPostalCode, ShipCountry  
    FROM Orders   
    WHERE CustomerID = @CustomerID  
    ```  
  
    > [!NOTE]
    >  データベースに対してパラメーターの構文が正しいことを確認します。 たとえば、Microsoft Access では、WHERE 句は `WHERE CustomerID = ?` のようになります。  
  
6.  **[次へ]**をクリックします。  
  
7.  **DataTableMethod 名を入力**、型`FillByCustomerID`です。  
  
8.  クリア、 **DataTable を返す**オプションをクリックして**次**です。  
  
9. **[完了]**をクリックします。  
  
## <a name="create-a-method-on-form2-to-pass-data-to"></a>データの渡し先となる Form2 のメソッドを作成します。  
  
#### <a name="to-create-a-method-to-pass-data-to"></a>データの渡し先となるメソッドを作成するには  
  
1.  右クリック**Form2**を選択して**コードの表示**を開くには**Form2**で、**コード エディター**です。  
  
2.  次のコードを追加**Form2**後、`Form2_Load`メソッド。  
  
     [!code-vb[VbRaddataDisplaying#1](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_1.vb)]
     [!code-csharp[VbRaddataDisplaying#1](../data-tools/codesnippet/CSharp/pass-data-between-forms_1.cs)]  
  
## <a name="create-a-method-on-form1-to-pass-data-and-display-form2"></a>データを渡して、Form2 を表示する Form1 のメソッドを作成します。  
  
#### <a name="to-create-a-method-to-pass-data-to-form2"></a>Form2 にデータを渡すメソッドを作成するには  
  
1.  **Form1**Customer データ グリッドを右クリックし、クリックして**プロパティ**です。  
  
2.  **プロパティ**ウィンドウで、をクリックして**イベント**です。  
  
3.  ダブルクリックして、 **CellDoubleClick**イベント。  
  
     コード エディターが表示されます。  
  
4.  メソッド定義を次のサンプルのように更新します。  
  
     [!code-csharp[VbRaddataDisplaying#2](../data-tools/codesnippet/CSharp/pass-data-between-forms_2.cs)]
     [!code-vb[VbRaddataDisplaying#2](../data-tools/codesnippet/VisualBasic/pass-data-between-forms_2.vb)]  
  
## <a name="run-the-application"></a>アプリケーションを実行する  
  
#### <a name="to-run-the-application"></a>アプリケーションを実行するには  
  
-   F5 キーを押してアプリケーションを実行します。  
  
-   内の顧客レコードをダブルクリックして**Form1**を開くには**Form2**その顧客の注文とします。  
  
## <a name="next-steps"></a>次の手順  
 フォーム間でデータを渡した後に、アプリケーションの要件に応じてさらに操作を追加して実行できます。 このチュートリアルで行うことができる拡張には次のものがあります。  
  
-   データセットを編集し、データベース オブジェクトの追加または削除を行います。 詳細については、[データセットの作成と構成](../data-tools/create-and-configure-datasets-in-visual-studio.md)に関するページを参照してください。  
  
-   データベースにデータを戻して保存する機能を追加します。 詳細については、次を参照してください。[データをデータベースに保存](../data-tools/save-data-back-to-the-database.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)