---
title: '&lt;削除&gt;要素&lt;リスナー&gt;の&lt;トレース&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 54fd529c571c8e8cf43c5dabe2398ae4a6cf4f11
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030537"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;削除&gt;要素&lt;リスナー&gt;の&lt;トレース&gt;
リスナーを削除、**リスナー**コレクション。  
  
 \<configuration>  
\<system.diagnostics >  
\<トレース >  
\<リスナー >  
\<remove>  
  
## <a name="syntax"></a>構文  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|**name**|必須の属性です。<br /><br /> 削除するリスナーの名前、**リスナー**コレクション。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|`configuration`|共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。|  
|`listeners`|収集、するリスナーをストアを指定し、メッセージをルーティングします。 リスナーでは、適切なターゲットのトレースを出力します。|  
|`system.diagnostics`|メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。|  
|`trace`|ASP.NET トレース サービスを構成します。|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  削除、<xref:System.Diagnostics.DefaultTraceListener>から、`Listeners`コレクションの動作を変更する、 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、 <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>、および<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>メソッド。 呼び出す、`Assert`または`Fail`メソッド結果は、通常、メッセージ ボックスの表示の場合、メッセージ ボックスは表示されませんが、<xref:System.Diagnostics.DefaultTraceListener>内にない、`Listeners`コレクション。  
  
## <a name="example"></a>例  
 次の例は、トレースから既定のトレース リスナーを削除する方法を示しています。**リスナー**コレクション。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [トレースおよびデバッグ設定のスキーマ](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
