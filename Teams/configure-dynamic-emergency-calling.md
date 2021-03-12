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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft 通話方案與電話系統直接路由動態緊急電話功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca2fb94ff67f2efa874e670926330f8f3630cbe2
ms.sourcegitcommit: 74f12ed15e1aa1106fa47b95597bde451b0b37f4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741884"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>規劃和設定動態緊急電話 

Microsoft 通話方案與電話系統直接路由的動態緊急電話功能，可設定及路由緊急電話，並依據 Teams 用戶端的目前位置通知安全性人員。  

根據租使用者系統管理員定義的網路拓撲，Teams 用戶端在要求中提供網路連接資訊給位置資訊服務 (LIS) 。 如果有相符專案，LIS 會將位置返回用戶端。 此位置資料會傳回用戶端。  

Teams 用戶端在緊急通話中包含位置資料。 緊急服務提供者接著會使用這些資料來判斷適當的公用安全答對點 (PSAP) ，以及將電話路由到該 PSAP，讓 PSAP 調度員取得來電者的位置。  

針對動態緊急電話，必須發生下列情況：

1. 網路系統管理員會設定網路設定和 LIS，以建立網路/緊急位置地圖。

   針對直接路由，路由緊急電話時可能需要進行其他組組，並且可能還需要合作夥伴連接。 系統管理員必須設定與緊急路由服務 (ERS) 提供者 (美國) 的關聯，或針對緊急位置識別碼 (ELIN) 應用程式設定會話邊界控制器 (SBC) 。

2. 在啟動期間和之後定期，或網路連接變更時，Teams 用戶端會傳送包含其網路連接資訊的位置要求至網路設定和 LIS。

   - 如果有網路設定網站相符 ，緊急通話政策會從該網站回到 Teams 用戶端。  (有關政策的資訊，請參閱設定 [緊急](#configure-emergency-policies)) 。

   - 如果有 LIS 比對，Teams 用戶端所連接之網路元素的緊急位置會回到 Teams 用戶端。 會以下列循序執行比對，並返回第一個相符的結果：
       - Wap
       - 乙太網路交換器/埠
       - 乙太網路開關
       - 子網路

3. 當 Teams 用戶端撥打緊急電話時，緊急位置會傳送至 PSTN 網路。

   對於直接路由，系統管理員必須將 SBC 設定為傳送緊急電話給 ERS 提供者，或設定 SBC ELIN 應用程式。

本文包含下列各節。

- [設定緊急位址](#assign-emergency-addresses)
- [設定網路設定](#configure-network-settings)
- [設定位置資訊服務](#configure-location-information-service)
- [設定緊急政策](#configure-emergency-policies)
- [啟用使用者和網站](#enable-users-and-sites)
- [測試緊急電話](#test-emergency-calling)

自動路由至適當的公用安全答對點 (PSAP) 視 Teams 使用者的使用國家/地區而異。

若要進一步瞭解緊急電話，包括緊急位址和緊急電話路由資訊、國家/地區特定資訊，以及網路設定和網路拓撲相關資訊，請參閱下列內容：

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)

有關哪些功能可在政府雲端使用，請參閱本文結尾的政府支援[](#government-support)。


## <a name="supported-clients"></a>支援的用戶端

目前支援下列用戶端。  請經常回來查看此清單的更新。

- Microsoft Windows 版 Teams 桌面用戶端
- Apple macOS 版 Teams 桌面用戶端
- Apple iOS 用戶端版本 1.0.92.2019121004 和 App Store 版本 1.0.92 及更新版本的 Teams 行動用戶端
- Android 版 Teams 行動用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更新版本
- Teams 手機版本 1449/1.0.94.2019110802 及更新版本
- Teams 會議室版本 4.4.25.0 及更新版本

> [!NOTE]
> Teams Web 用戶端不支援動態緊急電話 ，包括安全電話台通知。 若要防止使用者使用 Teams Web 用戶端撥打 PSTN 號碼，您可以設定 Teams 通話政策，並關閉 [允許 **Web PSTN 通話設定** 。 若要深入瞭解，請參閱 [Teams 和](teams-calling-policy.md) [Set-CsTeamsCallingPolicy 中的通話政策](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。

## <a name="assign-emergency-addresses"></a>指派緊急位址

您可以將緊急位址指派給通話方案使用者，以及動態取得位置所需的網路識別碼。  (子網和 WiFi AP。 Windows 8.1 及更新版本目前支援乙太網路交換器/埠) 。

若要支援在美國境內自動路由緊急電話，您必須確保指派給網路識別碼的緊急位置包含相關聯的地理代碼。  (沒有地理代碼的緊急位址無法指派給動態位置所需的網路識別碼。) 

Azure 地圖用於位置型服務。  當您使用 Microsoft Teams 系統管理中心輸入緊急位址時，Teams 會檢查 Azure 地圖的位址：

- 如果找到相符專案，系統會自動包含地理代碼。

- 如果找不到相符專案，您將有機會手動建立緊急位址。 您可以使用 PIN 拖放功能執行此工作。 

這表示，如果為指派通話方案使用者而建立的現有緊急位置是供動態位置使用，必須重新建立相同的位址，以包含地理代碼。 若要區分這兩個位置，您應該包含不同的描述。 您可以將新的緊急位置指派給擁有舊位置的使用者。 完全移移後，可以刪除舊位置。

您可以在 Microsoft Teams 系統管理中心或 PowerShell 中新增及指派緊急位址。 詳細資訊請參閱新增 [組織的緊急](add-change-remove-emergency-location-organization.md) 位置，以及為 [使用者指派緊急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>設定網路設定

網路設定可用來判斷 Teams 用戶端的位置，以及動態取得緊急通話政策及緊急位置。 您可以根據組織希望緊急電話運作方式設定網路設定。

網路設定包括包含子網集合的網站，這些網站會專屬於將動態策略指派給使用者。 例如，緊急通話政策及緊急電話路由策略可能會指派給「Redmond 網站」，如此一來，從家中或另一個 Microsoft 位置漫遊的任何使用者，都配置了 Redmond 專用緊急號碼、路由和安全性電話機。  

>[!Note]
>子網也可以定義在 LIS 中，而且可以與緊急位置相關聯。  

請記住下列定義。 詳細資訊請參閱雲端 [語音功能的網路設定](cloud-voice-network-settings.md)。

- 信任的 IP 位址包含商業網路網際網路外部 IP 位址的集合，用來判斷使用者的端點是否位於公司網路內。 只有在使用者的外部 IP 位址與信任的 IP 位址中的 IP 位址符合時，才能嘗試取得動態策略或位置。 您可以對 IPv4 或 IPv6 IP 位址進行比對，而且要根據要送到網路設定之 IP 封包的格式而定。   (公用 IP 位址同時有 IPv4 和 IPv6，您必須將兩者新增為信任的 IP 位址。) 

- 網路區域包含網路網站集合。 

- 網路網站代表貴組織具有實際值的位置，例如辦公室、一組建築物或校園。 這些網站定義為 IP 子網集合。

- 網路子網必須與特定網路網站相關聯。 用戶端的位置是根據網路子網和相關聯的網路網站所決定。  

您可以在 Microsoft Teams 系統管理中心或 PowerShell 中設定網路設定。 若要深入瞭解，請參閱 [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。

請注意，可能需要一些時間 (可能需要數小時) ，才能對網路設定進行一些變更 (例如新位址、網路識別碼等) 來傳播並提供給 Teams 用戶端使用。  

**針對通話方案使用者：**

- 如果需要動態設定安全性電話台通知，您必須同時設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則必須只設定信任的 IP 位址。

- 如果兩者都不需要，則不需要設定網路設定。 

**針對直接路由使用者：**

- 如果需要動態啟用緊急電話或動態設定安全性電話台通知，則必須同時設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則必須只設定信任的 IP 位址。

- 如果兩者都不需要，則不需要設定網路設定。


## <a name="configure-location-information-service"></a>設定位置資訊服務

Teams 用戶端會從與不同網路識別碼相關聯的位置取得緊急位址。 支援子網和無線存取點 (WAP) 。 Windows 8.1 及更新版本目前支援乙太網路交換/埠。

若要讓用戶端取得位置，您必須在 LIS 中填入網路識別碼 (子網、WAP、交換器、埠和) 位置。 您可以在 Microsoft Teams 系統管理中心或 PowerShell 中執行此工作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側流覽中，前往 **位置**  >  **網路&位置**。
2. 按一下代表要新增之網路識別碼的選項卡。 例如，按一下 **子網****、Wi-Fi 存取點**、**交換器** 或 **埠**。 然後按一下 [ **新增**。
3. 完成欄位，新增緊急位置，然後按一下 [套 **用**。

### <a name="using-powershell"></a>使用 PowerShell

使用下列 Cmdlet 在 LIS 中新增埠、交換器、子網和 WAP。

- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)[、移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps)-CsOnlineLisSubnet
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)[、移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps)-CsOnlineLisWirelessAccessPoint
- [取得](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、[設定](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)[、移除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps)-CsOnlineLisSwitch

>[!Important]
>如果子網正作為網路網站的一部分使用，則必須在位置資訊服務中重新定義子網，以呈現動態位置。

## <a name="configure-emergency-policies"></a>設定緊急政策

使用下列政策設定緊急電話。 您可以在 Microsoft Teams 系統管理中心或 PowerShell 中管理這些策略。

- **緊急電話路由原則** - 僅適用于直接路由。 此政策會設定緊急號碼、每個號碼的遮罩 ，以及每個號碼的 PSTN 路由。  您可以將此策略指派給使用者、網路網站或兩者。  (通話方案 Teams 用戶端會根據國家/地區使用的 Microsoft 365 或 Office 365 使用位置自動啟用緊急電話。) 若要深入瞭解，請參閱管理直接路由的緊急電話路由[規則。](manage-emergency-call-routing-policies.md)

- **緊急通話原則** - 適用于通話方案與直接路由。 此策略會設定撥打緊急電話時的安全性電話台通知體驗。 您可以設定要通知哪些人，以及如何通知他們。 例如，若要自動通知貴組織的安全電話台，讓他們接聽緊急電話。  這個策略可以指派給使用者或網路網站，也可以同時指派給兩者。 若要深入瞭解，請參閱在 [Teams 中管理緊急通話政策](manage-emergency-calling-policies.md)。

## <a name="enable-users-and-sites"></a>啟用使用者和網站

您可以將緊急電話路由策略和緊急通話政策指派給使用者和網站。 請記住，緊急呼叫路由原則僅適用于直接路由。  (雖然可以將此策略指派給通話方案使用者，但該政策並沒有任何作用。) 

您可以在 Microsoft Teams 系統管理中心或 PowerShell 中指派策略。 若要深入了解，請參閱：

- [管理直接路由的緊急呼叫路由規則](manage-emergency-call-routing-policies.md)
- [在 Teams 中管理緊急通話政策](manage-emergency-calling-policies.md)

以下是一些 PowerShell 範例。

若要啟用特定使用者的安全性桌面通知，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要將稱為「Contoso 緊急電話政策 1」的「政策」指派給網站 1，請使用下列命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要啟用特定直接路由使用者進行緊急通話，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要將名為「Contoso New York 緊急電話路由」的政策指派給網站 1，請使用下列命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果您將緊急通話政策指派給網路網站和使用者，而且該使用者位於該網路網站，則指派給網路網站的策略會優先于指派給使用者的政策。

## <a name="test-emergency-calling"></a>測試緊急電話

美國部分緊急路由服務提供者 (ERSP) 提供緊急通話測試機器人。

- **美國的電話方案** 使用者可以使用預先定義的測試緊急號碼 933 驗證其緊急通話設定。 此號碼會路由至 Bot，然後回顯來電者的電話號碼 (通話線路識別碼) 、緊急位址或位置，以及該通話是否會自動路由至 PSAP 或先進行篩選。

- **美國的直接路由客戶應** 協調其 ERSP 以進行測試服務。

## <a name="government-support"></a>政府支援

下表顯示政府雲端動態緊急電話的支援：

| 雲 | 可用 性 |
| :------------|:-------|
| 全球多租使用者 | 完全可用 |
| Gcc | 可在 Teams IP 電話以外的所有用戶端使用 |
| GCCH | 等待 |
| 國防部 | 等待 |

 ## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急電話路由規則 ](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)
