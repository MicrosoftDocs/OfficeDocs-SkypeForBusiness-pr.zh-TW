---
title: 設定網路研討會
ms.author: mabond
author: mkbond007
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
- highpri
description: 瞭解如何在 Teams 中管理網路研討會和會議註冊原則。
ms.openlocfilehash: 097f4c385261ba1aea96990751d208b99d4d8b93
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950430"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中設定網路研討會

> [!NOTE]
> 本文將說明網路研討會中處於預覽階段且需要Teams 進階版授權的一些功能。

Microsoft 現在提供新的網路研討會體驗;本文將說明如何更新您的設定以使用這些功能。

如果您打算使用網路研討會，建議您使用新的網路研討會體驗。

會議註冊包括基本網路研討會功能、需要註冊會議的功能，以及出席報告。 藉由啟用新的網路研討會體驗，您可以使用會議註冊和許多新的網路研討會功能，例如：

- 網路研討會的專用活動和註冊頁面
- 共同召集人
- 活動頁面上的簡報者簡歷
- 註冊狀態概觀與管理

在 [開始使用 Teams 網路研討會](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3)中，深入瞭解可供使用者使用的新功能。

如果貴組織已啟用會議註冊，所有新建立的網路研討會都會有新的體驗。 先前排程的網路研討會將使用先前的網路研討會體驗。 新的體驗使用 TeamsEventsPolicy。 如果您已關閉網路研討會，這些網路研討會將會在新體驗推出時維持關閉狀態。

目前，基本網路研討會體驗是由使用 Teams 會議原則 (Set-CsTeamsMeetingPolicy) 的會議註冊所控制。 未來會議註冊設定將無法控制網路研討會;網路研討會正在轉換到由 Teams 事件原則控制 (Set-CsTeamsEventsPolicy) 。

新的網路研討會體驗已在 PowerShell 中設定。 請參閱 [如何設定新的網路研討會體驗](#set-up-new-webinar-experience)的範例。

如需會議、網路研討會和即時事件之間差異的詳細資訊，請參閱 [會議、網路研討會和即時活動](quick-start-meetings-live-events.md)。

> [!NOTE]
> 對於內部部署使用者，新的網路研討會體驗尚未提供。
>
> 新的網路研討會體驗不適用於 Microsoft 365 GCC、Microsoft 365 GCC High 或 Microsoft 365 DoD。 現有的網路研討會體驗不適用於 Microsoft 365 GCC High 或 Microsoft 365 DoD。

> [!IMPORTANT]
> 若要讓使用者設定網路研討會，您必須在 SharePoint 中設定Microsoft 清單，方法是針對電子檔探索目的建立個人清單。 若要深入瞭解，請參閱[控制Microsoft 清單設定](/sharepoint/control-lists)。

## <a name="set-up-new-webinar-experience"></a>設定新的網路研討會體驗

您必須使用 PowerShell 來為組織設定新的網路研討會體驗。 目前還無法在 Teams 系統管理中心中設定新的網路研討會體驗。

會議註冊必須已開啟，才能使用新的網路研討會體驗。

### <a name="configure-the-new-webinar-experience-with-powershell"></a>使用 PowerShell 設定新的網路研討會體驗

若要設定新的網路研討會體驗，請在 Windows PowerShell **Set-CsTeamsEventsPolicy** Cmdlet 中使用下列屬性。

|參數|預設設定|描述|
|---------|-----------|---------------|
|AllowWebinars|Enabled|此設定會決定使用者是否可以建立網路研討會。|
|EventAccessType|任何人|此設定會決定哪些使用者可以存取事件註冊頁面或即時網頁來註冊，以及允許哪些使用者類型加入會話 () 。|

您必須先連線到 Microsoft Teams PowerShell，才能執行這些 Cmdlet。 如需詳細資訊，請參閱 [使用 Microsoft Teams PowerShell 管理 Teams](/microsoftteams/teams-powershell-managing-teams)。

1. 開啟會議註冊。

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. 啟用新的網路研討會體驗。

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. 設定誰可以註冊網路研討會和會議。

    - **允許 **_only_* _ 貴組織中的使用者註冊網路研討會，meetings_*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **允許包括匿名使用者在內的所有人註冊網路研討會和會議**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> 如果會議設定中已關閉 **匿名使用者可以加入會議****的** 功能，匿名使用者就無法加入網路研討會。 若要深入瞭解並啟用此設定，請參閱 [Teams 中的會議設定](meeting-settings-in-teams.md)。

## <a name="configure-meeting-registration"></a>設定會議註冊

如果您想要使用網路研討會，則必須開啟會議註冊。

您可以使用 [**會議**  >  **會議** 原則] 下的 Teams 系統管理中心來設定會議註冊和網路研討會。

### <a name="meeting-registration"></a>會議註冊

如果您開啟 **會議註冊**，貴組織中的使用者可以排程需要註冊的網路研討會和會議。 此設定預設會開啟。 如果您想要關閉會議註冊和網路研討會，請將此原則設為 **[關閉]**。

**私人會議排程** 必須開啟，會議註冊才能運作。 深入瞭解 [私人會議排程](meeting-policies-in-teams-general.md)。

對於教育租使用者中的學生，此原則預設為關閉。 如需如何為學生啟用私人會議排程的詳細資訊，請[參閱Teams 教育版原則和原則套件](policy-packages-edu.md)。

#### <a name="who-can-register"></a>誰可以註冊

> [!NOTE]
> 這項原則不適用於新的網路研討會體驗。 若要設定誰可以註冊新的網路研討會體驗，請使用 `Set-CsTeamsEventsPolicy -EventAccessType` ，如在 [設定 PowerShell 的新網路研討會體驗](#configure-the-new-webinar-experience-with-powershell)中所示。

此原則會控制哪些使用者只能使用會議註冊來註冊及參加網路研討會。 此原則有兩個選項，只有在會議 **註冊** 已開啟時才能使用。 根據預設， **[誰可以註冊** ] 設定為 [ **所有人]**。

如果您選取 [ **所有人**]，所有使用者，包括匿名使用者，都可以註冊並參加網路研討會。 如果您選取 **組織中的 [所有人**]，則只有您組織中的使用者可以註冊並參加網路研討會。 如果關閉會議註冊，[ **誰可以註冊** ] 設定將無法使用，而且沒有人可以註冊網路研討會。

Who **can register** 的預設值是教育租使用者中 **組織中的每個人** 。 如需詳細資訊，請[參閱Teams 教育版原則精靈]](easy-policy-setup-edu.md)。

## <a name="collect-webinar-and-meeting-registration-attendance"></a>收集網路研討會和會議註冊出席

您可以使用 [**會議會議**  >  原則] 下的 Teams 系統管理中心來開啟 **[參與] 報告**。****

開啟此設定時，召集人會看到誰註冊並參與他們所設定的網路研討會或會議的報告。 此原則預設為開啟。 如需詳細資訊，請參閱 [Teams 中的會議原則 - 參與報告](meeting-policies-in-teams-general.md#engagement-report)。 如需使用者體驗的相關資訊，請參 [閱檢視及下載會議出席報告](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310)。

在 PowerShell 中， **AllowEngagementReport** 參數可用來開啟此功能。 此原則預設為開啟。 若要將它關閉，請在 PowerShell 中執行下列命令：

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

如需 Cmdlet 的詳細資訊，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 。

## <a name="turn-off-webinars"></a>關閉網路研討會

您可以使用 PowerShell 關閉網路研討會。 這會關閉新的網路研討會體驗，以及只有會議註冊的網路研討會。

使用下列 PowerShell 腳本來關閉網路研討會：

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>相關主題

- [Teams 中的會議原則 - 一般](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
