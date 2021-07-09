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
description: 瞭解如何設定 Microsoft 通話方案電話系統直接路由動態緊急電話功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e399c5e18bc90f99ebe59f3f4e603da5f7cbfe9
ms.sourcegitcommit: 1c5608e6b539e90e42f48212d038f861ecf8136b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53337832"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>規劃和設定動態緊急電話 

Microsoft 通話方案與直接路由的動態緊急電話系統提供設定和路由緊急電話的能力，並依據用戶端的目前位置通知Teams人員。  

根據租使用者系統管理員定義的網路拓撲，Teams用戶端會向位置資訊服務中心或 LIS (提供網路) 。 如果有相符專案，LIS 會將位置返回用戶端。 此位置資料會傳回用戶端。  

用戶端Teams緊急通話中包含位置資料。 然後，緊急服務提供者會使用這些資料來判斷適當的公用安全應答點 (PSAP) ，然後將通話路由至該 PSAP，讓 PSAP 調度員取得來電者的位置。  

針對動態緊急電話，必須發生下列情況：

1. 網路系統管理員會設定網路設定和 LIS，以建立網路/緊急位置地圖。

   針對直接路由，路由緊急電話需要其他組組，並可能還需要合作夥伴連接。 系統管理員必須為緊急位置識別號碼 (ELIN) 應用程式設定與緊急路由服務 (ERS) 提供者 (美國) 或會話邊界控制器 (SBC) 的連接。

2. 在啟動期間和之後定期，或網路連接變更時，Teams用戶端會傳送包含其網路連接資訊的位置要求至網路設定和 LIS。

   - 如果有網路設定網站相符 ，緊急電話Teams會從該網站回到用戶端。  (有關政策的資訊，請參閱設定 [緊急](#configure-emergency-policies)) 。

   - 如果有 LIS 相符專案，則從已連接用戶端Teams網路元素的緊急位置會Teams用戶端。 會以下列循序執行比對，並返回第一個相符的結果：
       - Wap
       - 乙太網路交換器/埠
       - 乙太網路交換器
       - 子網路

3. 當Teams用戶端撥打緊急電話時，緊急位置會傳送至 PSTN 網路。

   對於直接路由，系統管理員必須將 SBC 設定為傳送緊急電話給 ERS 提供者，或設定 SBC ELIN 應用程式。

本文包含下列各節。

- [設定緊急位址](#assign-emergency-addresses)
- [設定網路設定](#configure-network-settings)
- [設定位置資訊服務](#configure-location-information-service)
- [設定緊急政策](#configure-emergency-policies)
- [啟用使用者和網站](#enable-users-and-sites)
- [測試緊急通話](#test-emergency-calling)

自動路由至適當的安全性應答點 (PSAP) 的能力會視使用者使用Teams國而異。

若要進一步瞭解緊急電話，包括緊急位址和緊急電話路由的資訊、國家/地區特有的資訊，以及網路設定和網路拓撲的資訊，請參閱下列內容：

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)

有關哪些功能可在政府雲端使用，請參閱本文結尾的政府支援[](#government-support)。


## <a name="supported-clients"></a>支援的用戶端

目前支援下列用戶端。  經常回來查看此清單的更新。

- Teams Microsoft 電腦版桌面Windows
- Teams MacOS 版桌面用戶端
- Teams適用于 Apple iOS 用戶端版本 1.0.92.2019121004 和 App Store 版本 1.0.92 及更新版本的行動用戶端
- Teams Android 用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更新版本的行動用戶端
- Teams 1449/1.0.94.2019110802 及更新版本
- Teams 會議室版本 4.4.25.0 及更新版本

> [!NOTE]
> 3PIP 電話不支援動態緊急電話。 

> [!NOTE]
> Web 用戶端不支援動態緊急電話，包括安全Teams通知。 若要防止使用者使用網路用戶端Teams PSTN 號碼，您可以設定Teams，並關閉 [允許 **Web PSTN** 通話設定。 若要深入瞭解，請參閱在[](teams-calling-policy.md)Teams[和 Set-CsTeamsCallingPolicy 中的通話政策](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 

> [!NOTE]
> 所有用戶端都支援子網和 WiFi Teams位置。 <br>
> 乙太網路/ (LLDP) 僅支援 Windows 且目前僅支援 Windows 8.1 及更新版本。

## <a name="assign-emergency-addresses"></a>指派緊急位址

您可以將緊急位址指派給通話方案使用者，以及動態取得位置所需的網路識別碼。  (子網和 WiFi AP 支援。 目前支援乙太網路Windows 8.1/埠) 。

若要支援美國境內緊急電話的自動路由，您必須確保指派給網路識別碼的緊急位置包含相關聯的地理代碼。  (沒有地理代碼的緊急位址無法指派給動態位置所需的網路識別碼。) 

Azure 地圖用於位置型服務。  當您使用系統管理中心輸入緊急位址Microsoft Teams，Teams檢查 Azure 地圖位址：

- 如果找到相符專案，系統會自動包含地理代碼。

- 如果找不到相符專案，您將有機會手動建立緊急位址。 您可以使用 PIN 拖放功能執行此工作。 

這表示，如果為指派給通話方案使用者而建立的現有緊急位置是針對動態位置所建立，必須重新建立相同的位址，以包含地理代碼。 若要區別這兩個位置，您應該包含不同的描述。 新的緊急位置可以指派給擁有舊位置的使用者。 完全移移後，可以刪除舊位置。

您可以在系統管理中心Microsoft Teams或使用 PowerShell 來新增和指派緊急位址。 若要詳細資訊，請參閱 [為貴組織](add-change-remove-emergency-location-organization.md) 新增緊急位置，以及指派 [使用者的緊急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>設定網路設定

網路設定可用來判斷用戶端Teams，以及動態取得緊急通話策略和緊急位置。 您可以根據貴組織希望緊急電話運作方式來設定網路設定。

網路設定包括包含子網集合的網站，這些網站僅用於動態策略指派給使用者。 例如，緊急通話策略和緊急電話路由策略可能會指派給「Redmond 網站」，讓任何從家用或另一個 Microsoft 位置漫遊的使用者，都使用 Redmond 特有的緊急號碼、路由和安全性電話機進行配置。  

> [!Note]
> 子網也可以定義在 LIS 中，而且可以與緊急位置相關聯。  LIS 子網必須由符合指派給用戶端之子網 IP 範圍的網路識別碼定義。 例如，用戶端 IP/遮罩 10.10.10.150/25 的網路識別碼是 **10.10.10.128**。 詳細資訊請參閱瞭解 [TCP/IP 位址和子網劃分基本功能](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。

> [!Important]
> 雲端 Proxy 服務部署不支援網路設定設定檢查，這些部署會修改來自Teams IP 位址。

請記住下列定義。 詳細資訊，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。

- 信任的 IP 位址包含商業網路的網際網路外部 IP 位址集合，並用來判斷使用者的端點是否位於公司網路內。 只有在使用者的外部 IP 位址符合信任的 IP 位址中的 IP 位址時，才能嘗試取得動態策略或位置。 您可以根據 IPv4 或 IPv6 IP 位址進行比對，並視要送往網路設定之 IP 封包的格式而定。   (如果公用 IP 位址同時有 IPv4 和 IPv6，您必須同時將兩者新增為信任的 IP 位址。) 

- 網路區域包含網路網站的集合。 

- 網路網站代表貴組織具有實體值的位置，例如辦公室、一組建築物或校園。 這些網站定義為 IP 子網的集合。

- 網路子網必須與特定網路網站相關聯。 用戶端的位置是根據網路子網和相關網路網站所決定。  

您可以在系統管理中心Microsoft Teams或使用 PowerShell 來設定網路設定。 若要深入瞭解，請參閱 [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。

請注意，網路設定 (可能需要一些時間) 才能進行一些網路設定變更 (例如新位址、網路識別碼等) 來傳播，並且可供 Teams 用戶端使用。  

**針對通話方案使用者：**

- 如果需要動態設定安全電話台通知，您必須同時設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則必須只設定信任的 IP 位址。

- 如果兩者都不需要，則不需要設定網路設定。 

**針對直接路由使用者：**

- 如果需要動態啟用緊急電話或安全性電話台通知的動態設定，則必須同時設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，則必須只設定信任的 IP 位址。

- 如果兩者都不需要，則不需要設定網路設定。


## <a name="configure-location-information-service"></a>設定位置資訊服務

用戶端Teams會從與不同網路識別碼相關聯的位置取得緊急位址。 支援子網和無線存取點 (WAP) 。 目前支援乙太網路Windows 8.1/埠。

若要讓用戶端取得位置，您必須在 LIS 中填入網路識別碼 (子網、WAP、切換器、埠和) 位置。 您可以在系統管理中心Microsoft Teams PowerShell 執行此工作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側流覽中，前往位置  >  **網路&位置**。
2. 按一下代表要新增之網路識別碼的 Tab。 例如，按一下 **[子網****、Wi-Fi 存取點、****開關** 或 **埠。** 然後按一下 [ **新增**。
3. 完成欄位，新增緊急位置，然後按一下 [ **套用**。

### <a name="using-powershell"></a>使用 PowerShell

使用下列 Cmdlet 在 LIS 中新增埠、切換、子網和 WAP。

- [取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>如果子網是作為網路網站的一部分使用，則必須在位置資訊服務中重新定義子網，以呈現動態位置。

## <a name="configure-emergency-policies"></a>設定緊急政策

使用下列策略來設定緊急電話。 您可以在系統管理中心Microsoft Teams使用 PowerShell 來管理這些策略。

- **緊急電話路由原則** - 僅適用于直接路由。 此策略會設定緊急號碼、每個號碼的遮罩 ，以及每個號碼的 PSTN 路由。  您可以將此策略指派給使用者、網路網站或兩者。  (通話方案 Teams 用戶端會根據國家/地區 Microsoft 365 或 Office 365 使用位置自動啟用緊急電話。) 若要深入瞭解，請參閱管理直接路由的緊急電話路由[策略。](manage-emergency-call-routing-policies.md)

- **緊急通話原則** - 適用于通話方案及直接路由。 此策略會設定撥打緊急電話時的安全性電話台通知體驗。 您可以設定要通知哪些人，以及如何通知他們。 例如，若要自動通知貴組織的安全電話台，讓他們接聽緊急電話。  此策略可以指派給使用者或網路網站，也可以同時指派給使用者或網路網站。 若要深入瞭解，請參閱在 Teams 中[管理緊急Teams。](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>啟用使用者和網站

您可以將緊急通話路由策略和緊急通話策略指派給使用者和網站。 請記住，緊急通話路由原則僅適用于直接路由。  (雖然可以將此策略指派給通話方案使用者，但該政策將沒有任何作用。) 

您可以在系統管理中心Microsoft Teams使用 PowerShell 指派策略。 若要深入了解，請參閱：

- [管理直接路由的緊急通話路由策略](manage-emergency-call-routing-policies.md)
- [在 Teams](manage-emergency-calling-policies.md)

以下是一些 PowerShell 範例。

若要啟用特定使用者的安全性桌面通知，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要將名為「Contoso 緊急電話政策 1」的政策指派給網站 1，請使用下列命令：

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

如果您將緊急通話策略指派給網路網站和使用者，且該使用者位於該網路網站，則指派給網路網站的策略會取代指派給使用者的策略。

## <a name="test-emergency-calling"></a>測試緊急通話

美國部分緊急路由服務提供者 (ERSP) 提供緊急通話測試 Bot。

- **美國的通話方案使用者可以** 使用預先定義的測試緊急號碼 933 來驗證其緊急通話設定。 此號碼會路由至 Bot，然後回顯來電者的電話號碼 (電話線識別碼) 、緊急位址或位置，以及通話是否會自動路由至 PSAP 或先進行篩選。

- **美國的直接路由客戶應該** 與他們的 ERSP 協調，以進行測試服務。

## <a name="government-support"></a>政府支援

下表顯示政府雲端動態緊急電話的支援：

| 雲 | 可用 性 |
| :------------|:-------|
| 全球多重租使用者 | 可在所有用戶端Teams使用 |
| GCC | 可在所有用戶端Teams使用 |
| GCCH | 可在桌面Teams使用 |
| 國防部 | 等待 |

 ## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急通話路由策略 ](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)
