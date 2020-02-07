---
title: 音訊會議和使用者 PSTN 通話的撥出通話限制原則
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
description: 系統管理員可以控制使用者可以發出的音訊會議和使用者 PSTN 呼叫類型。
ms.openlocfilehash: 830ab45178c10ab485d50aafd66a4bf5d4db9011
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836883"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音訊會議和使用者 PSTN 通話的撥出通話限制原則

身為系統管理員，您可以使用撥出通話控制來限制組織中的使用者可進行的音訊會議類型和終端使用者 PSTN 通話類型。 

輸出呼叫控制可以在每位使用者的基礎上套用，並提供下列兩個控制項來單獨限制每個輸出呼叫類型。 根據預設，兩個控制項都設定為允許國際和國內呼出通話。 

|控制權|說明|控制選項|
|:-----|:-----|:-----|
|音訊會議 PSTN 通話|限制輸出類型 </br>內部允許的通話 </br>由使用者組織的會議。|國際和國內（預設）</br>家用</br>無|
|最終使用者 PSTN 通話|限制通話類型 </br>使用者可以進行的工作。|國際和國內（預設）</br>家用</br>無|

   > [!NOTE]
   > 如果撥打的電話號碼位於與會議召集人（在音訊會議中）設定的 Office 365，或使用者（在使用者 PSTN 呼叫的情況下），則會被視為國內通話。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音訊會議撥出通話 

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [**編輯**]。

3. 按一下 [**音訊會議**] 旁的 [**編輯**]。

4. 在 [**從會議撥出許可權**] 底下，選取您想要的撥出限制選項。

5. 按一下 [**儲存**]。 

![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

1.  在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議** > **使用者**]，然後從可用使用者清單中選取使用者。

2.  在 [動作] 窗格中，按一下 [**編輯**]。

3.  在 [**限制使用此使用者的會議進行撥**出] 底下，選取您想要的撥出限制選項。

    ![撥出選項的限制](media/restrictions-to-dial-outs.png)

5. 按一下 [**儲存**]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 PowerShell**

出站通話限制是由名為 OnlineDialOutPolicy 的單一原則所控制，每個策略都有一個限制屬性。 原則無法自訂，而是針對每個設定組合提供預先定義的原則實例。 

您可以使用 CSOnlineDialOutPolicy Cmdlet 來查看輸出通話原則，並使用授與 CSDialOutPolicy Cmdlet 將其指派給使用者。 （請注意，Grant Cmdlet 不會包含「線上」一詞，因為取得 Cmdlet 一樣。） 

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
