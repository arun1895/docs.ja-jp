---
title: -checked (C# コンパイラ オプション)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: cf6fa0e87654d0f9d61f34ea9b29ad80921a5720
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084856"
---
# <a name="-checked-c-compiler-options"></a>-checked (C# コンパイラ オプション)
**-checked** オプションは、データ型の範囲外の値になる整数の算術ステートメントと、[checked](../../../csharp/language-reference/keywords/checked.md) または [unchecked](../../../csharp/language-reference/keywords/unchecked.md) キーワードのスコープ内に含まれない整数の算術ステートメントで、ランタイム例外が発生するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a>コメント  
 `checked` または `unchecked` キーワードのスコープ内に含まれる整数の算術ステートメントは、**-checked** オプションの作用の対象になりません。  
  
 `checked` または `unchecked` キーワードのスコープ内に含まれない整数の算術ステートメントがデータ型の範囲外の値になり、**-checked+** (または **-checked**) がコンパイル時に使用されている場合は、そのステートメントでランタイム例外が発生します。 **-checked-** がコンパイル時に使用された場合、そのステートメントでランタイム例外は発生しません。  
  
 このオプションの既定値は **-checked-** です。オーバーフロー チェックは無効になっています。
 
 場合によっては、大規模アプリケーションの構築に使用される自動化ツールによって -checked が + に設定されます。 -checked- を使用する場合のシナリオの 1 つは、-checked- を指定してツールのグローバルな既定値をオーバーライドすることです。
 
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ]** ページを開きます。 詳細については、「[Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)」([ビルド] ページ (プロジェクト デザイナー) (C#)) を参照してください。  
  
2.  **[ビルド]** プロパティ ページをクリックします。  
  
3.  **[詳細設定]** ボタンをクリックします。  
  
4.  **[演算のオーバーフローおよびアンダーフローのチェック]** プロパティを変更します。  
  
 プログラムによってこのコンパイラ オプションにアクセスする方法については、<xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A> に関する記事をご覧ください。  
  
## <a name="example"></a>例  
 次のコマンドは `t2.cs` をコンパイルします。 コマンドで使用されている `-checked` は、ファイル内の整数の算術ステートメントのうち、`checked` または `unchecked` キーワードのスコープ内に含まれず、データ型の範囲外の値になるステートメントで、ランタイム例外が発生することを指定します。  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a>参照  

- [C# コンパイラ オプション](../../../csharp/language-reference/compiler-options/index.md)  
- [プロジェクトおよびソリューションのプロパティの管理](/visualstudio/ide/managing-project-and-solution-properties)  
