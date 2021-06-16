---
title: 在 Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 瞭解如何管理會議的網路研討會Teams策略。
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926745"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>在 Microsoft Teams

本文將協助您將組織設定為主持網路研討會。

## <a name="what-are-webinars"></a>什麼是網路研討會？

網路研討會是一種結構化會議，簡報者和參與者都有明確角色，通常用於訓練目的或銷售與行銷潛在客戶產生案例。

在貴組織中設定網路研討會之後，您的使用者可以排程網路研討會，並開啟註冊給出席者。 與包含許多討論和工作分派的傳統會議不同，網路研討會適用于互動式簡報，並提供工具供出席者分析。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>允許使用者使用 PowerShell 排程網路研討會

您可以在 **Set-CsTeamsMeetingPolicy** Cmdlet Windows PowerShell 中使用以下屬性來設定 Teams。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

請參閱 [Set-CsTeamsMeetingPolicy，](/powershell/module/skype/set-csteamsmeetingpolicy) 以在 Cmdlet 上獲得詳細資訊。

> [!NOTE]
> 執行這些 Cmdlet 之前，您必須連接到 PowerShell Microsoft Teams。 詳細資訊，請參閱使用[PowerShell Teams管理Microsoft Teams資料](/microsoftteams/teams-powershell-managing-teams)。

### <a name="allow-users-to-schedule-webinars"></a>允許使用者排程網路研討會

您可以只將註冊限制為貴組織的使用者，或將註冊開放給租使用者內外的每個人。 根據預設 **，WhoCanRegister** 會啟用並設定為 **所有人**。 如果您想要關閉會議註冊，請設定 **AllowMeetingRegistration** 為 **False**。

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** 必須設為 **True，AllowMeetingRegistration** 可以工作。 此外，Microsoft 清單必須設定在 SharePoint。 若要深入瞭解，請參閱 Microsoft [清單的控制項設定](/sharepoint/control-lists)。

1. 開啟會議註冊

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 開啟私人會議排程

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. 設定誰可以註冊網路研討會

**只允許 *貴* 組織的使用者註冊網路研討會**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**若要允許任何人 ，包括匿名使用者，註冊網路研討會，請執行：**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 如果在會議設定中關閉匿名加入，匿名使用者無法加入網路研討會。 若要深入瞭解並啟用此設定[，請參閱會議](meeting-settings-in-teams.md)Teams。

### <a name="collect-meeting-attendance"></a>收集會議出席人數

如果您希望召集人分析誰註冊並參加網路研討會，您必須開啟 **AllowEngagementReport** 政策。 若要這麼做，請執行 PowerShell 中的下列命令。

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>設定網路研討會設定

啟用網路研討會環境之後，就不需要進一步系統管理員管理。 該政策會控制網路研討會召集人會顯示哪些選項。

## <a name="related-topics"></a>相關主題

- [會議Teams - 一般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 檔](/powershell/module/skype/set-csteamsmeetingpolicy)
