---
title: 使用 PowerShell 控制來賓對團隊的存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何使用 PowerShell 來允許或封鎖 Microsoft 團隊中所有團隊或特定團隊的來賓存取權。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e2833d1afedb975edf2532fb69c4fdbbdb31d4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655904"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>使用 PowerShell 控制來賓對團隊的存取
================================================

除了使用 Microsoft 365 系統管理中心以及 Azure Active Directory) 入口網站 (，您也可以使用 Windows PowerShell 來控制來賓存取。 您可以在 PowerShell 中執行下列動作：
  
- 允許或封鎖來賓對所有團隊及 Microsoft 365 群組的存取權

- 允許將來賓新增至所有團隊及 Microsoft 365 群組

- 允許或封鎖來自特定小組或 Microsoft 365 群組的來賓使用者

如需詳細資訊，請參閱[管理 Microsoft 365 群組中的來賓存取](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)中的「使用 PowerShell 控制來賓存取」。

  
您也可以使用 PowerShell 根據其網域來允許或封鎖來賓使用者。 例如，假設您的企業 (Contoso) 與其他商務 (Fabrikam) 有合作夥伴關係。 您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增到他們的群組中。 如需詳細資訊，請參閱[允許/封鎖 Microsoft 365 群組的來賓存取權](https://go.microsoft.com/fwlink/?linkid=854001)。
  
如果您想要封鎖團隊中的來賓，但仍要允許他們存取 SharePoint 網站，您可以使用 Azure AD PowerShell Cmdlet 停用公司物件上的 AllowGuestsToAccessGroups 參數（假設已開啟適用于 SharePoint 網站的外部共用）。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 開啟或關閉來賓存取

1.  從下載商務用 Skype Online PowerShell 模組https://www.microsoft.com/download/details.aspx?id=39366
 
2.  將 PowerShell 會話連線到商務用 Skype Online 端點。

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  檢查您 `AllowGuestUser` 的設定，如果是 `$False` ，請使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Cmdlet 將它設定為 `$True` 。

    ```powershell
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


## <a name="guest-access-vs-external-access"></a>來賓存取與外部存取

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
