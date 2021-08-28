---
title: 商務用 Skype Server 中的架構變更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在您部署和操作商務用 Skype Server 之前，您必須透過擴充架構來準備 Active Directory 網域服務。 架構擴充新增商務用 Skype Server 所需的類別和屬性。
ms.openlocfilehash: 16f71b80864fae8fc97b87eda22ad2a9594c3987
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626535"
---
# <a name="schema-changes-in-skype-for-business-server"></a>商務用 Skype Server 中的架構變更
 
在您部署和操作商務用 Skype Server 之前，您必須透過擴充架構來準備 Active Directory 網域服務。 架構擴充新增商務用 Skype Server 所需的類別和屬性。

> [!NOTE]
> 如果您是從 Lync Server 2013 升級為商務用 Skype Server 2015，則不會進行任何架構變更，因此本文也不適用。
  
商務用 Skype Server 需要數個新的類別和屬性，並修改一些現有的類別和屬性。 此外，商務用 Skype Server 的大部分設定資訊都會儲存在中央管理存放區，而不是在先前的版本中儲存在 AD DS 中。 下列資訊仍儲存在 AD DS 中商務用 Skype Server：
  
- **架構擴充**：
    
  - 使用者物件擴充
    
  - 用於維護與支援之舊版 Lync Server 的回溯相容性的類別擴充。
    
- 儲存在商務用 Skype Server 擴充架構和現有架構類別) 中的 **資料** (：
    
  - 使用者 SIP 統一資源識別項 (URI) 和其他使用者設定
    
  - 回應群組和會議語音應答等應用程式的連絡人物件
    
  - 中央管理存放區的指標
    
  - Kerberos 驗證帳戶 (選用的電腦物件) 
    
本主題說明商務用 Skype Server 所需的 Active Directory 架構變更。 它不會描述先前版本的 Office 通訊伺服器所引進的架構變更。 如需類別及其描述的清單，請參閱[商務用 Skype Server 中的架構類別和描述](schema-classes-and-descriptions.md)。 如需屬性及其描述的清單，請參閱[商務用 Skype Server 中的架構屬性和描述](schema-attributes-and-descriptions.md)。 如需可包含其屬性的類別清單，請參閱[Schema attributes in 商務用 Skype Server 中的類別](schema-attributes-by-class.md)。
  
msRTCSIP 首碼可識別商務用 Skype Server 特有的類別和屬性。
  
## <a name="new-active-directory-attributes"></a>新的 Active Directory 屬性

下表說明商務用 Skype Server 所新增的 Active Directory 屬性。
  
**商務用 Skype Server 所新增的屬性**

|**屬性**|**描述**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |此多重值屬性包含適用于使用者之保留原則的識別碼。 保留原則會在保留期間保留使用者的信箱專案。 此屬性與 Exchange 2013 共用。  <br/> |
|msRTCSIP UserRoutingGroupId  <br/> |這是 SIP 路由群組識別碼。 相同群組中的使用者會註冊到同一個前端伺服器。  <br/> |
|msRTCSIP MirrorBackEndServer  <br/> |此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。  <br/> |
   
## <a name="modified-active-directory-classes"></a>修改的 Active Directory 類別

下表說明商務用 Skype Server 修改的 Active Directory 類別。
  
**商務用 Skype Server 修改的類別**

|**類別**|**變更**|**類別或屬性**|
|:-----|:-----|:-----|
|使用者  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|連絡人  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP MirrorBackEndServer  <br/> |
   

