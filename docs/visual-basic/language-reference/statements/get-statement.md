---
title: Get ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 32b89caf56c010f9e6ed7b78309ef30b56b682ea
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332897"
---
# <a name="get-statement"></a>Get ステートメント
宣言を`Get`プロパティ プロシージャのプロパティの値を取得するために使用します。  
  
## <a name="syntax"></a>構文  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>指定項目  
  
|用語|定義|  
|---|---|  
|`attributelist`|任意。 参照してください[属性一覧](../../../visual-basic/language-reference/statements/attribute-list.md)します。|  
|`accessmodifier`|1 つだけでは省略可能、`Get`と`Set`このプロパティ内のステートメント。 次のいずれかの値を指定します。<br /><br /> -   [保護されています。](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [プライベート](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 参照してください[アクセス レベルを Visual Basic で](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)します。|  
|`statements`|任意。 場合に実行する 1 つまたは複数のステートメント、`Get`プロパティ プロシージャが呼び出されます。|  
|`End Get`|必須。 定義を終了、`Get`プロパティ プロシージャ。|  
  
## <a name="remarks"></a>Remarks  
 すべてのプロパティがあります、`Get`プロパティ プロシージャ、プロパティが指定されていない限り`WriteOnly`します。 `Get`プロパティの現在の値を返すプロシージャを使用します。  
  
 Visual Basic がプロパティを自動的に呼び出します`Get`プロシージャ式は、プロパティの値を要求するとします。  
  
 プロパティ宣言の本体でのみ、プロパティを含めることができます`Get`と`Set`間で、プロシージャ、 [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)と`End Property`ステートメント。 これらのプロシージャ以外のものを格納できません。 具体的には、プロパティの現在の値を格納できません。 に、プロパティ プロシージャのいずれかの内部で保存する場合、その他のプロパティ プロシージャ アクセスできないために、プロパティの外部には、この値を格納する必要があります。 値を格納する通常の方法も、[プライベート](../../../visual-basic/language-reference/modifiers/private.md)プロパティと同じレベルで宣言された変数。 定義する必要があります、`Get`適用されるプロパティ内のプロシージャです。  
  
 `Get`プロシージャの既定値はその包含するプロパティのアクセス レベルを使用しない限り`accessmodifier`で、`Get`ステートメント。  
  
## <a name="rules"></a>ルール  
  
-   **混合アクセス レベル。** 必要に応じていずれかの異なるアクセス レベルを指定することができます、読み取り/書き込みプロパティを定義する場合、`Get`または`Set`両方ではなく、プロシージャ。 これを行うと、プロシージャのアクセス レベル、プロパティのアクセス レベルよりもより制限の厳しい場合があります。 例では、プロパティが宣言されている場合、 `Friend`、宣言することができます、`Get`プロシージャ`Private`、なく`Public`します。  
  
     定義する場合、`ReadOnly`プロパティ、`Get`プロシージャは、全体のプロパティを表します。 レベル別のアクセスを宣言することはできません`Get`プロパティの 2 つのアクセス レベルを設定することがあるため、します。  
  
-   **型を返します。** [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)が返す値のデータ型を宣言できます。 `Get`プロシージャが自動的にそのデータ型を返します。 任意のデータ型または列挙型、構造体、クラス、インターフェイスの名前を指定することができます。  
  
     場合、`Property`ステートメントが指定されなかった`returntype`、プロシージャが返す`Object`します。  
  
## <a name="behavior"></a>動作  
  
-   **プロシージャを終了します。** ときに、`Get`プロパティ値を要求するステートメント内で、プロシージャは、呼び出し元のコードに返す、実行が続行します。  
  
     `Get` プロパティ プロシージャは、いずれかを使用して値を返すことができます、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)またはプロパティ名に、戻り値を割り当てることで。 詳細については、「戻り値」を参照してください[関数ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)します。  
  
     `Exit Property`と`Return`ステートメントでは、プロパティ プロシージャからすぐに終了します。 任意の数の`Exit Property`と`Return`ステートメントは、手順では、どこでも表示でき、組み合わせることができます`Exit Property`と`Return`ステートメント。  
  
-   **値を返します。** 値を返す、`Get`プロシージャ、プロパティ名に値を割り当てるか、含めることで、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)します。 `Return`ステートメントを同時に割り当てます、`Get`プロシージャを返す値し、手順を終了します。  
  
     使用する場合`Exit Property`、プロパティ名に値を割り当てることがなく、`Get`プロパティのデータ型の既定値を返します。 詳細については、「戻り値」を参照してください[関数ステートメント](../../../visual-basic/language-reference/statements/function-statement.md)します。  
  
     次の例は、読み取り専用プロパティの 2 つの方法を示しています。`quoteForTheDay`プライベート変数に保持された値を返すことができます`quoteValue`します。  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>例  
 次の例では、`Get`ステートメント、プロパティの値を返します。  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>関連項目  
 [Set ステートメント](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Property ステートメント](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit ステートメント](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [クラスとオブジェクト](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [チュートリアル : クラスの定義](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
