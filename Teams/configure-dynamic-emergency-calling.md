---
title: 設定動態緊急電話
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
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft 通話方案和電話系統直接路由動態緊急通話功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92862eb960722ac2becbe216cdec5281282106b5
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905885"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>規劃和設定動態緊急電話 

Microsoft 通話方案和電話系統直連路由的動態緊急通話可提供設定及路由緊急通話的功能，並根據團隊用戶端的目前位置來通知安全人員。  

根據租使用者管理員定義的網路拓撲，小組用戶端會在位置資訊服務（.LIS）的要求中提供網路連線資訊。  如果有相符的專案，則 .LIS 會傳回用戶端的位置。 這個位置資料會傳回用戶端。  

團隊用戶端包含位置資料做為緊急通話的一部分。 這個資料然後由緊急服務提供者用來判斷適當的公用安全回應點（PSAP），並將呼叫路由到該 PSAP，這可讓 PSAP dispatcher 取得來電者的位置。  

針對動態緊急通話，必須發生下列情況：

1. 網路系統管理員會設定網路設定和 .LIS，以建立網路/緊急位置地圖。

   針對直接路由，需要進行額外的設定，以路由緊急呼叫並可能提供合作夥伴連線。 系統管理員必須設定與緊急路由服務（ERS）提供者（美國）的連線，**或**針對緊急位置識別號碼（ELIN）應用程式設定會話邊界控制器（SBC）。

2. 在啟動期間及之後定期進行，或當網路連線變更時，小組用戶端會將包含其網路連線資訊的位置要求傳送到網路設定和 IIS 類型。

   - 如果有網路設定網站相符的專案，緊急通話原則會傳回該網站的小組用戶端。 （如需有關原則的詳細資訊，請參閱[設定緊急原則](#configure-emergency-policies)）。

   - 如果有一個 IIS 相符的專案，則會將團隊用戶端連接的網路元素的緊急位置傳回給團隊用戶端。

3. 當團隊用戶端進行緊急通話時，緊急位置會傳達給 PSTN 網路。

   如果是直接路由，系統管理員必須設定 SBC 來傳送緊急呼叫給 ERS 提供者，或設定 SBC ELIN 應用程式。

本文包含下列各節。

- [設定緊急位址](#assign-emergency-addresses)
- [設定網路設定](#configure-network-settings)
- [設定位置資訊服務](#configure-location-information-service)
- [設定緊急原則](#configure-emergency-policies)
- [啟用使用者和網站](#enable-users-and-sites)
- [測試緊急通話](#test-emergency-calling)


自動路由至適當的公用安全應答點（PSAP）的功能會視小組使用者使用的國家/地區而有所不同。 

如需緊急通話的詳細資訊，包括緊急位址及緊急通話路由的相關資訊、國家/地區的相關資訊，以及網路設定和網路拓撲的相關資訊，請參閱下列內容：

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)


## <a name="supported-clients"></a>支援的用戶端

目前支援下列用戶端。  經常回到查看此清單的更新。

- Microsoft Windows 版團隊桌面用戶端
- Apple macOS 的小組桌面用戶端
- Apple iOS 用戶端版本1.0.92.2019121004 和 App Store 1.0.92 及更高版本的團隊行動用戶端
- 適用于 Android 用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更高版本的團隊行動用戶端
- 團隊手機版本 1449/1.0.94.2019110802 及更高版本

## <a name="assign-emergency-addresses"></a>指派緊急位址

您可以將緊急位址指派給呼叫方案使用者，以及動態取得位置所需的網路識別碼。 （支援 Subnet 和 WiFi AP; 乙太網上交換器/埠的支援擱置）。

若要支援在美國的緊急通話自動路由，您必須確認指派給網路識別碼的緊急位置包含關聯的地功能變數代碼。 （沒有地理程式碼的緊急位址無法指派給動態位置所需的網路識別碼）。

Azure 對應是用來進行位置服務的。  當您使用 Microsoft 團隊系統管理中心輸入緊急位址時，小組會檢查 Azure 對應位址：

- 如果找到相符的位置，系統會自動包含地區代碼。

- 如果找不到相符的專案，您就有機會手動建立緊急位址。 您可以使用釘選功能來執行此動作。   

這表示，如果為指派給呼叫計畫使用者的現有緊急位置是針對動態位置所設計，則必須重新建立相同的位址，才能包含 geo 碼。 若要區分兩個位置，您應該包含不同的描述。 新的緊急位置可以指派給擁有舊位置的使用者。 完全遷移後，就可以刪除舊位置。

如需有關設定緊急位址的詳細資訊，請參閱為[您的組織新增緊急位置](add-change-remove-emergency-location-organization.md)並[指派緊急位置給您的使用者](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>設定網路設定

[網路設定] 可用來判斷團隊用戶端的位置，以及動態取得緊急通話原則與緊急位置。 您可以根據貴組織希望緊急通話運作的方式來設定網路設定。

[網路設定] 包含包含子網集合的網站：這些都是專門針對動態原則指派給使用者。  例如，您可以將 TeamsEmergencyCalling 原則和 TeamsEmergencyCallRouting 原則指派給「雷德蒙網站」，讓從家裡或其他 Microsoft 位置進行漫遊的任何使用者都是以緊急號碼、路由和安全服務台（特定于雷蒙德）來設定。  

>[!Note]
>子網也可以在 .LIS 中定義，而且可以與緊急位置相關聯。  

請牢記下列定義：

- 受信任的 IP 包含商業網路的網際網路外部 Ip 集合，並用來判斷使用者的端點是否在商業網路內。 只要使用者的外部 IP 與信任的 IP 位址中的 IP 相符，就會嘗試取得動態原則或位置。 您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。  （如果公用 IP 位址同時具有 IPv4 與 IPv6，您必須將兩者都新增為信任的 IP 位址。）

- 網路區域包含一個網路網站集合。 

- 網路網站代表貴組織有實體價值（例如，辦公室、一組建築物或校園）的位置。 這些網站是由 IP 子網的集合所定義。

- 網路子網必須與特定的網路網站相關聯。 用戶端的位置是根據網路子網和相關的網路網站來決定。  

如需詳細資訊，請參閱[雲端語音功能的網路設定](cloud-voice-network-settings.md)和[管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。

請注意，網路設定（例如新位址、網路識別碼等）的某些變更可能需要幾個時間（例如新的位址、網路識別碼等），才能傳播並供團隊用戶端使用。  

**通話方案使用者：**

- 如果需要對 security 辦公桌通知進行動態設定，則您必須設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則您必須只設定信任的 IP 位址。 

- 如果兩者都不是必要的，則不需要設定網路設定。 

**針對直接路由使用者：**

- 如果您需要動態啟用緊急通話或安全服務台通知的動態設定，則您必須設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則您必須只設定信任的 IP 位址。

- 如果兩者都不是必要的，則不需要設定網路設定。


## <a name="configure-location-information-service"></a>設定位置資訊服務

團隊用戶端從與不同網路識別碼相關聯的位置取得緊急位址。 同時支援子網和無線存取點（WAPs）。 （乙太網上交換器/埠的支援已擱置。）

若要讓用戶端取得位置，您必須使用下列 Cmdlet 來填入位置資訊服務（.LIS）與網路識別碼及緊急位置：  


- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps)-CsOnlineLisPort
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-CsOnlineLisSwitch
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps)-CsOnlineLisSubnet
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、[移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
)-CsOnlineLisWirelessAccessPoint 


>[!Important] 
>如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義，才能呈現動態位置。


## <a name="configure-emergency-policies"></a>設定緊急原則

您可以使用下列原則來設定緊急通話：

- **TeamsEmergencyCallRoutingPolicy** –只適用于直接路由。 此原則會根據需要設定緊急電話號碼、每個數位的遮罩，以及每個號碼的 PSTN 路由。  您可以將此原則指派給使用者、網路網站，或同時指派給這兩者。 （通話計畫團隊用戶端會根據其 Office 365 使用位置，自動啟用緊急通話的緊急電話號碼。） 您可以使用 New、Set 和 Grant CsTeamsEmergencyCallRouting Cmdlet 來管理此原則。 

- **TeamsEmergencyCallingPolicy** -適用于通話方案和直接路由。 此原則會在發出緊急通話時設定 security 辦公桌的通知體驗。 您可以設定要通知的人員，以及通知的方式。 例如，自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。  您可以將此原則指派給使用者或網路網站，或同時指派給這兩者。 您可以使用 New、Set 和 Grant CsTeamsEmergencyCallingPolicy Cmdlet 來管理此原則。 

如需詳細資訊，請參閱[管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)和[管理直接路由的緊急通話路由原則](manage-emergency-call-routing-policies.md)。


## <a name="enable-users-and-sites"></a>啟用使用者和網站

您可以將**TeamsEmergencyCalling**和**TeamsEmergencyCallROuting**原則指派給使用者和網站。  

TeamsEmergencyCallRouting 原則只適用于直接路由。 （雖然您可以將此原則指派給通話方案使用者，但原則將沒有任何效果。）

例如，若要針對安全服務台通知啟用特定的使用者，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要將名為「Contoso 緊急通話原則1」的原則指派給 Site 1，請使用下列命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要啟用緊急通話的特定直接路由使用者，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要將名為「Contoso 紐約急救通話路由」的原則指派給 Site 1，請使用下列命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果您已將緊急通話原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。


## <a name="test-emergency-calling"></a>測試緊急通話

美國的一些緊急路由服務提供者（ERSPs）提供緊急呼叫測試 bot。

- **在美國撥打電話方案使用者**可以使用預先定義的測試緊急號碼933來驗證緊急通話設定。 這個號碼會路由到 bot，然後回顯來電者電話號碼（呼叫線路識別碼）、緊急位址或位置，以及是否要先將呼叫自動路由到 PSAP 或篩選。

- **在美國直接傳送路由的客戶**應該與其 ERSP，以進行測試服務。

 ## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)
