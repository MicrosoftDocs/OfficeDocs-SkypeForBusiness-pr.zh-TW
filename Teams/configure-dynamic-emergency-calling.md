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
- highpri
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft 通話方案和電話系統直接路由動態緊急通話功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1061adf81b8e9ae84ad028a5047636b6fee7a959
ms.sourcegitcommit: 052e4b3982b0b8ee7d4edc47da4d63b35518a757
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2023
ms.locfileid: "69814355"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>規劃和設定動態緊急電話 

Microsoft 通話方案、運算子連線、Teams Phone Mobile 和直接路由的動態緊急通話功能可設定和路由緊急通話，並根據 Teams 用戶端的目前位置通知安全性人員。  

根據與租使用者系統管理員定義之緊急位址) 相關聯的網路拓撲 (網路元素，Teams 用戶端會在連至定位資訊服務 (LIS) 的要求中提供網路連線資訊。 如果有相符專案，LIS 會傳回用戶端的位置。

Teams 用戶端會在緊急通話中包含位置資料。 然後緊急服務提供者會使用此資料來判斷適當的[Public Safety Answer point] (PSAP) ，並將通話路由至該 PSAP，讓 PSAP 調度人員取得來電者的位置。  

若要進行動態緊急通話，必須進行下列動作：

1. 網路系統管理員設定網路設定和 LIS 以建立網路/緊急位置地圖。

2. 在啟動期間和之後定期，或在網路連線變更時，Teams 用戶端會傳送一個位置要求，其中包含其網路連線資訊給網路設定和 LIS。

   - 如果有符合網站的網路設定 –緊急通話原則會從該網站傳回至 Teams 用戶端。  (如需原則的詳細資訊，請參閱) 設定 [緊急](#configure-emergency-policies) 原則。

   - 如果有 LIS 相符 ，Teams 用戶端連線的網路元素會傳回至 Teams 用戶端的緊急位置。 會依照下列循序執行比對，並傳回第一個相符的結果：
       - Wap
       - 乙太網路開關/埠
       - 乙太網路切換
       - 子網路

3. 當 Teams 用戶端撥打緊急電話時，緊急位置會傳送至 PSTN 網路。

自動路由到適當 [Public Safety Answer point] (PSAP) 的能力，取決於 Teams 使用者的使用國家/地區。

Microsoft 通話方案、運算子連線合作夥伴和 Teams Phone Mobile 合作夥伴都包含適用于美國和加拿大使用者的動態緊急路由服務。

不過，對於直接路由，路由緊急電話需要額外的設定，而且可能還需要合作夥伴連線。 系統管理員必須確定已設定傳送緊急電話的 PSTN 閘道，將線上 PSTN 閘道物件上的參數 PidfloSupported 設為 True，以將位置資訊新增至外寄 INVITE (。 此外，系統管理員必須設定與緊急路由服務 (ERS) 提供者的連線， (美國和加拿大) **或** 針對緊急位置識別編號 (ELIN) 應用程式設定會話框線控制器 (SBC) 。 如需 ERS 提供者的相關資訊，請參閱 [通過直接路由認證的會話框線控制器](direct-routing-border-controllers.md)。

本文包含下列各節。

- [指派緊急位址](#assign-emergency-addresses)
- [設定網路設定](#configure-network-settings)
- [設定位置資訊服務](#configure-location-information-service)
- [設定緊急原則](#configure-emergency-policies)
- [啟用使用者和網站](#enable-users-and-sites)
- [測試緊急通話](#test-emergency-calling)

如需緊急電話的詳細資訊，包括緊急位址和緊急電話路由的相關資訊、國家/地區的特定資訊，以及網路設定和網路拓撲的相關資訊，請參閱下列各項：

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)

如需有關哪些功能可在政府雲端中使用的詳細資訊，請參閱本文結尾的 [政府支援](#government-support) 。


## <a name="supported-clients"></a>支援的用戶端

目前支援下列用戶端。  請經常回來查看此清單的更新。

- 適用于 Microsoft Windows 的 Teams 桌面用戶端
- 適用于 Apple macOS 的 Teams 桌面用戶端
- 適用于 Apple iOS 用戶端版本 1.0.92.2019121004 和 App Store 版本 1.0.92 及更新版本的 Teams 行動用戶端
- 適用于 Android 用戶端和 Google Play 商店版本 1416/1.0.0.2019121201 及更新版本的 Teams 行動用戶端
- Teams 手機版本 1449/1.0.94.2019110802 及更新版本
- Teams 會議室版本 4.4.25.0 及更新版本

> [!NOTE]
> 所有支援的 Teams 用戶端都支援子網路和 WiFi 位置。 <br><br>
> 支援乙太網路/切換 (LLDP) ：
> - Windows 版本 10.0 和此時更新版本。<br>
> - 需要 [LLDP 啟用軟體的](https://www.microsoft.com/download/details.aspx?id=103383)Mac OS。<br>
> - Teams 手機與 Teams 應用程式版本 1449/1.0.94.2021110101 及更新版本。

> [!NOTE]
> Teams Web 用戶端不支援動態緊急通話，包括安全性中心通知。 若要防止使用者使用 Teams Web 用戶端撥打 PSTN 號碼，您可以設定 Teams 通話原則，並關閉 [ **允許 Web PSTN 通話** ] 設定。 若要深入瞭解，請參閱 [Teams 和](teams-calling-policy.md) [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)中的通話原則。 

> [!NOTE]
> 3PIP 電話不支援動態緊急通話。 



## <a name="assign-emergency-addresses"></a>指派緊急位址

您可以指派緊急位址，如下所示：

- 撥打給方案使用者。

- To Operator Connect and Teams Phone Mobile users &mdash; depending the capabilities assigned to the number when the carrier upload them to a customer's inventory.

- 移至動態取得位置所需的網路識別碼。 

若要支援在美國內自動路由緊急呼叫，您必須確保指派給網路識別碼的緊急位置包含相關的地理位置代碼。  (無法將沒有地理位置代碼的緊急位址指派給動態位置所需的網路識別碼。) 

Azure 地圖服務用於位置型服務。 當您使用 Microsoft Teams 系統管理中心輸入緊急位址時，Teams 會檢查位址Azure 地圖服務：

- 如果找到相符專案，即會自動包含地理代碼。

- 如果找不到相符專案，您將有機會手動建立緊急位址。 您可以使用 PIN 下拉功能來執行此動作。 

> [!NOTE]
> 超過數年的緊急位址無法指派給網路識別碼。 您必須重新建立較舊的位址。

您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 新增和指派緊急位址。 如需詳細資訊，請參閱 [為組織新增緊急位置](add-change-remove-emergency-location-organization.md) 和 [指派使用者的緊急位置](assign-change-emergency-location-user.md)。

## <a name="configure-network-settings"></a>設定網路設定

網路設定是用來判斷 Teams 用戶端的位置，以及動態取得緊急通話原則和緊急位置。 您可以根據貴組織希望緊急電話運作的方式來設定網路設定。

網路設定包括包含子網集合的網站，這些網站僅供動態原則指派給使用者。 例如，緊急通話原則和緊急電話路由原則可能會指派給「Redmond 網站」，讓從家或其他 Microsoft 位置漫遊的任何使用者都設定為 Redmond 專用的緊急號碼、路由和安全性服務台。  

信任的 IP 位址包含商業網路的網際網路外部 IP 位址集合，用來判斷使用者的端點是否在公司網路內。 只有在使用者的外部 IP 位址符合受信任 IP 位址中的 IP 位址時，才會嘗試取得動態原則或位置。

如需 IP 位址、網路區域、網站和子網址的詳細資訊，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。

您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 來設定網路設定。 若要深入瞭解，請參閱 [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)。

請注意，) 一些網路設定變更 (，例如新的位址、網路識別碼等，可能需要一些時間 (長達數小時的時間，) 傳播並提供給 Teams 用戶端使用。  

> [!Note]
> 子網也可以在 LIS 中定義，而且可以與緊急位置相關聯。  LIS 子網必須由與指派給用戶端的子網 IP 範圍相符的網路識別碼定義。 例如，10.10.10.150/25 用戶端 IP/遮罩的網路識別碼是 10.10.10.128。 如需詳細資訊，請 [參閱瞭解 TCP/IP 位址和子網的基本概念](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)。

> [!Important]
> 修改 Teams 用戶端來源 IP 位址的雲端 Proxy 服務部署不支援網路設定設定查閱。



**針對通話方案、電信業者連線和 Teams Phone Mobile 使用者：**

- 如果需要安全性中心通知的動態設定，您必須同時設定受信任的 IP 位址和網路網站。

- 如果只需要動態位置，您必須只設定信任的 IP 位址;不需要設定網路設定。

- 如果兩者都不需要，則不需要設定網路設定。 

**針對直接路由使用者：**

- 如果需要動態啟用緊急通話或動態設定安全性辦公桌通知，則必須同時設定信任的 IP 位址和網路網站。

- 如果只需要動態位置，您必須只設定信任的 IP 位址;不需要設定網路設定。

- 如果兩者都不需要，則不需要設定網路設定。


## <a name="configure-location-information-service"></a>設定位置資訊服務

Teams 用戶端會從與不同網路識別碼相關聯的位置取得緊急位址。 

若要讓用戶端取得位置，您必須使用網路識別碼填入 LIS (子網、WAP、開關、埠) 和緊急位置。 您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 執行此動作。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 [**位置**  >  **網路] &位置。**
2. 按一下代表您要新增之網路識別碼的索引標籤。 例如，按一下 [ **子網]**、 **[Wi-Fi 存取點]**、 **[參數]** 或 [ **埠]**。 然後按一下 [ **新增]**。
3. 完成欄位、新增緊急位置，然後按一下 [ **套用]**。

### <a name="using-powershell"></a>使用 PowerShell

使用下列 Cmdlet 將埠、開關、子網及 WAP 新增至 LIS。

- [取得](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [取得](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [取得](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [取得](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [設定](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [移除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>如果子網是做為網路網站的一部分使用，則必須在位置資訊服務中重新定義子網，才能呈現動態位置。

## <a name="configure-emergency-policies"></a>設定緊急原則

使用下列原則來設定緊急通話。 您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 來管理這些原則。

- **緊急通話路由原則 - 僅適用于直接路由**。 此原則會設定緊急號碼、視需要遮罩每一個數位，以及每個號碼的 PSTN 路由。 您可以將此原則指派給使用者、網路網站或兩者。 若要深入瞭解，請參閱 [管理直接路由的緊急通話路由原則](manage-emergency-call-routing-policies.md)。  

    (通話方案、運算子連線和 Teams Phone Mobile 使用者會根據其 Microsoft 365 或Office 365使用位置，自動啟用來自國家/地區的緊急電話號碼進行緊急通話。) 

- **緊急通話原則 - 適用于通話方案、電信業者連線、Teams Phone Mobile 和直接路由。** 這項原則會在撥打緊急電話時設定安全性中心通知體驗。 您可以設定要通知的人員，以及他們收到通知的方式。 例如，若要自動通知貴組織的安全性服務台，並讓他們聆聽緊急電話。  這個原則可以指派給使用者或網路網站，或同時指派給兩者。 若要深入瞭解，請參閱 [管理 Teams 中的緊急通話原則](manage-emergency-calling-policies.md)。

## <a name="enable-users-and-sites"></a>啟用使用者和網站

您可以將緊急通話路由原則和緊急通話原則指派給使用者和網站。 請記住，緊急通話路由原則僅適用于直接路由。  (雖然可以將此原則指派給通話方案、運算子連線或 Teams Phone Mobile 使用者，但原則不會生效。) 

您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 指派原則。 若要深入了解，請參閱：

- [管理直接路由的緊急通話路由原則](manage-emergency-call-routing-policies.md)
- [管理 Teams 中的緊急通話原則](manage-emergency-calling-policies.md)

以下是 PowerShell 範例：

若要針對安全性辦公桌通知啟用特定使用者，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

若要將名為「Contoso 緊急通話原則 1」的原則指派給網站 1，請使用下列命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

若要啟用特定的直接路由使用者進行緊急通話，請使用下列命令：

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

若要將名為「Contoso New York 緊急電話路由」的原則指派給網站 1，請使用下列命令：

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

如果您將緊急通話原則指派給網路網站和使用者，而如果該使用者位於該網路網站，則指派給該網路網站的原則會覆寫指派給使用者的原則。

## <a name="test-emergency-calling"></a>測試緊急通話

美國中的某些緊急路由服務提供者 (ERSP) 提供緊急通話測試機器人。

- **美國或加拿大的通話方案、電信業者連線和 Teams Phone Mobile 使用者** 可以使用預先定義的測試緊急號碼 933 來驗證其緊急通話設定。 此號碼會路由至 Bot，隨後會回溯來電者電話號碼 (電話線識別碼) 、緊急位址或位置，以及通話是否會自動路由至 PSAP 或先進行螢幕。

- **直接路由至美國中的客戶** 應與其 ERSP 進行測試服務的協調。

## <a name="government-support"></a>政府支援

下表顯示政府雲端中動態緊急通話的支援：

| 雲 | 可用 性 |
| :------------|:-------|
| 全球多租使用者 | 適用于所有 Teams 用戶端 |
| Gcc | 適用于所有 Teams 用戶端 |
| GCCH | -可在 Teams 電腦版上使用 <br> -可在 Teams 行動用戶端上使用 <br> -適用于 Teams 手機、應用程式版本：1449/1.0.94.2022061702 |
| 國防部 | -可在 Teams 電腦版上使用 <br>-可在 Teams 行動用戶端上使用 <br>-在 Teams 手機上擱置中 |

 ## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急通話路由原則 ](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [雲端語音功能的網路設定](cloud-voice-network-settings.md)
- [管理雲端語音功能的網路拓撲](manage-your-network-topology.md)
