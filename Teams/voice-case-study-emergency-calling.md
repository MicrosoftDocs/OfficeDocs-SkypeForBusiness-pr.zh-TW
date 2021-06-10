---
title: Teams Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams多國公司的語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785977"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 案例研究：緊急電話

若要瞭解緊急電話與緊急通話相關術語的可用性，Contoso 已審查管理緊急電話和規劃及設定動態緊急電話 &mdash; &mdash; 。 [](what-are-emergency-locations-addresses-and-call-routing.md) [](configure-dynamic-emergency-calling.md)

在 Office 365，系統會自動啟用通話方案使用者進行緊急通話。 但只有美國的通話方案使用者可以使用動態位置路由緊急電話。 

對於直接路由，Contoso 瞭解路由緊急電話時，可能需要其他組組，並可能還需要合作夥伴連接。 系統管理員必須為緊急位置識別號碼 (ELIN) 應用程式設定與緊急路由服務提供者 (ERSP)  () 或設定會話邊界控制器 (SBC) 的連接。

Contoso 在美國及美國以外地區設有辦公室：

- 在美國，Contoso 通話方案使用者可以使用動態位置路由緊急電話。 

- 在美國以外，Contoso 有一些使用通話方案的網站，以及透過直接路由電話系統連結至其他網站。

## <a name="emergency-calling-use-cases"></a>緊急通話使用案例

決定 Contoso 如何連接到電話後，Contoso 識別出下列緊急電話使用案例： 

- [美國的通話方案使用者](#calling-plan-user-in-the-united-states) 

- [美國以外的通話方案使用者](#calling-plan-user-outside-of-the-united-states)

- [透過直接路由電話系統使用者](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>美國的通話方案使用者  

當電話號碼需要與緊急位置相關聯時，有一些需求。 為了瞭解這些要求，Contoso 已審查 [通話方案考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 

根據這些需求，Contoso 決定在將號碼指派給美國使用者時，將位置與電話號碼關聯。

### <a name="calling-plan-user-outside-of-the-united-states"></a>美國以外的通話方案使用者 

為了瞭解電話號碼何時需要與緊急位置相關聯，Contoso 已審查通話  [方案考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 根據需求，Contoso 決定下列專案：  

-  當號碼指派給加拿大的使用者時，Contoso 會將位置與電話號碼關聯。 

- 當電話號碼從 Office 365或從另一個服務提供者或電信公司移轉時，Contoso 會指派緊急位置。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>透過直接路由電話系統使用者 

為了針對此使用案例規劃緊急路由，Contoso 已審查 [直接路由的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。 由於直接路由使用者不會以與通話方案使用者相同的方式接收緊急電話，因此 Contoso 必須決定如何提供緊急電話。 直接路由可以連接到緊急路由服務提供者 (ERSP) 。 直接路由也可以有包含緊急位置識別號碼的 SBC (ELIN) 。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>緊急路由服務提供者 (ERSP) 考慮

緊急路由服務提供者 (ERSP) 根據來電者的位置自動路由緊急電話。  

- 如果緊急路由服務提供者已整合至直接路由部署，具有動態取得位置的緊急電話會自動路由至服務該位置的公用安全應答點 (PSAP) 點。 

- 沒有動態取得位置的緊急電話會先經過篩選，以決定使用者的目前位置，然後再根據更新的位置將通話連接到適當的調度中心。 


#### <a name="elin-considerations"></a>ELIN 考慮事項

如果 SBC ELIN 應用程式已整合至直接路由部署，則需要執行其他組組步驟，將緊急位址與電話號碼建立關聯。  

Contoso 決定使用會話邊界控制器，其中包括 ELIN (緊急) 號碼。  

## <a name="security-desk-notification"></a>安全電話台通知

Microsoft 通話方案及直接路由功能都提供在緊急通話時通知電話系統功能。 Contoso 已查看安全性中心通知中的詳細資料，以判斷這是否應在其辦公室進行配置  

Contoso 決定使用安全電話台通知。

## <a name="configuration"></a>配置 

Contoso 遵循設定動態緊急 [電話的步驟](configure-dynamic-emergency-calling.md) 進行： 

- 指派緊急位址 

- 設定網路設定 

- 設定位置資訊服務 

- 設定緊急政策 

- 啟用使用者和網站 

- 測試緊急通話 

在動態緊急電話配置完成之後，Contoso 需要將位置指派給適當的使用者。  

- 若要新增、變更或移除貴組織的緊急位置，Contoso 會遵循新增、變更或移除貴組織的緊急位置 [中的步驟](add-change-remove-emergency-location-organization.md)

- 若要建立建築物、樓層和辦公室的位置，Contoso 遵循新增、變更或移除緊急位置位置 [中的步驟](add-change-remove-emergency-place-organization.md) 。 

- 若要指派緊急位置，Contoso 遵循指派或變更使用者的緊急 [位置中的步驟](assign-change-emergency-location-user.md)。 

 