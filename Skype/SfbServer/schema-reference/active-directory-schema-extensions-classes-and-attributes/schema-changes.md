---
title: 商務用 Skype Server 中的架構變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在您部署並執行商務用 Skype Server 之前, 您必須透過延伸架構來準備 Active Directory 網域服務。 架構延伸會新增商務用 Skype Server 所需的類別和屬性。
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192913"
---
# <a name="schema-changes-in-skype-for-business-server"></a>商務用 Skype Server 中的架構變更
 
在您部署並執行商務用 Skype Server 之前, 您必須透過延伸架構來準備 Active Directory 網域服務。 架構延伸會新增商務用 Skype Server 所需的類別和屬性。

> [!NOTE]
> 如果您要從 Lync Server 2013 升級到商務用 Skype Server 2015, 則不會進行任何架構變更, 因此本文不適用。
  
商務用 Skype 伺服器需要幾個新的類別和屬性, 並修改一些現有的類別和屬性。 此外, 商務用 Skype 伺服器的許多配置資訊會儲存在中央管理儲存區, 而不是在 AD DS 中, 就像在舊版中一樣。 下列資訊仍會儲存在商務用 Skype Server 的 AD DS 中:
  
- **架構擴充**:
    
  - 使用者物件延伸
    
  - 類別延伸與支援的舊版 Lync Server 保持向後相容性。
    
- **資料**(儲存在商務用 Skype Server 擴展架構和現有的架構類別中):
    
  - 使用者 SIP 統一資源識別項 (URI) 及其他使用者設定
    
  - 回應群組和會議助理等應用程式的連絡人物件
    
  - 指向中央管理存放區的指標
    
  - Kerberos 驗證帳戶 (選擇性電腦物件)
    
本主題描述商務用 Skype Server 所需的 Active Directory 架構變更。 它不會說明舊版 Office 通訊伺服器所引入的架構變更。 如需類別及其描述的清單, 請參閱[商務用 Skype Server 中的架構類別和描述](schema-classes-and-descriptions.md)。 如需屬性及其描述的清單, 請參閱[商務用 Skype Server 中的架構屬性及描述](schema-attributes-and-descriptions.md)。 如需具有它們可能包含之屬性的類別清單, 請參閱[商務用 Skype Server 中的班級架構屬性 (依類別](schema-attributes-by-class.md))。
  
MsRTCSIP 首碼會識別商務用 Skype Server 專用的類別和屬性。
  
## <a name="new-active-directory-attributes"></a>新的 Active Directory 屬性

下表說明商務用 Skype Server 新增的 Active Directory 屬性。
  
**商務用 Skype Server 新增的屬性**

|**Attribute**|**說明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |這個多重值屬性包含適用于使用者的保留原則的識別碼。 保留原則在保留期間保留使用者的信箱專案。 這個屬性是與 Exchange 2013 共用的。  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |這是 SIP 路由群組識別碼。 相同群組中的使用者會註冊到相同的前端伺服器。  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |這個屬性是用來儲存前端池所使用的鏡像 SQL Server 後端。  <br/> |
   
## <a name="modified-active-directory-classes"></a>已修改的 Active Directory 類別

下表說明商務用 Skype Server 所修改的 Active Directory 類別。
  
**商務用 Skype Server 修改的類別**

|**靜態類**|**切換**|**類別或屬性**|
|:-----|:-----|:-----|
|使用者名  <br/> |新增: mayContain  <br/> 新增: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|資訊  <br/> |新增: mayContain  <br/> 新增: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|郵件-收件者  <br/> |新增: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |新增: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

