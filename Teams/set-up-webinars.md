---
title: 在 Microsoft Teams 中設定網路研討會
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 瞭解如何管理Teams會議的網路研討會原則。
ms.openlocfilehash: 2cf3af39b64506fc8802eafd1e2c45f35b7a4d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646242"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中設定網路研討會

本文將協助您將貴組織設定為主控網路研討會。

## <a name="what-are-webinars"></a>什麼是網路研討會？

網路研討會是結構化會議，簡報者和參與者具有清楚的角色，通常用於訓練目的或銷售和行銷潛在客戶產生案例。

在貴組織中設定網路研討會之後，您的使用者可以排程網路研討會，並開啟註冊給出席者。 不同于包含許多討論和工作指派的傳統會議，網路研討會是用於互動式簡報，並提供工具供出席者分析。

> [!IMPORTANT]
> 若要讓使用者設定網路研討會，Microsoft 清單必須在SharePoint中設定，方法是建立個人清單。 若要深入瞭解，請參閱[控制Microsoft 清單設定](/sharepoint/control-lists)。

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>允許使用者在Teams系統管理中心排程網路研討會

您可以使用Teams系統管理中心為貴組織設定網路研討會。 您可以在 [**會議**  >  會議] 原則下Teams系統管理中心找到設定網路研討會 **的原則**。

### <a name="meeting-registration"></a>會議註冊

如果您開啟此設定，使用者可以排程網路研討會。 預設會開啟此功能。 如果您想要關閉會議註冊，請將此原則設為 **[關閉]**。

> [!IMPORTANT]
> **私人會議排程** 必須開啟，會議註冊才能運作。 根據預設，此原則會在系統管理中心Teams開啟。 對於教育租使用者中的學生，此原則預設為關閉。 如需如何為學生啟用私人會議排程的詳細資訊，請[參閱Teams 教育版原則和原則套件](policy-packages-edu.md)。

### <a name="who-can-register"></a>神秘可以註冊

如果您選取 [ **所有人**]，所有使用者，包括匿名使用者，都可以註冊並參加網路研討會。 如果您選取 **組織中的 [所有人**]，則只有您組織中的使用者可以註冊網路研討會。 如果關閉會議註冊，將無法使用此選項，而且沒有人可以註冊網路研討會。

> [!NOTE]
> 神秘 **可以註冊** 的預設值是教育租使用者 **中組織中的每個人**。 如需詳細資訊，請[參閱Teams 教育版原則精靈]](easy-policy-setup-edu.md)。

### <a name="engagement-report"></a>互動報告

開啟此設定時，召集人會看到註冊和參與其所設定網路研討會的人員報告。 此原則預設為開啟。 如需詳細資訊，請參閱[Teams - 互動報告中的會議原則](meeting-policies-in-teams-general.md#engagement-report)。 如需使用者體驗的相關資訊，請參 [閱檢視及下載會議出席報告](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>允許使用者使用 PowerShell 排程網路研討會

您可以在 **Windows PowerShell Set-CsTeamsMeetingPolicy** Cmdlet 中使用下列屬性來設定 Teams 中的網路研討會。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

如需 Cmdlet 的詳細資訊，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 。

> [!NOTE]
> 您必須先連線至 Microsoft Teams PowerShell，才能執行這些 Cmdlet。 如需詳細資訊，請參閱[使用 Microsoft Teams PowerShell 管理Teams](/microsoftteams/teams-powershell-managing-teams)。

### <a name="allow-users-to-schedule-webinars"></a>允許使用者排程網路研討會

您可以將註冊限制為僅限貴組織中的使用者，或向租使用者內外的所有人開放註冊。 根據預設，**WhoCanRegister** 會啟用並設定為全 **局 (組織預設)** 原則的 [**所有人**]。 如果您想要關閉會議註冊，請將 **AllowMeetingRegistration** 設為 **False**。

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** 必須設為 **True** ， **AllowMeetingRegistration** 才能運作。

1. 開啟會議註冊

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 開啟私人會議排程

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. 設定誰可以註冊網路研討會

***僅* 允許貴組織中的使用者註冊網路研討會**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**若要允許任何人，包括匿名使用者，註冊網路研討會，請執行：**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 如果會議設定中關閉匿名加入，匿名使用者就無法加入網路研討會。 若要深入瞭解並啟用此設定，請參閱[Teams 中的會議設定](meeting-settings-in-teams.md)。

### <a name="collect-meeting-attendance"></a>收集會議出席

**AllowEngagementReport** 參數可讓您查看已註冊和參與網路研討會的人員。 此原則預設為開啟。 若要將它關閉，請在 PowerShell 中執行下列命令：

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>設定網路研討會設定

啟用網路研討會的環境之後，不需要進一步的系統管理。 原則會控制網路研討會召集人要顯示哪些選項。

## <a name="related-topics"></a>相關主題

- [Teams中的會議原則 - 一般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 檔](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams 教育版原則精靈](easy-policy-setup-edu.md)
