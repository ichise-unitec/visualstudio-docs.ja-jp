---
title: "Visual Studio for Mac のアンインストール | Microsoft Docs"
description: "Visual Studio for Mac と関連ツールをアンインストールする方法を説明します。"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 4EB95F75-BC2E-4982-9564-2975805712D8
ms.openlocfilehash: 193eebd4849e6a133ade1d14cb17d5b345199811
ms.sourcegitcommit: 24f81b8fb59722cf4a856005227f6a29bb2990cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2017
---
# <a name="uninstalling-visual-studio-for-mac"></a>Visual Studio for Mac のアンインストール

Visual Studio for Mac のようなスタンドアロン アプリなど、クロスプラットフォーム アプリケーション開発が可能な Xamarin 製品がいくつかあります。

このガイドでは、関連するセクションに移動して各製品を個別にアンインストールする方法を説明します。 このガイドのすべての手順に従うことで、Xamarin ツールセット全体をアンインストールすることができます。

Xamarin Studio をコンピューターにインストールしてある場合は、以下の手順に加えて、developer.xamarin.com の[アンインストール](https://developer.xamarin.com/guides/cross-platform/getting_started/installation/uninstalling_xamarin/) ガイドの手順にも従うことが必要な場合があります。

## <a name="uninstall-script"></a>アンインストール スクリプト

アンインストール スクリプトを使うと、Visual Studio とそれに関連するコンポーネントを一度にアンインストールできます。スクリプトは[こちら](https://raw.githubusercontent.com/MicrosoftDocs/visualstudio-docs/master/mac/resources/uninstall-vsmac.sh)にあります。

このアンインストール スクリプトには、この記事で説明されているほとんどのコマンドが含まれます。 外部依存関係の可能性のためにスクリプトからは次の 2 つが除外されています。

- **Mono のアンインストール**
- **Android AVD のアンインストール**

スクリプトを実行するには次のようにします。

1. スクリプトを右クリックして **[名前を付けて保存]** を選び、 Mac にファイルを保存します。
2. ターミナルを開き、スクリプトをダウンロードした場所に作業ディレクトリを変更します。

    ```bash
    $ cd /location/of/file
    ```
3. スクリプトを実行可能にして、**sudo** で実行します。

    ```bash
    $ chmod +x ./uninstall-vsmac.sh
    $ sudo ./uninstall-vsmac.sh
    ```
4. 最後に、アンインストール スクリプトを削除します。

## <a name="uninstall-visual-studio-for-mac"></a>Visual Studio for Mac をアンインストールする

Mac から Visual Studio をアンインストールするときは最初に、**/Applications** ディレクトリで **Visual Studio.app** を探して、それを**ごみ箱**にドラッグします。 または、右クリックして **[ごみ箱に移動]** を選びます (下図参照)。

![Visual Studio アプリケーションをごみ箱に移動する](media/uninstall-image1.png)

このアプリ バンドルを削除すると Visual Studio for Mac は削除されますが、Xamarin 関連の他のファイルがファイル システムにまだ残っている可能性があります。

Visual Studio for Mac のすべてのトレースを削除するには、ターミナルで次のコマンドを実行する必要があります。

```bash
sudo rm -rf "/Applications/Visual Studio.app"
rm -rf ~/Library/Caches/VisualStudio
rm -rf ~/Library/Preferences/VisualStudio
rm -rf "~/Library/Preferences/Visual Studio"
rm -rf ~/Library/Logs/VisualStudio
rm -rf ~/Library/VisualStudio
rm -rf ~/Library/Preferences/Xamarin/
rm -rf ~/Library/Developer/Xamarin
rm -rf "~/Library/Application Support/VisualStudio"
```

## <a name="uninstall-mono-sdk-mdk"></a>Mono SDK (MDK) をアンインストールする

Mono は Microsoft .NET Framework のオープン ソースの実装であり、すべての Xamarin 製品 (Xamarin.iOS、Xamarin.Android、Xamarin.Mac) によって、C# でこれらのプラットフォームの開発を可能にするために使われています。

> [!WARNING]
> Visual Studio for Mac 以外にも Mono を使うアプリケーションがあります (Unity など)。
> Mono をアンインストールする前に、Mono に依存するアプリケーションが他にないことを確認してください。

Mono Framework をコンピューターから削除するには、ターミナルで次のコマンドを実行します。

```bash
sudo rm -rf /Library/Frameworks/Mono.framework
sudo pkgutil --forget com.xamarin.mono-MDK.pkg
sudo rm -rf /etc/paths.d/mono-commands
```

## <a name="uninstall-xamarinandroid"></a>Xamarin.Android をアンインストールする

Xamarin.Android をインストールして使うために必要なものがいくつかあります (Android SDK や Java SDK など)。

Xamarin.Android を削除するには、次のコマンドを使います。

```bash
sudo rm -rf /Developer/MonoDroid
rm -rf ~/Library/MonoAndroid
sudo pkgutil --forget com.xamarin.android.pkg
sudo rm -rf /Library/Frameworks/Xamarin.Android.framework
```

### <a name="uninstall-android-sdk-and-java-sdk"></a>Android SDK と Java SDK をアンインストールする

Android アプリケーションの開発には Android SDK が必要です。 Android SDK のすべての部分を完全に削除するには、**~/Library/Developer/Xamarin/** でファイルを探して、**ごみ箱**に移動します。

Java SDK (JDK) は Mac OS X/macOS の一部として既にあらかじめパッケージ化されているので、アンインストールする必要はありません。

### <a name="uninstall-android-avd"></a>Android AVD をアンインストールする

> [!WARNING]
> Android Studio など、Visual Studio for Mac 以外にも Android AVD とこれらの追加 Android コンポーネントを使うアプリケーションがあります。
> このディレクトリを削除すると、プロジェクトが Android Studio で壊れる可能性があります。 

Android AVD および追加 Android コンポーネントを削除するには、次のコマンドを使います。

```bash
rm -rf ~/.android
```

Android AVD のみを削除するには、次のコマンドを使います。

```bash
rm -rf ~/.android/avd
```

 

## <a name="uninstall-xamarinios"></a>Xamarin.iOS をアンインストールする

Xamarin.iOS により、Visual Studio for Mac で C# または F# を使って iOS アプリケーションを開発できます。

以前のバージョンの Xamarin.iOS では、Visual Studio での iOS 開発を可能にするために、Xamarin Build Host も自動的にインストールされました。 両方をコンピューターからアンインストールするには、次の手順のようにします。

ターミナルで次のコマンドを使って、ファイル システムからすべての Xamarin.iOS ファイルを削除します。

```bash
rm -rf ~/Library/MonoTouch
sudo rm -rf /Library/Frameworks/Xamarin.iOS.framework
sudo rm -rf /Developer/MonoTouch
sudo pkgutil --forget com.xamarin.monotouch.pkg
sudo pkgutil --forget com.xamarin.xamarin-ios-build-host.pkg
sudo pkgutil --forget com.xamarin.xamarin.ios.pkg
```

## <a name="uninstall-xamarinmac"></a>Xamarin.Mac をアンインストールする

Visual Studio for Mac が正常にアンインストールされた後は、次の 2 つのコマンドを使って Mac から製品とライセンスを除去することにより、コンピューターから Xamarin.Mac を削除できます。

```bash
sudo rm -rf /Library/Frameworks/Xamarin.Mac.framework
rm -rf ~/Library/Xamarin.Mac
```

## <a name="uninstall-workbooks-and-inspector"></a>Workbooks と Inspector をアンインストールする

1.2.2 以降では、ターミナルで次のコマンドを実行して、Xamarin Workbooks と Inspector をアンインストールできます。

```bash
sudo /Library/Frameworks/Xamarin.Interactive.framework/Versions/Current/uninstall
```

古いバージョンでは、次のものを手動で削除する必要があります。

* `"/Applications/Xamarin Workbooks.app"` の Workbooks アプリを削除します
* `"Applications/Xamarin Inspector.app"` の Inspector アプリを削除します
* アドイン `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Interactive"` と `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Inspector"` を削除します
* `/Library/Frameworks/Xamarin.Interactive.framework` および `/Library/Frameworks/Xamarin.Inspector.framework` にある Inspector のファイルとサポート ファイルを削除します

# <a name="uninstall-the-xamarin-profiler"></a>Xamarin Profiler をアンインストールする

```bash
sudo rm -rf "/Applications/Xamarin Profiler.app"
```

## <a name="uninstall-the-visual-studio-installer"></a>Visual Studio インストーラーをアンインストールする

次のコマンドを使って、Xamarin Universal Installer のすべてのトレースを削除します。

```bash
rm -rf ~/Library/Caches/XamarinInstaller/
rm -rf ~/Library/Caches/VisualStudioInstaller/
rm -rf ~/Library/Logs/XamarinInstaller/
rm -rf ~/Library/Logs/VisualStudioInstaller/
rm -rf ~/Library/Preferences/Xamarin/
rm -rf "~/Library/Preferences/Visual Studio/"
```
