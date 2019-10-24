---
title: 開啟或關閉 Microsoft 團隊的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 開啟或關閉 Microsoft 團隊中的來賓存取功能。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 186c83b82c396a21fe0098a561bcd4db13370140
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "37571574"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>開啟或關閉 Microsoft 團隊的來賓存取權
===================================================

做為 Office 365 系統管理員，您必須先啟用來賓功能，您或貴組織的使用者（特別是團隊擁有者）才能新增來賓。

來賓設定是在 Azure Active Directory 中設定。 在您的 Office 365 組織中，變更的時間必須是2小時到24小時才能生效。 當使用者嘗試將來賓新增到其小組時，如果使用者看到「與您的系統管理員聯繫」的訊息，可能是因為來賓功能尚未啟用或設定尚未生效。

> [!IMPORTANT]
> 若要啟用來賓存取功能的完整體驗，請務必瞭解 Microsoft 團隊、Azure Active Directory 和 Office 365 之間的核心授權相依性。 如需詳細資訊，請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。

## <a name="guest-access-vs-external-access-federation"></a>來賓存取與外部存取（同盟）

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>在 Microsoft [團隊管理中心] 中設定來賓存取

1.  登入 Microsoft 團隊系統管理中心。

2.  選取 [全**組織性設定** > **來賓存取**]。

3. 將**Microsoft 團隊中的 [允許來賓存取**] 切換為 [**開啟**]。

    ![[允許來賓存取開關設定為開啟] ](media/set-up-guests-image1.png)

4.  根據您要允許來賓使用者的功能，將 [**通話**]、[**會議**] 和 [**訊息**] 下的切換設定為 [**開啟**] 或 [**關閉**]。

    - **撥打私人電話** **–開啟此設定可**讓來賓進行對等通話。
    - [**允許 IP 影片**] **-開啟此設定可**讓來賓在通話和會議中使用影片。
    - **螢幕共用模式**–此設定會控制來賓使用者螢幕共用的可用性。 
       - 將此設定設為 [**停用**]，移除來賓在小組中共用畫面的功能。 
       - 將此設定轉換為 [**單一應用程式**] 以允許共用個別的應用程式。 
       - 將此設定設為 [**整個畫面**] 以允許完整的螢幕共用。
    - [**允許立即開會**] –開啟**此設定可讓來賓在 Microsoft**團隊中使用 [立即開會] 功能。
    - **編輯已傳送的郵件** **-開啟此設定，** 允許來賓編輯先前傳送的郵件。
    - **來賓可以刪除已傳送的郵件**–開啟**此設定，** 允許來賓刪除先前傳送的郵件。
    - [**聊天**] **：開啟此設定可**讓客人在團隊中使用聊天功能。
    - **在交談中使用 giphy** –開啟此**設定可讓來賓在交談**中使用 giphy。 Giphy 是線上資料庫和搜尋引擎，可讓使用者搜尋及共用動畫 GIF 檔案。 每個 Giphy 都會獲指派內容評級。
    - **Giphy 內容分級**–從下拉式清單中選取評分：
       - [**允許所有內容**-來賓] 能在聊天中插入所有 giphy，無論內容分級為何。
       - [**適中**]-訪客將能在聊天中插入 giphy，但將會針對成人內容適度地限制。
       - [**嚴格**]-來賓將能在聊天中插入 giphy，但會限制插入成人內容。
    - **在交談中使用 meme** -開啟此**設定可讓來賓在交談**中使用 meme。
    - **在交談中使用不乾膠**圖示，請**開啟此設定，** 以允許來賓在交談中使用不乾膠圖示。 


5.  按一下 [**儲存**]。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 開啟或關閉來賓存取

1.  從下載商務用 Skype Online PowerShell 模組https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  將 PowerShell 會話連線到商務用 Skype Online 端點。

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  檢查您的設定， `AllowGuestUser`如果`$False`是，請使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Cmdlet 將它設定為`$True`。

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
您現在可以在貴組織的小組中擁有來賓使用者。

## <a name="more-information"></a>其他資訊

請觀看下列影片，以取得更多關於來賓存取的詳細資料。

|  |  |
|---------|---------|
| 在 Microsoft 團隊中新增來賓   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
