---
title: 控制誰可以在 Teams 中略過會議大廳Microsoft
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
description: 瞭解如何在 Teams 中使用會議大廳Microsoft只允許特定會議參與者直接加入會議。
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392713"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>控制誰可以在 Teams 中略過會議大廳Microsoft

Teams 會議大廳可防止特定類型的會議參與者加入會議，直到會議召集人、共同召集人或簡報者准後才能加入會議。 當參與者前往大廳時，召集人、共同召集人和簡報者都會收到通知，並可以選擇不准許他們加入會議。

您可以使用 Teams 系統管理中心的大廳設定來建立預設值，讓哪些類型的會議參與者可以略過大廳，哪些參與者必須在那裡等候，直到獲准參加會議為止。 您可以控制下列類型的參與者與大廳互動的方式：

- 會議召集人和共同召集人
- 組織中的人員
- 來賓
- 在信任的組織中人員
- 匿名參與者

除非參與者是匿名，否則Microsoft 365 可驗證加入會議之人員的身分識別。 無法驗證匿名參與者。

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>與組織外部人員開會的先決條件

Teams 中有一些設定可以控制組織外部的人員是否可以與 Teams 互動。 組織外部人員必須啟用下列設定，才能加入會議：

- [Teams 中的來賓存取](guest-access.md) 權必須啟用，來賓才能加入會議。
- 外部存[取](manage-external-access.md)必須啟用，才能讓信任組織中的人員加入會議。 您組織與外部組織之間的相互信任必須設定，且貴組織中的會議召集人以及外部組織的任何參與者都必須啟用外部存取。
- **匿名使用者可以 (** 組織層級) 加入會議設定，而為建立會議) 召集人的會議原則 (必須為 [**開** 啟]，匿名參與者才能加入會議。

如果任一設定已關閉，無論大廳設定為何，這類外部參與者都無法加入會議。

## <a name="overview-of-lobby-settings-and-policies"></a>大廳設定與原則概觀

下表顯示影響會議參與者與大廳互動方式的 Teams 會議原則。

|設定|描述|
|:------|:----------|
|**匿名使用者和撥入式來電者可以開始會議**|這是每個召集人的原則，可允許無前導參閱會議。 此設定會控制匿名參與者和撥入使用者是否可以在未通過驗證參與者出席的情況下加入會議。 只有當 **[誰可以略過大廳** ] 設定為 [ **所有人]** 時，才適用此設定。 如果 **匿名使用者可以加入會議** 組織或會議設定為 **[關閉]**，則此設定僅適用于撥入式來電者。 根據預設，此設定會關閉，以防止匿名使用者可能濫用您的會議連結。 <br><br> **關閉** 時，匿名參與者和撥入使用者會在大廳等候，直到經過驗證的參與者 (包括電話撥入式召集人) 加入會議，此時系統會自動允許他們加入。 會議開始後，匿名參與者和撥入使用者會自動加入通話，即使召集人離職。 <br><br> 如果此設定為 **[開啟**]，匿名和撥入式參與者可以啟動並加入會議，而不需要驗證的參與者出席。|
|**撥入人員可以略過大廳**|這是每一召集人原則。 此設定會控制使用電話撥入的人員是否直接加入會議，或是在大廳等候。 當此設定 **關閉** 時，撥入式使用者會在大廳等候，直到召集人、共同召集人或簡報者加入會議並允許他們加入。 當此設定 **為開啟** 時，撥入式使用者將自動加入會議，而不會進入大廳。  (如果 **匿名使用者和撥入式來電者可以召開會議** 已 **關閉**，他們會在大廳等候，直到會議開始為止。) |
|**誰可以略過大廳**|這是每一召集人原則。 此設定會控制除了透過電話撥入的參與者外，哪些類型的參與者 () 直接加入會議，以及哪些類型的參與者在大廳等候，直到召集人、共同召集人或簡報者准後才能加入。|

下表顯示 [ **誰可以略過大廳** 原則] 的每個選項如何影響每 *種類型的會議參與者*。

|原則值：|任何人|組織中的人員、信任的組織和來賓|組織中的人員和來賓|組織中的人員|僅限受邀者|僅限召集人和共同召集人|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*召集人和共同召集人*|旁路|旁路|旁路|旁路|旁路|旁路|
|*組織中的人員*|旁路|旁路|旁路|旁路|人員傳送或轉寄邀請的人員將會略過;其他人則可在大廳等候|大堂|
|*來賓*|旁路|旁路|旁路|大堂|人員傳送或轉寄邀請的人員將會略過;其他人則可在大廳等候|大堂|
|*在信任的組織中人員*|旁路|旁路|大堂|大堂|人員傳送或轉寄邀請的人員將會略過;其他人則可在大廳等候|大堂|
|*匿名參與者*|旁路|大堂|大堂|大堂|大堂|大堂|

**只有受邀的人員** 只會套用至已傳送邀請或轉寄邀請給之驗證參與者。 新增為通訊群組一部分的使用者將會在大廳等候。

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>在貴組織主持的會議中選擇誰可以略過大廳

您可以在 Teams 系統管理中心設定上述設定和原則。 請參閱下列各節，以取得針對不同情況選擇哪一個設定的指導方針。 如需會議原則運作方式的相關資訊，請參閱[管理 Microsoft Teams 中的會議原則](/microsoftteams/meeting-policies-overview)。

> [!Important]
> 會議召集人可以變更您為撥入人員選擇的預設值，**可以略過大廳**，而 **[誰可以略過大廳** 設定]。 如果您需要針對特定值強制執行這些設定，您可以使用會議範本或敏感度標籤 (需要使用 Teams 進階版) 。  如需詳細資訊，請參閱針對[敏感性會議設定Microsoft Teams 會議大廳](configure-lobby-sensitive-meetings.md)。

設定會議加入和大廳原則
1. 在 Teams 系統管理中心中，展開 **[會議** ]，然後選取 **[會議原則]**。
1. 選取您要更新的原則。
1. 在 [ **參與者&來賓** ] 區段中，更新您要變更的設定：
   - **讓匿名人員加入會議**
   - **讓匿名人員開始會議**
   - **自動准許人員** (誰可以略過大廳) 
   - **撥入式使用者可以略過大廳**

    ![螢幕擷取畫面顯示 Teams 系統管理中心的會議加入和大廳原則。](media/meeting-join-and-lobby-tac-settings.png)
1. 選取 [儲存 **]**。

請注意，變更最多可能需要 24 小時才會生效。

如果您想要允許匿名會議存取，請確定匿名 **使用者可以加入會議** 的設定也已開啟。

設定匿名會議加入的全組織會議設定
1. 在 Teams 系統管理中心中，展開 **[會議** ]，然後選取 [ **會議設定]**。
1. 在 [**參與者]** 區段中，將 **[匿名使用者可以加入會議]** 設為 [**開****啟] 或 [關閉]**。
    ![螢幕擷取畫面顯示 Teams 系統管理中心的會議加入和大廳設定。](media/anonymous-users-can-join-meetings-org-setting.png)
1. 選取 [儲存 **]**。

## <a name="control-access-to-meetings-by-anonymous-participants"></a>控制匿名參與者對會議的存取權

匿名參與者是匿名的，因為他們沒有登入可經由 Microsoft 365 驗證的帳戶。 這可能包括：

- 人員未使用公司或學校帳戶登入 Microsoft 365 的人員 
-  (外部存[取](manage-external-access.md)) 中設定的非信任組織人員。
- 人員來自您信任但不信任貴組織的組織

如果您想要防止匿名參與者完全加入會議，您可以關閉 **匿名使用者可以加入** 全組織的會議設定。 您也可以使用 **匿名使用者可以加入** 會議原則，針對特定會議召集人停用匿名加入。

如果您希望匿名加入的人員在大廳等候，您可以將 [ **誰可以略過大廳** 會議原則] 設定為 [ **所有人**] 以外的任何設定。  (此設定不會影響透過電話撥入的人員。) 

根據預設， **匿名使用者和撥入式來電者可以啟動會議** 原則為 **[關閉]**。 這表示，如果經過驗證的參與者尚未開始會議，匿名參與者和透過電話撥入的人員一律會在大廳等候。 當您想要允許匿名參與者和透過電話撥入的人員開始會議時，雖然您可以開啟此設定，但我們建議您將它關閉。  設定開啟時，擁有未驗證帳戶的人員可以召開會議，包括使用會議連結在未排程的時間召開會議。

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>控制透過電話撥入的人員存取會議

根據預設，**撥入人員可以略過大廳** 原則為 **[關閉**]，但會議召集人在設定會議時可以變更此設定。 您可以藉由更新人員撥入來變更預設值，**可以略過大廳** 原則，也可以使用會議範本強制執行特定值。

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>控制來賓和受信任組織人員的會議存取權

組織外部有兩種類型的人員可以以通過驗證的參與者身分加入會議：

- 來賓 - 在貴組織中擁有 [Azure Active Directory (Azure AD) B2B 共同作業帳戶](/azure/active-directory/external-identities/what-is-b2b) 的人員
- 外部存取使用者 - 在 Teams 外部存取中定義之受信任組織中擁有 Azure AD 帳戶[的](manage-external-access.md)人員

如果您希望組織外部所有經過驗證的會議參與者在大廳等候，您可以將 [誰可以略過大廳原則] 設定 **為在我的組織中人員**，或者只要來賓不是召集人或共同召集人) ，**則只有召集人和共同召集** 人 (。 如果您只想要讓信任組織 (外部存取使用者) 在大廳等候，您可以選擇 **組織中的人員和來賓**。

## <a name="control-access-to-meetings-by-people-without-invitations"></a>控制沒有邀請之人員的會議存取權

如果您只想允許有邀請的人員直接加入會議，並讓所有其他參與者在大廳等候， **請將 [誰可以略過大廳** ] 設定 **為 [只有受邀的人員]**。 不包含透過通訊群組清單邀請的 (人員。) 

**[只有受邀的人員**] 設定會包含已驗證的參與者，邀請是轉寄給的，而不只是召集人直接邀請的參與者。 它不包含具有會議加入連結的人員，但不包括邀請本身和未經驗證 (匿名) 參與者。 他們必須在大廳等候。

請注意，如果會議召集人只希望對方直接邀請參加會議，可以停用轉寄會議邀請。

## <a name="control-access-to-meetings-by-non-organizers"></a>控制非召集人對會議的存取權

如果您有共用機密資訊的會議，或受到法規要求規範，建議所有參與者在大廳等候，直到會議召集人或共同召集人允許他們進入為止。 在此情況下，您可以將 **[誰可以略過大廳** ] 設定為 **[僅限召集人和共同召集人]**。

由於 **誰可以略過大廳** ，只會設定會議召集人可以變更的預設值，因此如果您在這個區域有合規性要求，請考慮強制執行具有敏感度標籤或會議範本的值。 如需詳細資訊，請參閱針對[敏感性會議設定Microsoft Teams 會議大廳](configure-lobby-sensitive-meetings.md)。

## <a name="set-meeting-policies-by-using-powershell"></a>使用 PowerShell 設定會議原則

您可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) PowerShell Cmdlet 搭配下列參數來設定本文所述的會議原則：

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) 以控制匿名使用者是否可以加入會議
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) 控制使用者是否可以略過大廳來撥入
- [-AutoAdmittedUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) 可控制誰可以略過大廳

## <a name="related-topics"></a>相關主題

[在沒有 Teams 帳戶的情況下加入會議](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[使用 Microsoft Teams 系統管理中心來設定全組織原則。](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[外部參與者會收到「登入 Teams 以加入，或連絡會議召集人」](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)
