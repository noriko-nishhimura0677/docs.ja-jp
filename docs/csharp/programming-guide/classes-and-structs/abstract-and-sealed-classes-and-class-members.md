---
title: 抽象クラスとシール クラス、およびクラス メンバー (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: 0e80357a51bde270d5ed012f16f7b2e821f084c8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517343"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a>抽象クラスとシール クラス、およびクラス メンバー (C# プログラミング ガイド)
[abstract](../../../csharp/language-reference/keywords/abstract.md) キーワードを使用すると、派生クラスで実装する必要のある不完全な[クラス](../../../csharp/language-reference/keywords/class.md) メンバーを作成できます。  
  
 また、[sealed](../../../csharp/language-reference/keywords/sealed.md) キーワードを使用すると、既に [virtual](../../../csharp/language-reference/keywords/virtual.md) とマークされているクラスや特定のクラス メンバーを継承しないようにできます。  
  
## <a name="abstract-classes-and-class-members"></a>抽象クラスと抽象クラス メンバー  
 クラス定義の前にキーワード `abstract` を指定することで、クラスを抽象として宣言できます。 例:  
  
 [!code-csharp[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 抽象クラスはインスタンス化できません。 抽象クラスの目的は、複数の派生クラスで共有できる基底クラスの共通の定義を提供することです。 たとえば、クラス ライブラリでは、その多くの関数のパラメーターとして使用される抽象クラスを定義できます。このライブラリを使用する場合は、派生クラスを作成してクラスの独自の実装を提供する必要があります。  
  
 抽象クラスでは、抽象メソッドも定義できます。 抽象メソッドを定義するには、メソッドの戻り値の型の前に `abstract` キーワードを記述します。 例:  
  
 [!code-csharp[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 抽象メソッドには実装がないので、メソッド定義の後に、通常のメソッド ブロックの代わりにセミコロン (;) を配置します。 抽象クラスの派生クラスでは、すべての抽象メソッドを実装する必要があります。 抽象クラスが基底クラスから仮想メソッドを継承した場合は、この抽象クラスでは抽象メソッドで仮想メソッドをオーバーライドできます。 例:  
  
 [!code-csharp[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 `virtual` メソッドが `abstract` として宣言されている場合、そのメソッドは、その抽象クラスを継承するどのクラスでも仮想になります。 抽象メソッドを継承するクラスでは、そのメソッドの元の実装にアクセスできません。上の例では、クラス F の `DoWork` は、クラス D の `DoWork` を呼び出すことができません。このようにして抽象クラスは、派生クラスに対し、仮想メソッドの新しいメソッド実装を強制的に提供させることができます。  
  
## <a name="sealed-classes-and-class-members"></a>シール クラスとシール クラス メンバー  
 クラス定義の前にキーワード `sealed` を指定することで、クラスを [sealed](../../../csharp/language-reference/keywords/sealed.md) として宣言できます。 例:  
  
 [!code-csharp[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 シール クラスは、基底クラスとして使用できません。 このため、シール クラスは抽象クラスになることもできません。 シール クラスにより、派生が防止されます。 シール クラスは基底クラスとして使用できないので、実行時の最適化で、シール クラス メンバーを多少高速に呼び出すことができる場合があります。  
  
 基底クラスの仮想メンバーをオーバーライドしている派生クラスのメソッド、インデクサー、プロパティ、またはイベントでは、そのメンバーをシールとして宣言できます。 これにより、その後の派生クラスでは、メンバーの仮想性が無効になります。 このように宣言するには、クラス メンバー宣言で [override](../../../csharp/language-reference/keywords/override.md) キーワードの前に `sealed` キーワードを配置します。 例:  
  
 [!code-csharp[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## <a name="see-also"></a>参照

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [クラスと構造体](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [継承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
- [メソッド](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [フィールド](../../../csharp/programming-guide/classes-and-structs/fields.md)  
- [方法: 抽象プロパティを定義する](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)
