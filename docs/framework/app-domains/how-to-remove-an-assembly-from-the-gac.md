---
title: '方法 : グローバル アセンブリ キャッシュからアセンブリを削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18148d21c6329167437cd1ca3ea1f4635c7a28a0
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452535"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a>方法 : グローバル アセンブリ キャッシュからアセンブリを削除する
グローバル アセンブリ キャッシュ (GAC) からアセンブリを削除するには、次の 2 つの方法があります。  
  
-   [グローバル アセンブリ キャッシュ ツール (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) を使用する方法。 このオプションを使用すると、開発およびテスト時に GAC に配置したアセンブリをアンインストールできます。  
  
-   [Windows インストーラー](/windows/desktop/Msi/windows-installer-portal)を使用する方法。 インストール パッケージをテストするとき、そして実稼働システムのために、アセンブリをアンインストールするにはこのオプションを使用する必要があります。  
  
### <a name="removing-an-assembly-with-gacutilexe"></a>Gacutil.exe によるアセンブリの削除  
  
1.  コマンド プロンプトに次のコマンドを入力します。  
  
     **gacutil –u** \<*assembly name*>  
  
     このコマンドで、*assembly name* はグローバル アセンブリ キャッシュから削除するアセンブリの名前です。  
  
    > [!WARNING]
    >  アセンブリが一部のアプリケーションで引き続き必要となる可能性があるので、Gacutil.exe を使用して実稼働システムのアセンブリを削除しないでください。 代わりに、GAC にインストールされる各アセンブリの参照カウントを保持する Windows インストーラーを使用する必要があります。  
  
 次の例では、`hello.dll` という名前のアセンブリが、グローバル アセンブリ キャッシュから削除されます。  
  
```  
gacutil -u hello  
```  
  
### <a name="removing-an-assembly-with-windows-installer"></a>Windows インストーラーでアセンブリを削除する  
  
1.  **コントロール パネル**の**プログラムと機能**アプリで、アンインストールするアプリを選択します。 インストール パッケージが GAC にアセンブリを配置した場合、それらが別のアプリケーションによって使用されないときは、Windows インストーラーはそれらを削除します。  
  
    > [!NOTE]
    >  Windows インストーラーは、GAC にインストールされたアセンブリの参照カウントを保持します。 アセンブリの参照カウントがゼロになる場合 (それが Windows インストーラー パッケージによってインストールされたアプリケーションによって使用されないことを示す) にのみ、アセンブリが GAC から削除されます。  
  
## <a name="see-also"></a>参照  
- [アセンブリとグローバル アセンブリ キャッシュの使用](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
- [方法: グローバル アセンブリ キャッシュにアセンブリをインストールする](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
- [Gacutil.exe (グローバル アセンブリ キャッシュ ツール)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
