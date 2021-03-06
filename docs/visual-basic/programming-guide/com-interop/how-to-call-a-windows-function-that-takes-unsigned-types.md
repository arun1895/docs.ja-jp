---
title: '方法: 符号なしの型を使用する Windows の機能を呼び出す (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: d66b74f06abe6b337c24859c444f7a8c2aa52c13
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524566"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>方法: 符号なしの型を使用する Windows の機能を呼び出す (Visual Basic)
クラス、モジュール、または符号なし整数型のメンバーを含む構造体を使用する場合は、Visual Basic でのこれらのメンバーを表示できます。  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>符号なしの型を受け取る Windows 関数を呼び出す  
  
1.  使用して、 [Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)関数を保持するためのライブラリ、その名前がそのライブラリでは、その呼び出し元のシーケンスがおよび呼び出し時に文字列を変換する方法は、Visual Basic を通知します。  
  
2.  `Declare`ステートメントを使用して`UInteger`、 `ULong`、 `UShort`、または`Byte`必要に応じて、各パラメーターでは、符号なしの型にします。  
  
3.  Windows 関数の名前と使用されている定数の値を見つけるには、ドキュメントを参照してください。 これらの多くは、WinUser.h ファイルで定義されます。  
  
4.  コードで必要な定数を宣言します。 多くの Windows 定数は、32 ビット符号なしの値、およびこれらを宣言する必要があります`As``UInteger`します。  
  
5.  通常の方法で関数を呼び出します。 次の例は、Windows の関数を呼び出して`MessageBox`、符号なし整数の引数を受け取ります。  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     関数をテストする`messageThroughWindows`を次のコード。  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  `UInteger`、 `ULong`、 `UShort`、および`SByte`データ型はの一部、 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) に CLS 準拠コードのコンポーネントを使用できないようにします。それらを使用します。  
  
    > [!IMPORTANT]
    >  Windows アプリケーション プログラミング インターフェイス (API) など、アンマネージ コードに呼び出しを行う、潜在的なセキュリティ リスクにコードを公開します。  
  
    > [!IMPORTANT]
    >  Windows API を呼び出すと、アンマネージ コード アクセス許可が必要です。 詳細については、次を参照してください。<xref:System.Security.Permissions.SecurityPermission>と[コード アクセス許可](https://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675)します。  
  
## <a name="see-also"></a>関連項目  
 [データの種類](../../../visual-basic/language-reference/data-types/index.md)  
 [整数データ型](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [UInteger データ型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [チュートリアル : Windows API の呼び出し](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
