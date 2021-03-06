---
title: "ソリューション &lt;name&gt; とそのプロジェクトを現在の形式に変換しなければなりません。 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.querymigratesolution"
ms.assetid: 1ecb09ab-1283-4ba5-874c-f675905a3b7b
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# ソリューション &lt;name&gt; とそのプロジェクトを現在の形式に変換しなければなりません。
以前のバージョンの Visual Studio で作成されたソリューションを開きました。 ソリューション ファイルとプロジェクト ファイルを現在の形式に変換しないと、コンピューターにインストールされているバージョンの Visual Studio でソリューションを開いて編集することができません。 このソリューションをすぐに変換するかどうかを選択できます。 形式を変換したら、元に戻すことはできません。  
  
> [!CAUTION]
>  ソリューションがソース コード管理されていて、変換後に再びチェックインする場合は、そのソリューションのプロジェクトを共有しているソリューションが他にないかどうかを先に確認してください。 他のソリューションで使用されている変換したプロジェクトを含むソリューションをチェックインしないでください。 チェックインすると、そのプロジェクトを使用している他のソリューション内の依存関係が壊れて、正しく開いたりビルドしたりできなくなります。  
  
 変換する前にソリューション ファイルとプロジェクト ファイルのバックアップ コピーを作成しておくと安心です。  
  
> [!NOTE]
>  Visual Studio のソリューションを変換すると、変換前のソリューション ファイルは ".old" という拡張子で最上位のソリューション ディレクトリに保存されます。 プロジェクトの種類によっては \(Visual C\+\+ プロジェクトなど\)、プロジェクト ファイルについても同じように、変換前のファイルが ".old" という拡張子でプロジェクト ディレクトリに保存されます。  
  
 読み取り専用のプロジェクトは変換されません。 読み取り専用のプロジェクトを変換できるのは、編集のアクセス許可を持つユーザーだけです。 変換したソリューション内でプロジェクトを使用するには、そのプロジェクト ファイルを現在の形式に変換しておく必要があります。 ソリューションまたはそのいずれかのプロジェクトを変換すると、以前のバージョンの Visual Studio では、そのソリューションを編集、ビルド、または実行できなくなります。  
  
### 対処方法  
  
1.  **\[はい\]** または **\[いいえ\]** をクリックします。  
  
    -   **\[はい\]** \- ソリューション ファイルおよびそのソリューションの編集可能なプロジェクトのファイルは、コンピューターにインストールされているバージョンの Visual Studio で使用されている形式に変換されます。 変換されたソリューションは、ソース コード管理されている場合、ローカル ドライブにチェックアウトされ、編集できるように開かれます。  
  
    -   **\[いいえ\]** \- ソリューションとそのプロジェクトは変換されません。ソース コード管理からチェックアウトされることも、開くこともありません。  
  
 チームで開発している場合は、同じソリューションで作業するすべてのメンバーが同じバージョンの Visual Studio をローカル コンピューターにインストールしている必要があります。 ソリューションやプロジェクトにアクセスできなくなることがないように、定期的にチームと連絡を取ってください。  
  
## 参照  
 [Project Dependencies Dialog Box](http://msdn.microsoft.com/ja-jp/d66e48c3-3722-40dd-99b4-53d93cac128e)   
 [Visual Studio でのアプリケーションのビルド](../ide/compiling-and-building-in-visual-studio.md)