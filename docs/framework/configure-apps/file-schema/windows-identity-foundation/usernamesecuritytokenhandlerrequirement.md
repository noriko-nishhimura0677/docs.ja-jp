---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: dfcaad8b150321fda2a86e601bf57204cbdc1a0e
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123385"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a>&lt;userNameSecurityTokenHandlerRequirement&gt;
構成を提供、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>クラスまたは派生クラス。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<userNameSecurityTokenHandlerRequirement >  
  
## <a name="syntax"></a>構文  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|membershipProviderName|指定します、<xref:System.Web.Security.MembershipProvider>でセキュリティ トークン ハンドラーを使用する必要があります。|  
  
### <a name="child-elements"></a>子要素  
 なし  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|トークン ハンドラー コレクションには、指定したセキュリティ トークン ハンドラーを追加します。|  
  
## <a name="remarks"></a>Remarks  
 `<userNameSecurityTokenHandlerRequirement>`要素セット、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>プロパティと、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>構成からオブジェクトを初期化します。  
  
## <a name="example"></a>例  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
