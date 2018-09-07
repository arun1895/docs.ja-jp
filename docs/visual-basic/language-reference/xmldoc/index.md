---
title: ドキュメント コメントとして推奨される XML タグ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 3b2dec4224006d35fb9add11e170b9dcbeeafcf3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881282"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="cfd9b-102">ドキュメント コメントとして推奨される XML タグ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="cfd9b-103">Visual Basic コンパイラでは、ドキュメントのコメントをコードに XML ファイルを処理できます。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="cfd9b-104">その他のツールを使用して、ドキュメントに XML ファイルを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="cfd9b-105">XML コメントは、型などのコード コンストラクトでは許可し、メンバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="cfd9b-106">部分の型は、型の 1 つだけの一部はコメントのメンバーに制限はありませんが、XML コメントを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfd9b-107">ドキュメントのコメントは、名前空間には適用できません。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="cfd9b-108">理由は、1 つの名前空間は、複数のアセンブリをまたがることができ、同時に読み込む必要がないすべてのアセンブリのことです。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="cfd9b-109">コンパイラは、有効な XML である任意のタグを処理します。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="cfd9b-110">次のタグは、ユーザー ドキュメントでよく使用される機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="cfd9b-111">\<c></span><span class="sxs-lookup"><span data-stu-id="cfd9b-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="cfd9b-112">\<code></span><span class="sxs-lookup"><span data-stu-id="cfd9b-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="cfd9b-113">\<example></span><span class="sxs-lookup"><span data-stu-id="cfd9b-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="cfd9b-114">[\<例外 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="cfd9b-115">[\<含める >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="cfd9b-116">\<list></span><span class="sxs-lookup"><span data-stu-id="cfd9b-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="cfd9b-117">\<para></span><span class="sxs-lookup"><span data-stu-id="cfd9b-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="cfd9b-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="cfd9b-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="cfd9b-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="cfd9b-120">[\<アクセス許可 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="cfd9b-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="cfd9b-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="cfd9b-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="cfd9b-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="cfd9b-123">[\<参照してください >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="cfd9b-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="cfd9b-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="cfd9b-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="cfd9b-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cfd9b-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="cfd9b-127">\<value></span><span class="sxs-lookup"><span data-stu-id="cfd9b-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="cfd9b-128">(<sup>1</sup>コンパイラが構文を検証します)。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfd9b-129">山かっこをドキュメントのコメントのテキストで表示される場合を使用して、`&lt;`と`&gt;`します。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="cfd9b-130">たとえば、文字列`"&lt;text in angle brackets&gt;"`として表示されます`<text in angle brackets>`します。</span><span class="sxs-lookup"><span data-stu-id="cfd9b-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd9b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfd9b-131">See Also</span></span>  
 [<span data-ttu-id="cfd9b-132">XML の使用によるコードのドキュメントの作成</span><span class="sxs-lookup"><span data-stu-id="cfd9b-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="cfd9b-133">/doc</span><span class="sxs-lookup"><span data-stu-id="cfd9b-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="cfd9b-134">方法: XML ドキュメントを作成する</span><span class="sxs-lookup"><span data-stu-id="cfd9b-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)