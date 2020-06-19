---
title: 團隊語音 Contoso 案例研究
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
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785977"
---
# <a name="contoso-case-study-emergency-calling"></a>Contoso 案例研究：緊急通話

若要瞭解緊急通話的可用性，以及緊急通話 &mdash; 緊急位址、地點、緊急位置及登入位址的相關術語，請 &mdash; 查看[管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)並[規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。

在 Office 365 中，通話方案使用者會自動啟用緊急通話。 但只有美國地區的通話方案使用者可以使用動態位置來路由緊急通話。 

針對直接路由，Contoso 發現路由緊急通話需要額外設定，而且可能是合作夥伴連線性。 系統管理員必須設定與緊急路由服務提供者（ERSP）（美國）的連線，或針對緊急位置識別號碼（ELIN）應用程式設定會話邊界控制器（SBC）。

Contoso 在美國擁有辦事處，且在美國以外地區：

- 在美國，Contoso 通話方案使用者可以使用動態位置來路由緊急通話。 

- 在美國以外，Contoso 擁有一些使用通話方案的網站，以及透過直接路由連接至手機系統的部分網站。

## <a name="emergency-calling-use-cases"></a>緊急通話使用案例

決定 Contoso 將如何連接至電話系統之後，Contoso 已識別下列緊急通話使用案例： 

- [在美國撥打電話方案使用者](#calling-plan-user-in-the-united-states) 

- [美國以外的通話計畫使用者](#calling-plan-user-outside-of-the-united-states)

- [透過直接路由連接至手機系統的使用者](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a>在美國撥打電話方案使用者  

需要將電話號碼與緊急位置相關聯的需求。 若要瞭解這些需求，Contoso 已檢查[通話方案的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 

根據這些需求，當您將號碼指派給美國的使用者時，Contoso 決定要將位置與電話號碼產生關聯。

### <a name="calling-plan-user-outside-of-the-united-states"></a>美國以外的通話計畫使用者 

若要瞭解電話號碼需要與緊急位置相關聯的時間，Contoso 已檢查[通話方案的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。 根據需求，Contoso 決定下列事項：  

-  當您將數位指派給加拿大中的使用者時，Contoso 會將該位置與電話號碼產生關聯。 

- 當您從 Office 365 取得電話號碼，或從其他服務提供者或承運人傳送號碼時，Contoso 會指派緊急地點。 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a>透過直接路由連接至手機系統的使用者 

若要針對此使用案例規劃緊急路由，Contoso 已審查[直接路由的考慮](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。 因為直接路由使用者沒有像呼叫方案使用者一樣接收緊急通話，所以 Contoso 必須決定如何提供緊急通話。 直接路由可以連線到緊急路由服務提供者（ERSP）。 直接路由也可以有包含緊急位置識別號碼（ELIN）的 SBC。   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a>緊急路由服務提供者（ERSP）考慮

緊急路由服務提供者（ERSPs）可以根據來電者的位置，自動路由緊急通話。  

- 如果緊急路由服務提供者已整合至直接路由部署，則使用動態取得位置的緊急呼叫會自動路由到該位置的公用安全應答點（PSAP）。 

- 在沒有動態取得位置的緊急通話是先進行篩選，以便在根據更新的位置將呼叫連線至適當的派遣中心之前，決定使用者的目前位置。 


#### <a name="elin-considerations"></a>ELIN 考慮

如果 SBC ELIN 應用程式已整合至直接路由部署，則需要執行額外的設定步驟，才能將緊急位址與電話號碼產生關聯。  

Contoso 決定使用包含緊急位置身分識別號碼（ELIN）應用程式的會話框線控制器。  

## <a name="security-desk-notification"></a>Security 辦公桌通知

在 Microsoft 通話方案和電話系統直接路由中，都提供緊急通話時通知安全服務台的功能。 Contoso 已審查安全服務台通知中的詳細資料，以判斷是否應該在其辦公室進行設定  

Contoso 決定要使用安全服務台通知。

## <a name="configuration"></a>Configuration 

Contoso 按照[設定動態緊急呼叫](configure-dynamic-emergency-calling.md)的步驟進行： 

- 指派緊急位址 

- 設定網路設定 

- 設定位置資訊服務 

- 設定緊急原則 

- 啟用使用者和網站 

- 測試緊急通話 

設定動態緊急通話之後，Contoso 需要將位置指派給適當的使用者。  

- 若要新增、變更或移除組織的緊急位置，Contoso 按照[新增、變更或移除組織的緊急位置](add-change-remove-emergency-location-organization.md)中的步驟進行。

- 若要為建築物、地面和辦事處建立位置，Contoso 請按照[新增、變更或移除緊急位置](add-change-remove-emergency-place-organization.md)中的步驟進行。 

- 若要指派緊急地點，Contoso 按照[指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)中的步驟進行。 

 