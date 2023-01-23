---
title: " (IT 系統管理員管理 Teams 會議的匿名參與者存取權) "
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 適用于 IT 專業人員 - 瞭解 Microsoft Teams 中匿名會議參與的運作方式。
ms.openlocfilehash: fe4dbec2bc606838bd5cafbaec5ef9d9ecdd8a88
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948683"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a> (IT 系統管理員管理 Teams 會議的匿名參與者存取權) 

貴組織主持會議中的匿名參與者是無法驗證身分識別的人員。 這可能包括：

- 人員未使用公司或學校帳戶登入 Teams 的人員 
- 來自非信任組織的人員 (在[外部存取](manage-external-access.md)) 和您信任但不信任貴組織的組織中設定。

匿名會議加入是由組織層級設定和使用者層級原則所控制。 若要讓匿名會議加入運作：
- **匿名使用者可以加入會議** Teams 會議設定 (必須開啟組織層級) 。
- 會議召集人必須獲派 Teams 會議原則，其中已開啟 **[讓匿名人員加入會議** ] 控制項。

匿名加入預設會針對組織和預設的全域會議原則開啟。

請注意，如果啟用匿名加入，大廳原則會影響匿名參與者加入會議的程度。 如需詳細資料，請參閱 [控制誰可以略過 Microsoft Teams 中的會議大廳](who-can-bypass-meeting-lobby.md)。

#### <a name="meetings-with-trusted-organizations"></a>與信任的組織開會

當您為外部會議和聊天設定信任的組織時，如果兩個組織都未正確設定外部存取設定，這些組織的會議出席者可能會被視為匿名。 如需詳細資料，請參閱 [受信任的組織，以進行外部會議和聊天](manage-external-access.md)。

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>管理組織的匿名會議加入

組織中的任何人都必須開啟組織層級匿名會議加入設定，才能建立允許匿名參與者的會議。

> [!Important]
> 匿名 **參與者可以加入整個組織的會議** 設定，日後將會被移除。 我們建議您將此設定保持為開 **啟** ，並使用 [ **允許匿名人員加入會議** 使用者層級會議原則] 控制項，改為允許或防止匿名會議加入。

為組織設定匿名會議加入
1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。

1. 在左側導覽中，移至 [會議]  >  [會議設定]。

1. 在 [ **參與者**] 底下，將 **[匿名參與者可以加入會議** ] **設定為 [** 開 (建議) ] 或 [ **關閉]**。

    ![系統管理中心中會議的參與者設定螢幕擷取畫面。](media/meeting-settings-participants.png "Microsoft Teams 系統管理中心中 Teams 會議的參與者設定螢幕擷取畫面")

1. 選取 [儲存 **]**。

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>管理哪些會議召集人可以允許匿名會議加入

您可以控制哪些使用者或群組可以主持包含匿名參與者的會議。 若要這麼做，請將已開啟匿名會議加入的會議原則指派給需要與匿名參與者主持會議的每個會議召集人。

為特定會議召集人設定匿名會議加入
1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。

1. 在左側導覽中，移至 **[會議**  >  **會議原則]**。

1. 選取您要修改的原則。

1. 將 **[讓匿名人員加入會議** ] 設為 [ **開啟]**。

1. 選取 [儲存 **]**。

對會議原則所做的變更可能需要 24 小時才會生效。

## <a name="configure-anonymous-meeting-join-using-powershell"></a>使用 PowerShell 設定匿名會議加入

您可以使用下列方法來控制匿名參與者是否可以加入會議：

- `-DisableAnonymousJoin`設定組織層級設定的[Set-CsTeamsMeetingConfiguration](/powershell/module/skype/set-csteamsmeetingconfiguration)中的參數。  (建議您將此設定保留為 False，並使用 Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting 在使用者或群組層級控制匿名加入。) 
- `-AllowAnonymousUsersToJoinMeeting` [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)中用來設定使用者層級會議原則的參數

若要允許匿名參與者加入會議，您必須設定這兩者，以設定下列值以允許匿名加入：

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin` 設定為 **[$false**
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting` 設定為 **$true** 的相關會議召集人

## <a name="block-anonymous-join-for-specific-client-types"></a>針對特定用戶端類型封鎖匿名加入

允許匿名參與者加入會議時，他們可以使用 Teams 用戶端或使用Azure 通訊服務建置的自訂客戶[端](/azure/communication-services/)。 

系統管理員可以使用 `-BlockedAnonymousJoinClientTypes` [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes)中的參數來封鎖這些用戶端類型。

## <a name="anonymous-participants-meeting-experience"></a>匿名參與者的會議體驗

匿名參與者的功能與其他會議參與者不同。 例如，匿名參與者：

- 會議前後沒有會議聊天的存取權
- 在 Microsoft 365 中無法存取設定檔卡 (設定檔卡片 - Microsoft 支援服務) 

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>匿名參與者如何與會議中的應用程式互動

根據預設，允許匿名參與者在會議中與應用程式互動的設定已啟用。

設定匿名會議參與者的應用程式存取權

1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。

1. 在左側導覽中，移至 [會議]  >  [會議設定]。

1. 在 [**參與者**] 底下，將 **[匿名參與者可在會議中與應用程式互動**] 設為 [**開****啟] 或 [關閉]**。

您也可以使用 PowerShell 來控制此設定 `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers` 。

匿名參與者繼承全全組織 (預設) Teams 應用程式許可權原則。 匿名參與者可以在 Teams 會議中與應用程式互動，只要該原則中已啟用應用程式，**匿名參與者就可以在會議中與應用程式互動****。**

請注意，匿名參與者只能與會議中已提供的應用程式互動，而且無法取得和/或管理這些應用程式。

## <a name="related-topics"></a>相關主題

[在沒有 Teams 帳戶的情況下加入會議](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[使用 Microsoft Teams 系統管理中心來設定全組織原則。](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[外部參與者會收到「登入 Teams 以加入，或連絡會議召集人」](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[在 Teams 中指派原則 – 快速入門](policy-assignment-overview.md)