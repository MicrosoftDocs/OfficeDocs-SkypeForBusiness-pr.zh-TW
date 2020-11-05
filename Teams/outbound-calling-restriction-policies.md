---
title: 呼出通話限制-語音會議 & PSTN 通話
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 系統管理員可以控制使用者可以發出的音訊會議和使用者 PSTN 呼叫類型。
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908652"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音訊會議和使用者 PSTN 通話的撥出通話限制原則

身為系統管理員，您可以使用撥出通話控制來限制組織中的使用者可進行的音訊會議類型和終端使用者 PSTN 通話類型。 

輸出呼叫控制可以在每位使用者的基礎上套用，並提供下列兩個控制項來單獨限制每個輸出呼叫類型。 根據預設，兩個控制項都設定為允許國際和國內呼出通話。 

|控制權|說明|控制選項|
|:-----|:-----|:-----|
|音訊會議 PSTN 通話|限制輸出類型 </br>內部允許的通話 </br>由使用者組織的會議。|任何目的地 (預設) </br>在召集人所在的國家或地區 </br> 僅限[區域中的國家或地區](audio-conferencing-zones.md) </br>不允許|
|最終使用者 PSTN 通話|限制通話類型 </br>使用者可以進行的工作。|國際及國內 (預設) </br>家用</br>無|

若要找出哪些國家和地區被視為區域 A，請參閱 [音訊會議的國家和地區區域](audio-conferencing-zones.md)。

   > [!NOTE]
   > 如果撥打的電話號碼位於與)  (會議召集人設定的 Microsoft 365 或 Office 365 相同的國家/地區，或在最終使用者 PSTN 呼叫) 的情況下 (，則會被視為國內通話。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音訊會議撥出通話

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 [ **使用者** ]，然後從可用使用者清單中按一下使用者的顯示名稱。

3. 按一下 [ **音訊會議** ] 旁的 [ **編輯** ]。

4. 在 [ **從會議撥出** ] 底下，選取您想要的撥出限制選項。

5. 按一下 [儲存]。 

![商務用 Skype 標誌圖示](media/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

1. 在 **商務用 Skype 系統管理中心** 的左導覽中，前往 [ **音訊會議**  >  **使用者** ]，然後從可用使用者清單中選取使用者。

2. 在 [動作] 窗格中，按一下 [ **編輯** ]。

3.  在 [ **限制使用此使用者的會議進行撥** 出] 底下，選取您想要的撥出限制選項。

      ![撥出選項的限制](media/restrictions-to-dial-outs.png)
      

4. 按一下 [儲存]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 PowerShell**

出站通話限制是由名為 OnlineDialOutPolicy 的單一原則所控制，每個策略都有一個限制屬性。 原則無法自訂，而是針對每個設定組合提供預先定義的原則實例。 

您可以使用 Get-CSOnlineDialOutPolicy Cmdlet 來查看輸出通話原則，並使用 Grant-CSDialOutPolicy Cmdlet 將其指派給使用者。  (請注意，Grant Cmdlet 不會包含「線上」一詞，因為取得 Cmdlet 一樣。 )  

下表提供每個原則的概覽。

|||
|:-----|:-----|
|身分識別 = "tag： DialoutCPCandPSTNInternational"    |    會議中的使用者可以撥出到國際和國內號碼，此使用者也可以撥出電話給國際和國內電話號碼。    |
|身分識別 = "tag： DialoutCPCDomesticPSTNInternational"  |    會議中的使用者只能撥出至國內號碼，而這個使用者可以撥出電話給國際和國內號碼。    |
|    身分識別 = "tag： DialoutCPCDisabledPSTNInternational"    |    會議中的使用者無法進行任何撥出。此使用者可以撥出電話給國際和國內號碼。    |
|    身分識別 = "tag： DialoutCPCInternationalPSTNDomestic"    |    會議中的使用者可以撥出到國際和國內電話號碼，而且這個使用者只能撥打出站通話至國內 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCInternationalPSTNDisabled"    |    會議中的使用者可以撥出到國際和國內號碼，而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCandPSTNDomestic"    |    會議中的使用者只能撥出至國內號碼，而且這個使用者只能撥打外線電話給國內 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCDomesticPSTNDisabled"    |    會議中的使用者只能撥出至國內號碼，而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCDisabledPSTNDomestic"    |    會議中的使用者無法進行撥出，而且這個使用者只能撥打外線電話給國內 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCandPSTNDisabled"    |    會議中的使用者無法撥出任何電話，而且除了緊急數位以外，此使用者無法進行任何出站呼叫 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCZoneAPSTNInternational"    |    會議中的使用者只能撥出以對 [國家和地區進行分區](audio-conferencing-zones.md)，而且這個使用者可以撥出電話給國際和國內號碼。    |
|    身分識別 = "tag： DialoutCPCZoneAPSTNDomestic"    |    會議中的使用者只能撥出以對 [國家和地區進行分區](audio-conferencing-zones.md)，而且這個使用者只能撥打出站通話至國內 PSTN 號碼。    |
|    身分識別 = "tag： DialoutCPCZoneAPSTNDisabled"    |    會議中的使用者只能撥出以對 [國家和地區進行分區](audio-conferencing-zones.md)，而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。    |
