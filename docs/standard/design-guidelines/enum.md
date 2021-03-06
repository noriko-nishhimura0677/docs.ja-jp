---
title: 列挙型デザイン
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dea187b5f3911114e551d640e0bb0aa6fac1143
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213291"
---
# <a name="enum-design"></a>列挙型デザイン
列挙は、特殊な値の型です。 列挙型の 2 種類があります。 単純な列挙型、およびフラグの列挙型。  
  
 単純な列挙型では、選択肢の小規模の閉じたセットを表します。 単純な列挙型の一般的な例は、色のセットです。  
  
 フラグ列挙型は、列挙値のビットごとの演算をサポートするために設計されています。 フラグ列挙型の一般的な例では、オプションの一覧を示します。  
  
 **✓ DO** を厳密に型パラメーター、プロパティ、列挙型を使用し、戻り値のセットを表す値です。  
  
 **✓ DO** 列挙型を静的な定数の代わりに使用をお勧めします。  
  
 **X DO NOT** (など、オペレーティング システムのバージョン、友人などの名前)、開いているセットの列挙型を使用します。  
  
 **X DO NOT** 将来使用するためのものでは予約されている列挙値を提供します。  
  
 後の段階で既存の列挙体を単純に常に値を追加できます。 参照してください[列挙型に値を追加する](#add_value)列挙型に値を追加する方法の詳細についてはします。 予約済みの値は煩雑に実際の値のセットをユーザー エラーが発生する傾向がありますだけです。  
  
 **X AVOID** 1 つだけの値を持つ列挙型を公開することです。  
  
 C Api の将来の拡張性を確保するための一般的な方法では、メソッド シグネチャに予約済みのパラメーターを追加します。 このような予約済みのパラメーターは、1 つの既定値を持つ列挙型として表現できます。 これは、マネージ Api で実行する必要がありますされません。 メソッドのオーバー ロードでは、パラメーターは今後のリリースを追加できます。  
  
 **X DO NOT** enum で sentinel 値が含まれます。  
  
 フレームワークの開発者に役立つことがあります、sentinel 値は、フレームワークのユーザーが混乱します。 列挙型で表されるセットから値のいずれかの中ではなく、列挙型の状態を追跡するために使用されます。  
  
 **✓ DO** 単純な列挙型のゼロの値を指定します。  
  
 値を"None"のように呼び出すことを検討してください。 このような値がこの特定の列挙型に対して適切でない場合、列挙型の最も一般的な既定値は、基になる値の 0 割り当てする必要があります。  
  
 **✓ CONSIDER** を使用して<xref:System.Int32>(ほとんどのプログラミング言語の既定値) enum の基になる型として、次のいずれかが当てはまる場合を除き、します。  
  
-   列挙型はフラグ列挙体を 32 を超えるのフラグが設定されてしたりするは詳細は、将来の予想されます。  
  
-   基になる型が異なる必要があります<xref:System.Int32>のサイズの異なる列挙型を指定してください。 アンマネージ コードと相互運用を簡単にします。  
  
-   小さな基になる型は、スペースで大幅に削減になります。 列挙型の制御フローの引数として主に使用する場合は、ほとんど違いは、サイズ。 サイズ削減量がかなり大きくなる場合。  
  
    -   非常に頻繁にインスタンス化された構造体またはクラス内のフィールドとして使用される列挙型を期待します。  
  
    -   大きな配列または列挙型のインスタンスのコレクションを作成するユーザーを必要とします。  
  
    -   シリアル化する列挙型のインスタンスの数が多いはずです。  
  
 インメモリ使用量にマネージ オブジェクトが常には注意してください`DWORD`-配置するため、複数の列挙型、または合計インスタンス サイズは常にあるために、差別化する、するためを持つ小規模な列挙型をパックするインスタンスでの他の小規模な構造を効果的に必要四捨五入されますへ、`DWORD`します。  
  
 **✓ DO** フラグの列挙型には複数形の名詞または名詞句と単数形の名詞または名詞句と単純な列挙型の名前を付けます。  
  
 **X DO NOT** 拡張<xref:System.Enum?displayProperty=nameWithType>直接です。  
  
 <xref:System.Enum?displayProperty=nameWithType> 特殊な種類、CLR によって列挙型のユーザー定義の作成に使用します。 ほとんどのプログラミング言語では、この機能にアクセスを提供するプログラミング要素を指定します。 C# などの`enum`列挙体を定義するキーワードを使用します。  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>フラグ列挙型の設計  
 **✓ DO** 適用、<xref:System.FlagsAttribute?displayProperty=nameWithType>フラグ列挙体にします。 単純な列挙型にはこの属性は適用されません。  
  
 **✓ DO** フラグ列挙値に 2 の累乗を使用して、自由に組み合わせてことができます、ビットごとの OR 演算を使用しているためです。  
  
 **✓ CONSIDER** フラグの組み合わせを使用してよくの特別な enum 値を提供します。  
  
 ビットごとの演算は、高度な概念し、は単純な作業は必要ありません。 <xref:System.IO.FileAccess.ReadWrite> このような特殊な値の例に示します。  
  
 **X AVOID** 特定の値の組み合わせは有効なフラグ列挙型を作成します。  
  
 **X AVOID** 値が「すべてのフラグをクリアする」を表し、次のガイドラインで規定された方法、適切に名前がない限り、列挙型値ゼロのフラグを使用しています。  
  
 **✓ DO** フラグ列挙型のゼロ値の名前を付けます`None`です。 フラグ列挙型では、値必要がありますとは限りません"すべてのフラグがクリアされます"  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>列挙型に値を追加  
 既に配布した後に、列挙型に値を追加する必要があることを検出する非常に一般的です。 潜在的なアプリケーション互換性問題を新しく追加された値が、既存の API から返されるためには適切に記述されたアプリケーションの新しい値を正しく処理されない可能性があります。  
  
 **✓ CONSIDER** 小さい互換性上のリスクに関係なく、列挙型に値を追加します。  
  
 列挙型への追加によるアプリケーション互換性に関する実際のデータがあれば、新旧の値を返す新しい API の追加を検討して、古い値だけを返すことは引き続き以前の API の廃止します。 これにより、既存のアプリケーションの互換性を保つことが保証されます。  
  
 *Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*  
  
 *2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*  
  
## <a name="see-also"></a>関連項目

- [型デザインのガイドライン](../../../docs/standard/design-guidelines/type.md)  
- [フレームワーク デザインのガイドライン](../../../docs/standard/design-guidelines/index.md)
