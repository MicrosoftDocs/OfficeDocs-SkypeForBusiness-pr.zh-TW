---
title: 外線通話限制 - PSTN 通話&音訊會議
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 系統管理員可以控制使用者可撥打的音訊會議和使用者 PSTN 通話類型。
ms.openlocfilehash: 43fda0e088cc0b7c29bd270d20f0701f0391f8ce
ms.sourcegitcommit: 47f537a81659ec5ecb7dfdb57589fa133199ec57
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2021
ms.locfileid: "61066544"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音訊會議和使用者 PSTN 通話的撥出通話限制原則

做為系統管理員，您可以使用輸出通話控制項來限制貴組織中使用者可以撥打的音訊會議和使用者公用交換電話網路 (PSTN) 電話類型。

外發通話控制項可以依據每個使用者或租使用者來使用，並提供下列兩種控制項來獨立限制每種類型的外發通話。 根據預設，這兩個控制項都設定為允許國際和國內外發通話。

|控制|描述|控制項選項|
|:-----|:-----|:-----|
|音訊會議 PSTN 通話|限制外發類型 </br>內允許的通話 </br>使用者組織的會議。|任何目的地 (預設) </br>與召集人在同一個國家/地區 </br> [區域 A 國家/地區或區域](audio-conferencing-zones.md) </br>不允許|
|使用者 PSTN 通話|限制通話類型 </br>使用者可以進行。|國際和國內 (預設) </br>國內</br>無|

若要瞭解哪些國家和地區被視為區域 A，請參閱音訊會議的國家和地區 [區域](audio-conferencing-zones.md)。

   > [!NOTE]
   > 如果撥打的號碼位於會議 (的召集人已設定 Microsoft 365 或 Office 365 的同一個國家/地區，或使用者 () 如果是使用者 PSTN 通話) ，則電話會視為國內通話。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音訊會議輸出通話

**使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **選取使用者**，然後從可用使用者清單中選取使用者的顯示名稱。

3. 在音訊 **會議旁邊，選取****編輯**。

4. 在 **會議撥出下**，選取您想要的撥出限制選項。

5. 選取 [儲存 **]**。


**使用 PowerShell**

輸出通話限制是由稱為 OnlineDialOutPolicy 的單一策略控制，每個策略都有一個限制屬性。 無法自訂該策略，而是每個設定組合都有預先定義的策略實例。

您可以使用 Get-CSOnlineDialOutPolicy Cmdlet 來查看外寄通話政策，並使用下列命令進行設定。

**使用下列 Cmdlet** 將策略設定為每個使用者層級。  (Grant Cmdlet 不包含 「線上」一詞，就像 Get Cmdlet 一樣。) 

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**使用下列 Cmdlet 在租使用者層級設定策略**。

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

未指派任何撥出策略的租使用者所有使用者都會取得此策略。 其他使用者會維持目前的政策。

下表提供每個策略的概覽。

|PowerShell Cmdlet|描述|
|:-----|:-----|
|Identity='tag：DialoutCPCandPSTNInternational'    |    會議中的使用者可以撥出國際和國內號碼，而且這個使用者也可以撥打國際和國內號碼。    |
|Identity='tag：DialoutCPCDomesticPSTNInternational'  |    會議中的使用者只能撥出國內號碼，而此使用者可以撥打國際和國內號碼。    |
|    Identity='tag：DialoutCPCDisabledPSTNInternational'    |    會議中的使用者無法撥出。此使用者可以撥打國際和國內號碼。    |
|    Identity='tag：DialoutCPCInternationalPSTNDomestic'    |    會議中的使用者可以撥出國際和國內號碼，而且此使用者只能撥打國內 PSTN 號碼。    |
|    Identity='tag：DialoutCPCInternationalPSTNDisabled'    |    會議中的使用者可以撥出國際和國內號碼，而且除了緊急號碼之外，此使用者無法撥打任何外撥 PSTN 號碼。    |
|    Identity='tag：DialoutCPCandPSTNDomestic'    |    會議中的使用者只能撥出國內號碼，而且此使用者只能撥打國內 PSTN 號碼。    |
|    Identity='tag：DialoutCPCDomesticPSTNDisabled'    |    會議中的使用者只能撥出到國內號碼，而且除了緊急號碼之外，此使用者無法撥打任何撥出的 PSTN 號碼。    |
|    Identity='tag：DialoutCPCDisabledPSTNDomestic'    |    會議中的使用者無法撥出，而且此使用者只能撥打國內 PSTN 號碼。    |
|    Identity='tag：DialoutCPCandPSTNDisabled'    |    會議中的使用者無法撥出，而且除了緊急號碼之外，此使用者無法撥打任何外撥 PSTN 號碼。    |
|    Identity='tag：DialoutCPCZoneAPSTNInternational'    |    會議中的使用者只能撥出至 [區域 A](audio-conferencing-zones.md)國家/地區，而且此使用者可以撥打國際和國內號碼。    |
|    Identity='tag：DialoutCPCZoneAPSTNDomestic'    |    會議中的使用者只能撥出到 [區域 A](audio-conferencing-zones.md)國家/地區，而且此使用者只能撥打國內 PSTN 號碼。    |
|    Identity='tag：DialoutCPCZoneAPSTNDisabled'    |    會議中的使用者只能撥出到 [區域 A](audio-conferencing-zones.md)國家/地區，而且除了緊急號碼之外，此使用者無法撥打任何 PSTN 號碼。    |
