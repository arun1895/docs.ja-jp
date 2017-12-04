---
title: "デリゲート (F#)"
description: "F# でデリゲートを使用する方法を説明します。"
keywords: "visual f#, f#, 関数型プログラミング"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 719948a3-83ba-4618-82d6-a22945c3f4b0
ms.openlocfilehash: c929a342ab4c5098062417691a99cee3b007d2d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="delegates"></a>デリゲート

デリゲートは、オブジェクトとして関数呼び出しを表します。 F# では、通常使用することは関数の値をファーストクラスの値として関数を表すただし、デリゲートには .NET Framework で使用し、相互運用することが期待する Api を使用したときに、必要なため。 用に設計されたオーサリング ライブラリが他の .NET Framework 言語から使用も使用できます。


## <a name="syntax"></a>構文

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>コメント
前の構文で`type1`引数の型または型を表すと`type2`戻り値の型を表します。 引数の型によって表される`type1`自動的にカリー化します。 これは対象の関数の引数はカリー化された場合は、タプルの形式を使用するこの型、タプルの形式に既に含まれている引数をかっこで囲まれた組のことを示します。 自動カリー化には、対象のメソッドに一致する組の引数を残して、かっこのセットを削除します。 各ケースで使用する構文のコード例を参照してください。

デリゲートは、f# 関数値、および静的に関連付けることができます。 またはインスタンス メソッドです。 F# の関数の値は、デリゲート コンス トラクターに引数として直接渡すことができます。 静的メソッドは、クラスとメソッドの名前を使用して、デリゲートを構築します。 インスタンス メソッドでは、オブジェクトのインスタンスと 1 つの引数でメソッドを提供します。 どちらの場合、メンバー アクセス演算子 (`.`) を使用します。

`Invoke`デリゲート型のメソッドは、カプセル化された関数を呼び出します。 また、デリゲートは、かっこがない場合は、Invoke メソッドの名前を参照することによって関数の値として渡されますことができます。

次のコードは、クラスのさまざまなメソッドを表すデリゲートを作成するための構文を示しています。 メソッドは静的メソッドまたはインスタンス メソッドで、かどうかと、引数はタプル形式またはカリー化された形式であるかどうか、に応じてを宣言して、デリゲートを割り当てるのための構文は若干異なりますです。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

次のコードでは、デリゲートを使用するさまざまな方法の一部を示します。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

上記のコード例の出力は次のとおりです。

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>関連項目
[F# 言語リファレンス](index.md)

[パラメーターと引数](parameters-and-arguments.md)

[イベント](members/events.md)