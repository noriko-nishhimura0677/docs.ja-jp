---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: 37657a0611180d5b4c48b3e1778d33861afa5a74
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500573"
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)

カスタム属性クラスの使用方法を決定します。 <xref:System.AttributeUsageAttribute> は、カスタム属性定義に適用する属性です。 `AttributeUsage` 属性を使用すると、以下を制御できます。

- 適用できるプログラム要素属性。 使用法を制限しない限り、属性は以下のプログラム要素のいずれかに適用できます。
  - アセンブリ
  - name
  - フィールド
  - event
  - メソッド
  - param
  - property
  - return
  - 型
- 1 つのプログラム要素に属性を複数回適用できるかどうか。
- 属性が派生クラスに継承されるかどうか。

明示的に適用すると、既定の設定は次の例のようになります。

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

この例で `NewAttribute` クラスはサポートされている任意のプログラム要素に適用できます。 ただし、各エンティティに適用できるのは 1 回のみです。 基底クラスに適用すると、属性は派生クラスに継承されます。

<xref:System.AttributeUsageAttribute.AllowMultiple> 引数と <xref:System.AttributeUsageAttribute.Inherited> 引数は省略できるので、次のコードは同じ効果を持ちます。

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

最初の <xref:System.AttributeUsageAttribute> 引数は、<xref:System.AttributeTargets> 列挙型の 1 つまたは複数の要素でなければなりません。 次の例のように、複数のターゲット型を OR 演算子で 1 つにまとめることができます。

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

C# 7.3 以降、プロパティ、または自動実装バッキング フィールドに属性を適用できるようになりました。 属性に `field` 指定子を指定しない限り、属性はプロパティに適用されます。 その両方の例を次に示します。

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<xref:System.AttributeUsageAttribute.AllowMultiple> 引数が `true` の場合、次の例のように、結果の属性を 1 つのエンティティに複数回適用できます。

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

この例では、`AllowMultiple` が `true` に設定されているので、`MultiUseAttribute` を繰り返し適用できます。 示されているどちらの形式でも、複数の属性を適用できます。

<xref:System.AttributeUsageAttribute.Inherited> が `false` の場合、属性は属性クラスから派生したクラスに継承されません。 例:

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

この例で、`NonInheritedAttribute` は継承によって `DClass` に適用されません。

## <a name="remarks"></a>コメント

`AttributeUsage` 属性は、1 回だけ使用できる属性です。同じクラスに複数回適用することはできません。 `AttributeUsage` は <xref:System.AttributeUsageAttribute> の別名です。

詳しくは、「[リフレクションを使用した属性へのアクセス (C#)](accessing-attributes-by-using-reflection.md)」をご覧ください。

## <a name="example"></a>例

次の例を見ると、<xref:System.AttributeUsageAttribute> 属性に対する <xref:System.AttributeUsageAttribute.Inherited> 引数と <xref:System.AttributeUsageAttribute.AllowMultiple> 引数の効果、およびクラスに適用されているカスタム属性の列挙方法がわかります。

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a>出力例

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a>参照

- <xref:System.Attribute>  
- <xref:System.Reflection>  
- [C# プログラミング ガイド](../..//index.md)  
- [属性](../../../..//standard/attributes/index.md)  
- [リフレクション (C#)](../reflection.md)  
- [属性](index.md)  
- [カスタム属性の作成 (C#)](creating-custom-attributes.md)  
- [リフレクションを使用した属性へのアクセス (C#)](accessing-attributes-by-using-reflection.md)
