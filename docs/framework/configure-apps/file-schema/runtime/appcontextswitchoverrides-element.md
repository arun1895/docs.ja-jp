---
title: '&lt;AppContextSwitchOverrides&gt;要素'
ms.custom: updateeachrelease
ms.date: 09/19/2018
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2a81c4ec4f679b99f5f5a4d2a2c21270691e93
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839804"
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt;要素
<xref:System.AppContext> クラスで使用される、新機能に対するオプトアウト メカニズムを指定するスイッチを 1 つまたは複数定義します。  
  
 \<configuration>  
 \<ランタイム >  
\<AppContextSwitchOverrides>  
  
## <a name="syntax"></a>構文  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`value`|必須の属性です。<br /><br /> 1 つまたは複数のスイッチ名と関連付けられたブール値を定義します。|  
  
### <a name="value-attribute"></a>属性の値  
  
|[値]|説明|  
|-----------|-----------------|  
|"name=value"|定義済みのスイッチ名と値 (`true`または`false`)。 複数のスイッチの名前/値ペアをセミコロンで区切られます (「;」)。 .NET Framework でサポートされている定義済みのスイッチ名の一覧は、「解説」を参照してください。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|`configuration`|共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。|  
|`runtime`|ランタイム初期化オプションに関する情報を含んでいます。|  
  
## <a name="remarks"></a>Remarks  
 .NET Framework 4.6 以降、`<AppContextSwitchOverrides>`構成ファイル内の要素には、アプリで新しい機能を活用ことができます、ライブラリの以前のバージョンとの互換性を維持するかを判断するための API の呼び出し元ができるようにします。 たとえば、2 つのバージョンのライブラリ、API の動作が変更された場合、`<AppContextSwitchOverrides>`要素には、新しい機能をサポートするバージョンのライブラリに新しい動作を無効にするには、その API の呼び出し元ができるようにします。 アプリで、.NET Framework Api の呼び出しで、`<AppContextSwitchOverrides>`要素は呼び出し元のアプリを含む .NET Framework のバージョンで、アプリが実行されている場合は、新しい機能を有効にする .NET Framework の以前のバージョンを対象にもできます機能。  
  
 `value`の属性、`<AppContextSwitchOverrides>`要素は、1 つまたは複数のセミコロン区切りの名前/値ペアで構成される 1 つの文字列で構成されます。  それぞれの名前が、互換性スイッチを識別し、対応する値はブール値 (`true`または`false`)、スイッチが設定されているかどうかを示します。 スイッチは、既定では、 `false`、およびライブラリが、新しい機能を提供します。 スイッチが設定されている場合のみ前の機能を提供する (つまり、その値が`true`)。 これにより、新しい機能をオプトアウトする以前の動作に依存している呼び出し元を許可するときに既存の API の新しい動作を提供するライブラリです。  
  
 .NET Framework には、次のスイッチがサポートされています。  
  
|スイッチ名|説明|導入されました|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Windows Presentation Foundation がコントロールのレイアウトのレガシ、アルゴリズムを使用するかどうかを制御します。 詳細については、「[軽減策: WPF レイアウト](~/docs/framework/migration-guide/mitigation-wpf-layout.md)」を参照してください。|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|PackageDigitalSignatureManager によってパッケージのパーツに署名するために使用される既定のアルゴリズムが SHA1 または SHA256 がかどうかを制御します。|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|設定すると`false`FIPS が有効にすると、Visual Studio を使用した XAML ベースのワークフロー プロジェクトをデバッグできます。 これがない、 <xref:System.NullReferenceException> System.Activities アセンブリ内のメソッドの呼び出しでがスローされます。|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|デバッガーでのワークフロー インスタンスのチェックサムが MD5 または SHA1 を使用するかどうかを制御します。 | .NET Framework 4.7|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|ソース ファイルと行情報を含めることができますポータブル Pdb の使用時にスタック トレースを取得するかどうかを制御します。 `false` ソース ファイルと行情報を含めるそれ以外の場合、`true`します。|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|コントロールかどうか、<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>メソッドが例外をスロー時に、<xref:System.Drawing.Icon>オブジェクトに PNG フレーム。 詳細については、「[軽減策: Icon オブジェクトの PNG フレーム](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md)」を参照してください。|.NET Framework 4.6|  
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|決定かどうか<xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType>オブジェクトが適切に破棄して、コレクションに追加されたときに、<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>メソッド。 `true` 従来の動作を維持するには`false`プライベート フォントのすべてのオブジェクトを破棄します。 |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|コントロールかどうかのパフォーマンス、<xref:System.Windows.Forms.PrintPreviewDialog>ネットワーク プリンターに適しています。 詳細については、次を参照してください。 [PrintPreviewDialog コントロールの概要](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)します。|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|非同期操作を呼び出し元スレッドのコンテキストをフローしないかどうかを制御します。 詳細については、次を参照してください。 [CurrentCulture と CurrentUICulture のフローのタスクにわたって](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)します。|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|コントロールかどうか、<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>メソッドは、クレームの種類と最後の DNS エントリのみを照合しようとしています。 詳細については、「[軽減策: X509CertificateClaimSet.FindClaims メソッド](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)」を参照してください。|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|変更可能なオブジェクトを返す AuthorizationContext.Empty を許可するかどうかを制御します。|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|コントロールかどうかを超えるパス`MAX_PATH`(260) をスロー、<xref:System.IO.PathTooLongException>します。 詳細については、次を参照してください。[長いパスのサポート](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)します。|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|圧縮解除のネイティブ OS ルーチンを使用するかどうかを制御、<xref:System.IO.Compression.DeflateStream>クラス。 `false` ネイティブ Api を使用するには`true`を使用する、<xref:System.IO.Compression.DeflateStream>実装します。|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|円記号を使用して ("\\")、スラッシュではなく (「/」) のパスの区切り文字として、<xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>プロパティ。 詳細については、次を参照してください。[軽減策: ZipArchiveEntry.FullName パスの区切り文字](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)します。|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|オペレーティング システムの例外で作成されたバック グラウンド スレッドにスローされるかどうかを制御<xref:System.IO.Ports.SerialPort>ストリームは、プロセスを終了します。|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|レガシ パスの正規化が使用されでの URI のパスがサポートされているかどうかを制御、<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType>と<xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>メソッド。 詳細については、次を参照してください。[軽減策: パスの正規化](~/docs/framework/migration-guide/mitigation-path-normalization.md)と[軽減策: パスのコロン チェック](~/docs/framework/migration-guide/mitigation-path-colon-checks.md)します。|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|等値比較をテストするかどうかを制御、<xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType>を持つ 1 つのオブジェクトのプロパティ、 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> 2 番目のオブジェクトのプロパティ。 詳細については、次を参照してください。 [MemberDescriptor.Equals の不適切な実装](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)します。|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|証明書の拡張キー使用法 (EKU) のオブジェクト識別子 (OID) の検証を無効にします。 EKU (拡張キー使用法) 拡張は、キーを使用するアプリケーションを示すオブジェクト識別子 (OID) の集まりです。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|SCH_SEND_AUX_RECORD の使用を無効にして TLS1.0 ブラウザー悪用に対して SSL や TLS (BEAST) の軽減策を無効にします。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|コントロールかどうか、<xref:System.Net.ServicePointManager?displayProperty=nameWithType>と<xref:System.Net.Security.SslStream?displayProperty=nameWithType>クラスは、SSL 3.0 プロトコルを使用できます。 詳細については、「[軽減策: TLS プロトコル](~/docs/framework/migration-guide/mitigation-tls-protocols.md)」を参照してください。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Tls12、Tls11、Tls の既定値に戻します SystemDefault TLS バージョンを無効にします。|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|SslStream TLS サーバー側の警告を無効にします。|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |コントロールかどうか、 [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) ECMAScript V6 および V8 標準に基づくいくつかの制御文字をシリアル化します。 詳細については、「[軽減策: DataContractJsonSerializer での制御文字のシリアル化](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)」を参照してください。| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|コントロールかどうか、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>のタイム ゾーンに対して複数の調整または単一の調整のみをサポートしています。 場合`true`を使用して、<xref:System.TimeZoneInfo>をシリアル化する型し日付と時刻のデータを逆シリアル化。 それ以外の場合、使用して、<xref:System.TimeZone>型で、複数の調整規則をサポートしていません。|.NET Framework 4.6.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|コントロールかどうか、<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType>コンス トラクターの設定、新しいオブジェクトの<xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType>既存のオブジェクト参照を持つプロパティです。 詳細については、「[軽減策: ClaimsIdentity コンストラクター](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md)」を参照してください。|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|コントロールかどうかを再利用しようとすると、<xref:System.Security.Cryptography.AesCryptoServiceProvider>復号化がスローされます、<xref:System.Security.Cryptography.CryptographicException>します。 詳細については、次を参照してください。 [AesCryptoServiceProvider の復号化は、再利用可能な変換を提供します。](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)します。|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|コントロールかどうかの値、 [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle)プロパティは、 [IntPtr](xref:System.IntPtr)こと表しますウィンドウのメモリ位置を処理するかどうか、ウィンドウ ハンドル (HWND)。 詳細については、「[Mitigation: CspParameters.ParentWindowHandle Expects an HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md)」 (軽減策: CspParameters.ParentWindowHandle で HWND を受け取る) を参照してください。 |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|SignedCMS のいくつかの操作の既定値は SHA1 または SHA256 であるかどうかを判断します。 |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|一部の SignedXML 操作の既定値が SHA1 または SHA256 かどうかを判断します。 |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|決定かどうか、`TransportWithMessageCredential`セキュリティ モードで、符号なしのメッセージは、"to"ヘッダー。 これは、オプトイン スイッチです。 詳細については、次を参照してください。 [、.NET Framework 4.6.1 におけるランタイムの変更](~/docs/framework/migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf)します。|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|コントロールかどうか、<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>コンス トラクターがスローされます、<xref:System.ArgumentException>場合は、要素の 1 つ`null`します。|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|CSG キー ストレージ プロバイダーが例外をスローします X509 を使用しようとすると、証明書を使用するかどうかを判断します。 詳細については、次を参照してください。 [WCF トランスポート セキュリティは、CNG を使用して格納される証明書をサポートしている](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)します。|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|自己ホスト型サービスを HTTP トランスポートを使用する場合は、この値を設定`true`により、アプリケーションの追加を無視する WCF、`Connection: close`要求の応答ヘッダーをヘッダー。 この値を設定`false`追加できるように、`Connection: close`に、応答ヘッダー、ヘッダー。 応答が送信された後に、要求のソケットを閉じるときの結果。|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|再入可能サービスのインスタンスを一度に実行の 1 つのスレッドに制限することに起因するデッドロックを処理します。|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|と共に`Switch.System.Net.DontEnableSchUseStrongCrypto`、WCF メッセージ セキュリティには、TLS 1.1 および TLS 1.2 が使用しているかどうかを決定します。|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|値`false`プロトコルの選択をオペレーティング システムを許可する既定の構成を設定します。 値`true`使用可能な最も高いプロトコルを既定値に設定します。 (サービスの以前の framework バージョンのブランチにも使用可能)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|既定のメッセージ署名の WCF で MSMQ のメッセージのアルゴリズムが SHA1 または SHA256 かどうかを判断します。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|WCF が、SHA1 または SHA256 ハッシュを使用して名前付きパイプのランダムな名前を生成するかどうかを制御します。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|スローするかどうかを制御する[NullReferenceException](xref:System.NullReferenceException)例外メッセージが null の場合。|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|呼び出し元に、サービスの起動時にスローされた例外が反映されるかどうかを制御、<xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>メソッド。|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|場合によってはデコードされた特定のパーセントでエンコードされた文字を常に保たれるエンコードされたようになりましたかどうかを判断します。 場合`true`、デコードされた。 それ以外は`false`します。|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Uri に Unicode の双方向文字の処理を決定します。 `true` Uri; からそれらを削除するには`false`を保持し、そのパーセントでエンコードします。|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Windows Presentation Foundation が以前のアルゴリズムを適用するかどうかを指定します (`true`) または新しいアルゴリズム (`false`) 内に領域を割り当てる\*-列。 詳細については、「[Mitigation: Grid Control's Space Allocation to Star-columns](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md)」 (軽減策: グリッド コントロールの *-column へのディスク領域の割り当て) を参照してください。 |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|コントロールの選択範囲を発生させる前に、選択した値のプロパティの値を更新、セレクターまたはタブが常にして制御するかどうかは、イベントを変更します。|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|非装飾ベースの選択レンダリングが使用できるかどうか、<xref:System.Windows.Controls.TextBox>と<xref:System.Windows.Controls.PasswordBox>閉塞文字列を表示するコントロール (`false`)、装飾層のみのテキストをレンダリングするかどうか、または (`true`)。|.NET Framework 4.7.2|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|システムごとの DPI 変更が発生するかどうかを決定します (値の`false`) またはモニターごとの単位 (値の`true`)。|.NET Framework 4.6.2|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|開発者が特別に処理する必要があるかどうかを決定、<xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>コントロールのテキストが存在する場合のアクション。 `true` 処理するために、<xref:System.Windows.Forms.DomainUpDown.UpButton>アクション。`false`の<xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>と<xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>を正しく同期するアクション。|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|カスタムのコードは無効になります<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>例外をスローせず、メッセージを安全にフィルター処理する実装時に、<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>メソッドが呼び出されます。 詳細については、[「軽減策: カスタムの IMessageFilter.PreFilterMessage 実装」](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)を参照してください。|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|決定かどうか、<xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>プロパティは、ユーザーが、入れ子になったから、メニューを開いたときにソース コントロールを返します<xref:System.Windows.Forms.ToolStripMenuItem>コントロール。 `true` 返す`null`、従来の動作です。`false`をソース コントロールを返します。|.NET Framework 4.7.2|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|省略可能なのかどうかを判断します`WM_POINTER`-ベースのタッチ/スタイラス スタックが WPF アプリケーションで有効にします。 詳細については、次を参照してください[軽減策: ポインター ベースのタッチおよびスタイラスのサポート。](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|チェックサムで使用される既定のハッシュ アルゴリズムが SHA256 であるかどうかを判断します (`false`) または SHA1 (`true`)。|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|レガシかどうかを制御[NullReferenceException](xref:System.NullReferenceException)より具体的には、例外の原因を示す例外がスローされます (など、 [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException)または、 [FileNotFoundException](xref:System.IO.FileNotFoundException)します。 処理に依存するコードで使用するためには、 [NullReferenceException](xref:System.NullReferenceException)します。 | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|コントロールは、ユーザー補助機能と .NET Framework 4.7.1 以降で利用可能かどうかが有効または無効にします。 | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|ユーザー補助機能、.NET Framework 4.7.2 で使用できるかどうかが有効になっているコントロール (`false`) か無効 (`true`)。 場合`true`、`Switch.UseLegacyAccessibilityFeatures`必要もあります`true`.NET Framework 4.7.1 のアクセシビリティ機能を有効にします。|.NET Framework 4.7.2|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|XSD スキーマ検証で複合キーに空のキー シーケンスを無視するかどうかを制御します。 詳細については、次を参照してください。[軽減策: XML スキーマ検証](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md)です。|.NET Framework 4.6|  
  
> [!NOTE]
>  追加する代わりに、`AppContextSwitchOverrides`アプリケーション構成ファイルに要素を設定することも、スイッチ プログラムで呼び出すことによって、 `static` (で C# の場合) または`Shared`(Visual Basic) で<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>メソッド。  
  
 ライブラリ開発者は、そのライブラリの以降のバージョンで導入された変更された機能をオプトアウトする呼び出し元を許可するカスタムのスイッチも定義できます。 詳細については、<xref:System.AppContext> クラスを参照してください。  
  
## <a name="switches-in-aspnet-applications"></a>ASP.NET アプリケーションでのスイッチ

追加することで互換性の設定を使用する ASP.NET アプリケーションを構成することができます、 [\<追加 >](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md)要素を[ \<appSettings >](~/docs/framework/configure-apps/file-schema/appsettings/index.md) web.config ファイルのセクション。 

次の例では、`<add>`に 2 つの設定を追加する要素、 `<appSettings>` web.config ファイルのセクション。

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>例

 次の例では、`AppContextSwitchOverrides`要素で、1 つのアプリケーションの互換性スイッチを定義する`Switch.System.Globalization.NoAsyncCurrentCulture`、カルチャから非同期メソッド呼び出し内のスレッド間を移動できません。  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 次の例では、`AppContextSwitchOverrides`要素で 2 つのアプリケーションの互換性スイッチを定義する`Switch.System.Globalization.NoAsyncCurrentCulture`と`Switch.System.IO.BlockLongPaths`します。 2 つの名前/値ペアをセミコロンで区切ってことに注意してください。  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.AppContext?displayProperty=nameWithType>  
 [\<ランタイム > 要素](runtime-element.md)  
 [\<configuration> 要素](../configuration-element.md)
