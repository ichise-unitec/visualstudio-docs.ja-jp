---
title: "Visual Studio での Python 用 Django Web プロジェクト テンプレート | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 753c3d78ff3da45213ea7cb9625d765e564a88e1
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2018
---
# <a name="django-web-project-template"></a>Django Web プロジェクト テンプレート

[Django](https://www.djangoproject.com/) は、高速、安全、スケーラブルな Web 開発用に設計されたハイレベルの Python フレームワークです。 Visual Studio の Python サポートには、Django ベースの Web アプリケーションの構造を設定するためのプロジェクト テンプレートが用意されています。 Visual Studio でテンプレートを使用するには、**[ファイル]、[新規]、[プロジェクト]** の順に選択し、「Django」を検索して、**Django Web プロジェクト** テンプレートを選択します。 作成されるプロジェクトには、定型コードと既定の SQLite データベースが含まれます。 **空の Django Web プロジェクト** テンプレートも似ていますが、これにはデータベースが含まれません。

Visual Studio は、Django プロジェクトの完全な IntelliSense を提供します。

- テンプレートに渡されるコンテキスト変数:

    ![コンテキスト変数用の IntelliSense](media/template-django-intellisense.png)

- 組み込みとユーザー定義両方のタグ付けとフィルター処理:

    ![タグとフィルターの IntelliSense](media/template-django-intellisense-filter.png)

- 埋め込みの CSS と JavaScript の構文の色分け表示:

    ![CSS Intellisense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

また、Visual Studio は Django プロジェクトの完全な[デバッグ サポート](debugging.md)も提供します。 

![ブレークポイント](media/template-django-debugging.png)

Django プロジェクトは `manage.py` ファイルで管理するのが一般的であり、Visual Studio でもそのようになっています。 エントリ ポイントとしてそのファイルの使用を止めると、基本的にプロジェクト ファイルは壊れます。 その場合は、Django プロジェクトにしないで、[既存のファイルからプロジェクトを作成しなおす](python-projects.md#creating-a-project-from-existing-files)必要があります。

## <a name="django-management-console"></a>Django 管理コンソール

Django 管理コンソールには、**[プロジェクト]** メニューのさまざまなコマンドを使用するか、ソリューション エクスプローラーでプロジェクトを右クリックしてアクセスします。

- **[Django シェルを開く...]**: モデルを操作できるアプリケーション コンテキストでシェルを起動します

    ![コンソール](media/template-django-console-shell.png)

- **[Django Sync DB (Django 同期 DB)]**: `manage.py syncdb` を対話型ウィンドウで実行します。

    ![コンソール](media/template-django-console-sync-db.png)

- **[Collect Static (静的収集)]**: `manage.py collectstatic --noinput` を実行して、`settings.py` の `STATIC_ROOT` で指定されたパスにすべての統計ファイルをコピーします。 [Microsoft Azure に発行](template-web.md#publishing-to-azure-app-service)する場合、統計ファイルは発行操作の一部として収集されます。

    ![コンソール](media/template-django-console-collect-static.png)

- **[検証]**: `settings.py` の `INSTALLED_APPS` で指定されたインストール済みのモデルで検証エラーをレポートする `manage.py validate` を実行します。

    ![コンソール](media/template-django-console-validate.png)