---
title: プラットフォーム呼び出しの例
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 330d8ff784218483caf153b5c14f8a30df2d2452
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386780"
---
# <a name="platform-invoke-examples"></a>プラットフォーム呼び出しの例
User32.dll で **MessageBox** 関数を定義し、引数として単純な文字列を渡して呼び出す例を次に示します。 この例では、<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> フィールドは **Auto** に設定されているため、ターゲット プラットフォームで文字の幅と文字列のマーシャリングを決定できます。  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] 
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] 
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 その他の例については、「[Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)」(プラットフォーム呼び出しによるデータのマーシャリング) を参照してください。  
  
## <a name="see-also"></a>参照  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [マネージ コードでのプロトタイプの作成](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [文字セットの指定](../../../docs/framework/interop/specifying-a-character-set.md)
