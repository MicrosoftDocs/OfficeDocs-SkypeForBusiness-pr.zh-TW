---
title: 設定動態緊急通話
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 設定動態緊急通話
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37639271"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>規劃及設定通話方案的動態緊急通話
Microsoft 通話方案的動態緊急通話可提供根據團隊用戶端目前位置來設定和路由緊急通話的功能。  自動路由至適當的公用安全回應點（PSAP）或通知安全服務台人員的功能，會視小組使用者使用的國家/地區而有所不同。  

> [!Note] 
> 動態緊急通話目前僅適用于美國。 不過，在整個國家/地區的範圍內支援安全服務台通知。

在**美國**境內，您可以設定動態緊急呼叫路由，如下所示：
  
- 如果團隊用戶端位於租使用者定義的動態緊急位置，來自該用戶端的緊急呼叫會自動路由至該地理位置的 PSAP 服務。  

- 如果團隊用戶端不在租使用者的動態緊急位置，來自該用戶端的緊急呼叫是由國內話務中心加以遮罩，在將來電轉接到該地理位置的 PSAP 之前，決定呼叫者的位置。

您可以設定安全服務台通知，如下所示：

- 如果團隊用戶端位於租使用者定義的網路網站上，系統會通知針對該網站設定的安全性群組成員。

- 如果團隊用戶端不位於租使用者的網路網站上，系統會通知使用者設定的安全性群組成員。

**在美國以外**，緊急通話會傳送到已對應給使用者的電話號碼的 PSAP。  某些國家/地區（例如英國及加拿大），在將呼叫者轉移至適當的 PSAP 之前，會 nationally [呼叫] 的畫面，而其他人則直接路由至 PSAP，而不論使用者目前位於何處。 

請注意，您可以為所有通話方案使用者設定動態的 security 辦公桌通知。


## <a name="supported-clients"></a>支援的用戶端

目前支援下列用戶端。  經常回到查看此清單的更新。

- Windows 版團隊桌面用戶端
- Mac 版團隊桌面用戶端

## <a name="configure-dynamic-emergency-calling"></a>設定動態緊急通話

若要設定動態緊急通話，您需要執行下列工作：

- [設定緊急位址](#configure-emergency-addresses)
- [設定網路設定](#configure-network-settings)
- [設定位置資訊服務](#configure-location-information-service)
- [設定緊急原則](#configure-emergency-policies)
- [啟用使用者和網站](#enable-users-and-sites)
- [測試緊急通話](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>設定緊急位址

若要支援在美國自動路由，您必須完整設定指派給網路識別碼之緊急位置一部分的市政位址，並包含相關聯的地功能變數代碼。 （沒有地理程式碼的緊急位址不能指派給動態位置所需的網路識別碼）。

- 如果您透過 Microsoft 團隊系統管理中心輸入緊急位址，則如果找到相符專案，就會自動包含 geo 代碼。

- 如果沒有自動找到相符的專案，您就有機會手動建立緊急位址。  

這表示如果將現有的緊急位址設定為緊急通話，則必須重新建立相同的位址，才能包含 geo 碼。  若要區分兩個位址，您應該包含不同的描述。 新的緊急位址可以指派給擁有舊位址的使用者。 完全遷移後，就可以刪除舊的位址。 

如需有關設定緊急位址的詳細資訊，請參閱[什麼是緊急位置、地點及呼叫路由？](what-are-emergency-locations-addresses-and-call-routing.md)。

### <a name="configure-network-settings"></a>設定網路設定

您必須設定網路設定，以動態取得路由緊急通話的緊急位置，也可以選擇提供安全服務台通知的動態設定。 所需的緊急通話體驗將指示需要設定的網路設定。 

請牢記下列定義：

- 受信任的 IP 包含商業網路的網際網路外部 Ip 集合，並用來判斷使用者的端點是否在商業網路內。 只有在使用者的外部 IP 與信任的 IP 集合中的 IP 相符時，才會啟用動態位置。  您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。

- 網路區域包含一個網路網站集合。 

- 網路網站代表貴組織有實體價值（例如，辦公室、一組建築物或校園）的位置。 這些網站是由 IP 子網的集合所定義。

- 網路子網必須與特定的網路網站相關聯。 用戶端的位置是根據網路子網和相關的網路網站來決定。  


通話方案使用者：

- 如果需要對 security 辦公桌通知進行動態設定，則您必須設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則您必須只設定信任的 IP 位址。 

- 如果兩者都不是必要的，則不需要設定網路設定。 

如需詳細資訊，請參閱[設定以位置為基礎的路由的網路設定](location-based-routing-configure-network-settings.md)，說明如何設定網路設定。 （本文中的資訊同時適用于通話方案和直接路由）。


### <a name="configure-location-information-service"></a>設定位置資訊服務

團隊用戶端會從與不同網路識別碼相關聯的緊急位置取得緊急位址。  同時支援子網和無線存取點。 （乙太網上交換器/埠的支援已擱置。）

若要將位置資訊服務（.LIS）與網路識別碼及緊急位置進行設定，請使用下列 Cmdlet：

- 取得、設定、移除-CsOnlineLisPort
- 取得、設定、移除-CsOnlineLisSwitch
- 取得、設定、移除-CsOnlineLisSubnet
- 取得、設定、移除-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> 如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義，才能呈現動態位置。


### <a name="configure-emergency-policies"></a>設定緊急原則

緊急原則決定貴組織中的使用者進行緊急通話時，會發生什麼情況。  您可以設定要通知的人員，以及使用者呼叫緊急服務時通知的方式。 例如，您可以將原則設定設定為自動通知貴組織的安全服務台，並讓他們在緊急通話中聆聽。

您可以使用新的 CsTeamsEmergencyCalling 原則 Cmdlet 來管理緊急原則。  如需詳細資訊，請參閱[管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)。


### <a name="enable-users-and-sites"></a>啟用使用者和網站

當通話方案使用者自動啟用緊急通話時，您必須先設定緊急呼叫原則，以讓使用者取得安全服務台通知，如下列範例所示：


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

您也可以將緊急呼叫原則指派給網路網站，如下列範例所示，該範例會將名為「Contoso 急診通話原則1」的原則指派給 Site 1：

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

如果您已將緊急通話原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。


### <a name="test-emergency-calling"></a>測試緊急通話

若要在美國測試緊急通話，請使用預先定義的測試緊急號碼933。  這個號碼會路由到 bot，然後回顯來電者電話號碼（呼叫線路識別碼）、緊急位址或位置，以及是否要先將通話自動路由到 PSAP 或篩選。  