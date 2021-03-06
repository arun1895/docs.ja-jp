---
title: C# 7.2 の新機能
description: C# 7.2 の新機能の概要。
ms.date: 08/16/2017
ms.openlocfilehash: 93b0a5281db841abdb8de0865dfe4b13be6d9ee2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181174"
---
# <a name="whats-new-in-c-72"></a>C# 7.2 の新機能

C# 7.2 は、便利な機能が多数追加された、もう 1 つのポイント リリースです。
このリリースのテーマの 1 つは、不要なコピーや割り当てを回避して、さまざまな値の型の操作をより効率的に行うことです。 

他の機能も、小さくても、あると助かる機能です。

C# 7.2 では[言語バージョンの選択](../language-reference/configure-language-version.md)の構成要素を使用して、コンパイラ言語バージョンを選択します。

このリリースの新しい言語機能は次のとおりです。

* [安全で効率的なコードを記述するための手法](#safe-efficient-code-enhancements)
  - 参照セマンティクスを使用したさまざまな値の型の使用を有効にする、構文の機能強化の組み合わせ。
* [末尾以外の名前付き引数](#non-trailing-named-arguments)
  - 名前付き引数の後ろに位置引数を続けることができます。
* [数値リテラルでの先頭のアンダースコア (_)](#leading-underscores-in-numeric-literals)
  - 数値リテラルの印刷桁の前に先頭のアンダースコア(_) を含めることができるようになりました。
* [`private protected` アクセス修飾子](#private-protected-access-modifier)
  - `private protected` アクセス修飾子によって、同じアセンブリ内の派生クラスのアクセスが有効になります。

## <a name="safe-efficient-code-enhancements"></a>安全で効率的なコードの機能拡張

7.2 で導入された言語機能では、参照セマンティクスを使用しているときに、さまざまな値の型を使用できます。 これらは、参照型の使用に関連するメモリの割り当てを生じさせずに、値の型のコピーを最小限に抑えてパフォーマンスを改善するように設計されています。 次のような機能があります。

 - パラメーターの `in` 修飾子。引数が参照によって渡されるが、呼び出されたメソッドでは変更されないことを指定します。 引数に `in` 修飾子を加えることは、[ソース互換性がある変更](version-update-considerations.md#source-compatible-changes)です。
 - メソッド戻りの `ref readonly` 修飾子。メソッドが参照によってその値を戻しますが、そのオブジェクトに対する書き込みを許可しないことを指定します。 戻り値が値に割り当てられている場合、`ref readonly` 修飾子を追加することは、[ソース互換性がある変更](version-update-considerations.md#source-compatible-changes)です。 既存の `ref` return ステートメントに `readonly` 修飾子を追加することは、[互換性がない変更](version-update-considerations.md#incompatible-changes)です。 呼び出し元は、`readonly` 修飾子を含むように `ref` ローカル変数の宣言を更新する必要があります。
 - `readonly struct` 宣言。変更不可の構造体で、そのメンバー メソッドの `in` パラメーターとして渡す必要があることを示します。 既存の構造体の宣言に `readonly` 修飾子を追加することは、[バイナリ互換性がある変更](version-update-considerations.md#binary-compatible-changes)です。
 - `ref struct` 宣言。構造体型がマネージド メモリに直接アクセスし、常にスタック割り当てが必要であることを示します。 既存の `struct` の宣言に `ref` 修飾子を追加することは、[互換性がない変更](version-update-considerations.md#incompatible-changes)です。 `ref struct` をクラスのメンバーにすることはできません。また、ヒープ上に割り当てられている可能性がある他の場所で使用することもできません。

これらすべての変更点の詳細については、[安全で効率的なコードを記述する方法](../write-safe-efficient-code.md)に関するページを参照してください。

## <a name="non-trailing-named-arguments"></a>末尾以外の名前付き引数

メソッド呼び出しで、位置引数の前に名前付き引数を使用できるようになりました。ただし、そのような名前付き引数が正しい位置にある場合です。 詳細については、「[名前付き引数と省略可能な引数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)」を参照してください。

## <a name="leading-underscores-in-numeric-literals"></a>数値リテラルでの先頭のアンダースコア (_)

C# 7.0 の桁区切り記号のサポートの実装では、`_` をリテラル値の最初の文字にすることができませんでした。 16 進とバイナリの数値リテラルの先頭に `_` を使用できるようになりました。 

例:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>_private protected_ アクセス修飾子

最後に、新しい複合アクセス修飾子: `private protected` は、同じアセンブリで宣言されているクラスまたは派生クラスを含むことでメンバーにアクセスできることを示しています。 `protected internal` は同じアセンブリの派生クラスまたはクラスによるアクセスを許可していますが、`private protected` は同じアセンブリで宣言された派生型へのアクセスを制限しています。

詳細については、言語リファレンスの[アクセス修飾子](../language-reference/keywords/access-modifiers.md)に関するページを参照してください。
