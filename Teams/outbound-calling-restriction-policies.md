---
title: 撥出通話限制 - 音訊會議& PSTN 通話
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.topic: article
ms.service: msteams
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 系統管理員可以控制使用者可以撥打的音訊會議和使用者 PSTN 通話類型。
ms.openlocfilehash: 67c138db8522ec6eee1f384e182f5c8d01ea40fd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641764"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>音訊會議和使用者 PSTN 通話的撥出通話限制原則

身為系統管理員，您可以使用撥出撥號控制項來限制音訊會議和使用者公用交換電話網路 (PSTN 的類型，) 組織中使用者可以撥打的通話。

撥出撥號控制項可以依個別使用者或租使用者為基礎套用，並提供下列兩個控制項，以獨立限制每種類型的撥出通話。 根據預設，這兩個控制項都設定為允許國際和國內撥出電話。

|控制|描述|控制選項|
|:-----|:-----|:-----|
|音訊會議 PSTN 通話|限制輸出類型 </br>允許從內部撥打的通話 </br>由使用者召集的會議。|任何目的地 (預設) </br>在與召集人相同的國家或地區 </br> 區域：僅[限國家或地區](audio-conferencing-zones.md) </br>不允許|
|使用者 PSTN 通話|限制通話類型 </br>可由使用者建立。|國際及國內 (預設) </br>國內</br>無|

若要瞭解哪些國家與地區被視為 A 區，請參閱 [音訊會議的國家和地區區域](audio-conferencing-zones.md)。

   > [!NOTE]
   > 如果撥打的號碼與會議召集人設定 Microsoft 365 或Office 365的所在國家/地區 (音訊會議) ，或使用者在使用者 PSTN 通話) 的情況下 (，則通話會視為國內電話。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>限制音訊會議撥出電話

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，選取 [ **使用者**]，然後從可用使用者清單中選取使用者的顯示名稱。

2. 接著移至 **[音訊會議]**，選取 [ **編輯]**。

3. 在 [ **從會議撥出**] 底下，選取您想要的撥出限制選項。

4. 選取 [儲存 **]**。

### <a name="using-powershell"></a>使用 PowerShell

撥出電話限制是由單一稱為 OnlineDialOutPolicy 的原則所控制，其每個原則都有一個限制屬性。 原則無法自訂，而是每個設定組合都有預先定義的原則實例。

您可以使用Get-CSOnlineDialOutPolicy Cmdlet 來檢視輸出通話原則，並使用下列命令進行設定。

**使用下列 Cmdlet 在每個使用者層級上設定** 原則。  (Grant Cmdlet 不包含 「Online」 這個字，就像 Get Cmdlet 一樣。) 

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**使用下列 Cmdlet 在租使用者層級設定** 原則。

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

未指派任何撥號原則之租使用者的所有使用者都會取得此原則。 其他使用者仍維持其目前的原則。

**使用下列 Cmdlet 檢查租使用者層級的目前原則**。

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

下表提供每個原則的概觀。

|PowerShell Cmdlet|描述|
|:-----|:-----|
|Identity='tag：DialoutCPCandPSTNInternational'    |    會議中的使用者可以撥出國際和國內號碼，而此使用者也可以撥打國際和國內號碼的傳出號碼。    |
|Identity='tag：DialoutCPCDomesticPSTNInternational'  |    會議中的使用者只能撥出國內號碼，而且此使用者可以撥打國際和國內號碼的撥出電話。    |
|    Identity='tag：DialoutCPCDisabledPSTNInternational'    |    會議中的使用者無法撥出。此使用者可以撥打國際和國內號碼的撥出電話。    |
|    Identity='tag：DialoutCPCInternationalPSTNDomestic'    |    會議中的使用者可以撥出國際和國內號碼，且此使用者只能撥打國內 PSTN 號碼的傳出號碼。    |
|    Identity='tag：DialoutCPCInternationalPSTNDisabled'    |    會議中的使用者可以撥出國際和國內號碼，而且除了緊急號碼以外，此使用者無法撥打任何 PSTN 號碼的傳出號碼。    |
|    Identity='tag：DialoutCPCandPSTNDomestic'    |    會議中的使用者只能撥出國內號碼，且此使用者只能撥打國內 PSTN 號碼的傳出號碼。    |
|    Identity='tag：DialoutCPCDomesticPSTNDisabled'    |    會議中的使用者只能撥出國內號碼，而且除了緊急號碼以外，此使用者無法撥打任何 PSTN 號碼的撥出電話。    |
|    Identity='tag：DialoutCPCDisabledPSTNDomestic'    |    會議中的使用者無法撥出，且此使用者只能撥打國內 PSTN 號碼的撥出電話。    |
|    Identity='tag：DialoutCPCandPSTNDisabled'    |    會議中的使用者無法撥出，而且此使用者除了緊急號碼外，無法撥打任何 PSTN 號碼的撥出電話。    |
|    Identity='tag：DialoutCPCZoneAPSTNInternational'    |    會議中的使用者只能撥出到 [A 區國家與地區](audio-conferencing-zones.md)，且此使用者可以撥打國際和國內號碼的撥出電話。    |
|    Identity='tag：DialoutCPCZoneAPSTNDomestic'    |    會議中的使用者只能撥出到 [A 區國家與地區](audio-conferencing-zones.md)，且此使用者只能撥打國內 PSTN 號碼的撥出電話。    |
|    Identity='tag：DialoutCPCZoneAPSTNDisabled'    |    會議中的使用者只能撥出到 [A 區國家與地區](audio-conferencing-zones.md)，而且此使用者除了緊急號碼以外，無法撥打任何 PSTN 號碼的撥出電話。    |
