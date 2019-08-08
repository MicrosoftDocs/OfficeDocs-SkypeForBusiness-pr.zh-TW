---
title: Microsoft 團隊中的雲端語音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 在小組中部署雲端語音的登陸頁面
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7a17e207911ad4865cef5b82f7fe7f5f143a172
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236976"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Microsoft 團隊中的雲端語音

您已完成[快速入門](get-started-with-teams-quick-start.md)。 您已在整個組織中利用[聊天、團隊、頻道、& 應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)來推出小組。 也許您已將[會議 & 會議](deploy-meetings-microsoft-teams-landing-page.md)已部署。 現在您已經準備好為使用者新增雲端語音功能。 

雲端語音提供私人分支 Exchange (PBX) 功能, 以及連線至公用交換電話網絡 (PSTN) 的選項。

本文可協助您決定是否需要根據貴組織的設定檔和業務需求變更任何預設雲端語音設定, 然後逐步引導您完成每項變更。 我們已將這些設定分割成兩個群組, 從[您更容易進行](#core-deployment-decisions)的核心變更集合開始。 第二個群組包含您可能想要設定的[其他設定](#additional-deployment-decisions), 視貴組織的需求而定。

我們建議所有組織都在核心決策中運作, 然後, 如果您的組織有其他需求, 請參閱下列資料。



## <a name="learn-more-about-cloud-voice"></a>深入瞭解雲端語音

下列文章提供在小組中部署和使用雲端語音功能的詳細資訊:

- [Office 365 中的電話系統](what-is-phone-system-in-office-365.md)
- [含有通話方案的電話系統](calling-plan-landing-page.md)
- [電話系統直向路由](direct-routing-landing-page.md)
- [雲端語音部署](cloud-voice-deployment.md)
- [Microsoft 電話解決方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 請觀看下列會話, 深入瞭解手機系統: [Microsoft 團隊中的電話系統簡介](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>核心部署決定

這些是大多陣列織想要變更的設定 (如果小組預設設定不適用於組織)。

## <a name="phone-system-office-365"></a>電話系統 (Office 365)

[電話系統] 是 Microsoft 的技術, 可在 Office 365 雲端啟用呼叫控制和私人分支 Exchange (PBX) 功能。 [電話系統] 可讓您將現有的私人分支 Exchange (PBX) 系統取代為直接從 Office 365 提供的一組功能, 並緊密整合至公司的雲端生產力體驗。


|問自己|執行 |
|:------------|:-------|
|我要在哪個使用者位置或辦公室實現電話系統？ |如需電話系統的詳細資訊, 請參閱[Office 365 中的 [什麼是電話系統](what-is-phone-system-in-office-365.md)]。</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>連線到公用交換電話網絡 (PSTN)

若要將電話系統連線至公用的交換電話網絡 (PSTN), 讓使用者可以撥打世界各地的電話, 您可以根據業務需求選擇一些選項。  請自問下列事項:


|問自己|執行 |
| :------------|:-------|
| 我要使用 Microsoft 通話方案做為我的電話語音運營商嗎？ | 如需詳細資訊, 請參閱[含有通話方案的電話系統](calling-plan-landing-page.md)。|
| 我需要使用自己的電話運營商嗎？ | 如需詳細資訊, 請參閱[直接路由的電話系統](direct-routing-landing-page.md)。
|||


## <a name="additional-deployment-decisions"></a>其他部署決定

根據貴組織的需求和設定, 您可能會想要變更下列專案的設定:

- 語音信箱
- 通話身分識別
- Microsoft 的電話號碼
- 撥號方案
- 通話佇列
- 自動語音應答

### <a name="voicemail"></a>語音信箱

雲端語音信箱 (由 Azure 語音信箱服務提供支援) 只支援將語音信箱存款至 Exchange 信箱, 且不支援協力廠商電子郵件系統。 雲端語音信箱包括語音信箱, 預設會針對貴組織中的所有使用者啟用該功能。 您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。

|問自己|執行 |
|:------------|:-------|
| 我想要啟用雲端語音信箱嗎？ | 如需語音信箱設定程式, 請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。
| 我想要針對部分或所有使用者啟用語音信箱功能嗎？ | 若要關閉語音信箱, 請參閱[設定貴組織中的語音信箱原則](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)。</li></ul>|
|||

### <a name="calling-identity"></a>通話身分識別

根據預設, 所有出站通話都會將指派的電話號碼做為呼叫身分識別 (來電者識別碼)。 通話的收件者可以快速識別來電者, 決定是否要接受或拒絕通話。

|問自己|執行 |
|:------------|:-------|
|我想要遮罩或停用本機號碼嗎？ | 若要變更或封鎖本機號碼, 請參閱[設定使用者的本機號碼](set-the-caller-id-for-a-user.md)。 |
|||

### <a name="phone-numbers-from-microsoft"></a>Microsoft 的電話號碼

Microsoft 提供兩種電話號碼類型: 可指派給貴組織中的使用者的*訂閱者*(使用者) 號碼, 以及*服務*號碼 (以付費和免付費服務號碼提供), 這些號碼都有較高的同時通話容量比訂閱者號碼還可以指派給諸如音訊會議、自動語音應答或通話佇列等服務。

|問自己|執行 |
| :------------|:-------|
| 哪些使用者位置需要來自 Microsoft 的新電話號碼？ | 如需取得電話號碼的相關資訊, 請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md), 以及[為使用者取得電話號碼](getting-phone-numbers-for-your-users.md)。 
| 我需要哪一種類型的電話號碼 (訂閱者或服務)？ | 若要協助您挑選所需的電話號碼類型, 請參閱[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)。
我要如何將現有的電話號碼移植至 Office 365？|如需詳細資訊, 請參閱[將電話號碼轉移至 Office 365](transfer-phone-numbers-to-office-365.md)。
|||

### <a name="dial-plans"></a>撥號方案

Office 365 的 [電話系統] 功能中的撥號方案是一組正常化規則, 可將撥打的電話號碼轉換成替代格式 (通常是164個格式), 用於呼叫授權及呼叫路由。

如需撥號方案的詳細資訊, 請參閱[什麼是撥號方案？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|問自己|執行 |
|:------------|:-------|
| 我的組織是否需要自訂的撥號方案？ | 若要協助判斷您是否需要自訂撥號方案, 請參閱[規劃租使用者撥號方案](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
哪些使用者需要自訂的撥號方案, 以及應該將哪些租使用者撥號方案指派給每個使用者？ | 若要將使用者新增至 PowerShell 中的自訂撥號方案, 請參閱[建立及管理撥號方案](create-and-manage-dial-plans.md)。 |
|||

### <a name="call-queues"></a>通話佇列

雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能, 以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。 您可以為組織建立單一或多個通話佇列。 


|問自己|執行 |
|:------------|:-------|
| 我的組織是否需要呼叫佇列？ | 如需詳細資訊, 請參閱[建立雲端通話佇列](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)及[設定您的電話系統](setting-up-your-phone-system.md)。 |

### <a name="auto-attendants"></a>自動語音應答

雲端自動語音應答可用來為您的組織建立功能表系統, 讓外部和內部呼叫者在功能表系統間移動, 以找出電話, 並將來電放到貴組織中的公司使用者或部門中。

|問自己|執行 |
|:------------|:-------|
| 我的組織是否需要自動語音應答？ | 如需詳細資訊, 請參閱[什麼是雲端自動](what-are-phone-system-auto-attendants.md)語音應答, 以及[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答。 |

### <a name="devices"></a>台

如需支援的裝置的詳細資訊, 請參閱下列內容:

- [在 Microsoft 團隊中管理您的裝置](device-management.md)
- [IP 電話](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB 音訊與視頻裝置](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [裝置的智慧通訊](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


