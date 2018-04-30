### <a name="exception-message-has-changed-for-failed-datacontract-serialization-in-case-of-an-unknown-type"></a><span data-ttu-id="41d96-101">不明な型の場合に失敗した DataContract シリアル化の例外メッセージが変更された</span><span class="sxs-lookup"><span data-stu-id="41d96-101">Exception message has changed for failed DataContract serialization in case of an unknown type</span></span>

|   |   |
|---|---|
|<span data-ttu-id="41d96-102">説明</span><span class="sxs-lookup"><span data-stu-id="41d96-102">Details</span></span>|<span data-ttu-id="41d96-103">.NET Framework 4.6 以降では、"既知の型" がないために <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> または <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> のシリアル化または逆シリアル化が失敗した場合に提供される例外メッセージが明確化されました。</span><span class="sxs-lookup"><span data-stu-id="41d96-103">Beginning in the .NET Framework 4.6, the exception message given if a <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> or <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=name> fails to serialize or deserialize due to missing 'known types' has been clarified.</span></span>|
|<span data-ttu-id="41d96-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="41d96-104">Suggestion</span></span>|<span data-ttu-id="41d96-105">アプリは、特定の例外メッセージに依存しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41d96-105">Apps should not depend on specific exception messages.</span></span> <span data-ttu-id="41d96-106">アプリがこのメッセージに依存している場合は、新しいメッセージを使うように更新するか、(可能であれば) 例外の種類のみに依存するように変更してください。</span><span class="sxs-lookup"><span data-stu-id="41d96-106">If an app depending on this message, please either update it to expect the new message or (preferably) change it to depend only on the exception type.</span></span>|
|<span data-ttu-id="41d96-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="41d96-107">Scope</span></span>|<span data-ttu-id="41d96-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="41d96-108">Edge</span></span>|
|<span data-ttu-id="41d96-109">Version</span><span class="sxs-lookup"><span data-stu-id="41d96-109">Version</span></span>|<span data-ttu-id="41d96-110">4.6</span><span class="sxs-lookup"><span data-stu-id="41d96-110">4.6</span></span>|
|<span data-ttu-id="41d96-111">型</span><span class="sxs-lookup"><span data-stu-id="41d96-111">Type</span></span>|<span data-ttu-id="41d96-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="41d96-112">Runtime</span></span>|
|<span data-ttu-id="41d96-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="41d96-113">Affected APIs</span></span>|<ul><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Runtime.Serialization.Json.DataContractJsonSerializerSettings)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Runtime.Serialization.DataContractSerializerSettings)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type})?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.String,System.String,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.DataContractSerializer.%23ctor(System.Type,System.Xml.XmlDictionaryString,System.Xml.XmlDictionaryString,System.Collections.Generic.IEnumerable{System.Type},System.Int32,System.Boolean,System.Boolean,System.Runtime.Serialization.IDataContractSurrogate,System.Runtime.Serialization.DataContractResolver)?displayProperty=nameWithType></li></ul>|
