---
title: 在 Microsoft Teams 中設定網路研討會
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 瞭解如何管理網路研討會Teams會議。
ms.openlocfilehash: 5536a6c03df15be349edea7d980932b5fc0173ab
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224000"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中設定網路研討會

本文將協助您將組織設定為主持網路研討會。

## <a name="what-are-webinars"></a>什麼是網路研討會？

網路研討會是一種結構化會議，簡報者和參與者都有明確的角色，通常用於訓練目的或銷售和行銷潛在客戶產生案例。

在貴組織中設定網路研討會之後，您的使用者可以排程網路研討會，並開啟註冊給出席者。 與包含許多討論和工作分派的傳統會議不同，網路研討會適用于互動式簡報，並提供用於出席者分析的工具。

> [!IMPORTANT]
> 若要讓使用者設定網路研討會Microsoft 清單，您必須在 SharePoint中設定個人清單。 若要深入瞭解，請參閱[控制項設定Microsoft 清單。](/sharepoint/control-lists)

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>允許使用者在系統管理中心Teams網路研討會

您可以使用系統管理Teams中心為貴組織設定網路研討會。 您可以在會議會議政策下的 Teams系統管理中心找到設定網路研討會  >  **的政策**。

### <a name="meeting-registration"></a>會議註冊

如果您開啟此功能，使用者可以排程網路研討會。 根據預設，這會開啟。 如果您想要關閉會議註冊，請設定此策略為 **關閉**。

> [!IMPORTANT]
> **私人會議排程** 必須已上，會議註冊作業。 根據預設，此政策會于系統管理中心Teams開啟。 對於教育租使用者的學生，此政策預設為關閉。 若要瞭解如何為學生啟用私人會議排程功能，請參閱Teams 教育版[策略套件](policy-packages-edu.md)。

### <a name="who-can-register"></a>神秘註冊

如果您選取了 **每個人都**，所有使用者 ，包括匿名使用者，都可以註冊並參加網路研討會。 如果您選取組織的 **每個人都**，則只有貴組織的使用者可以註冊網路研討會。 如果會議註冊已關閉，則此選項將不可用，而且沒有人可以註冊網路研討會。

> [!NOTE]
> 您可以 **註冊神秘預設值** 為教育租使用者 **中的組織中** 所有人。 詳細資訊，請參閱Teams 教育版[精靈](easy-policy-setup-edu.md)。

### <a name="engagement-report"></a>互動報告

啟用時，召集人可以看到註冊及參加他們設定之網路研討會者的報告。 此策略預設為啟用。 如要詳細資訊，請參閱 Teams [- Teams中的會議政策](meeting-policies-in-teams-general.md#engagement-report)。 有關使用者經驗的資訊，請參閱 [查看及下載會議出席報告](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>允許使用者使用 PowerShell 排程網路研討會

您可以在 **Set-CsTeamsMeetingPolicy** Cmdlet 的 Windows PowerShell 中使用以下屬性來設定 Teams。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

請參閱 [Set-CsTeamsMeetingPolicy，](/powershell/module/skype/set-csteamsmeetingpolicy) 以進一瞭解更多關於 Cmdlet 的資訊。

> [!NOTE]
> 執行這些 Cmdlet 之前，您必須連接到 PowerShell Microsoft Teams。 詳細資訊，請參閱使用[PowerShell Teams管理Microsoft Teams資料](/microsoftteams/teams-powershell-managing-teams)。

### <a name="allow-users-to-schedule-webinars"></a>允許使用者排程網路研討會

您可以只將註冊限制為貴組織的使用者，或將註冊開放給租使用者內外的每個人。 根據預設 **，WhoCanRegister** 會啟用，並設定為全域 (**全組織的預設)** 規則。 如果您想要關閉會議註冊，請設定 **AllowMeetingRegistration** 為 **False**。

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** 必須設為 **True，AllowMeetingRegistration** 可以工作。

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

**AllowEngagementReport** 參數可讓您查看誰註冊和參加網路研討會。 此策略預設為開啟。 若要關閉，請于 PowerShell 中執行下列命令：

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>設定網路研討會設定

啟用網路研討會環境之後，就不需要進一步系統管理員管理。 該政策會控制網路研討會召集人顯示的選項。

## <a name="related-topics"></a>相關主題

- [會議Teams - 一般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 檔](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams 教育版策略精靈](easy-policy-setup-edu.md)
