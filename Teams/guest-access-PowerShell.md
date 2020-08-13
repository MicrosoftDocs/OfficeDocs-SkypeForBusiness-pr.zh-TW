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
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="9a3b1-103">使用 PowerShell 控制來賓對團隊的存取</span><span class="sxs-lookup"><span data-stu-id="9a3b1-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="9a3b1-104">除了使用 Microsoft 365 系統管理中心以及 Azure Active Directory) 入口網站 (，您也可以使用 Windows PowerShell 來控制來賓存取。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="9a3b1-105">您可以在 PowerShell 中執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="9a3b1-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="9a3b1-106">允許或封鎖來賓對所有團隊及 Microsoft 365 群組的存取權</span><span class="sxs-lookup"><span data-stu-id="9a3b1-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="9a3b1-107">允許將來賓新增至所有團隊及 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="9a3b1-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="9a3b1-108">允許或封鎖來自特定小組或 Microsoft 365 群組的來賓使用者</span><span class="sxs-lookup"><span data-stu-id="9a3b1-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="9a3b1-109">如需詳細資訊，請參閱[管理 Microsoft 365 群組中的來賓存取](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)中的「使用 PowerShell 控制來賓存取」。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="9a3b1-110">您也可以使用 PowerShell 根據其網域來允許或封鎖來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="9a3b1-111">例如，假設您的企業 (Contoso) 與其他商務 (Fabrikam) 有合作夥伴關係。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="9a3b1-112">您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增到他們的群組中。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="9a3b1-113">如需詳細資訊，請參閱[允許/封鎖 Microsoft 365 群組的來賓存取權](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="9a3b1-114">如果您想要封鎖團隊中的來賓，但仍要允許他們存取 SharePoint 網站，您可以使用 Azure AD PowerShell Cmdlet 停用公司物件上的 AllowGuestsToAccessGroups 參數（假設已開啟適用于 SharePoint 網站的外部共用）。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="9a3b1-115">使用 PowerShell 開啟或關閉來賓存取</span><span class="sxs-lookup"><span data-stu-id="9a3b1-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="9a3b1-116">從下載商務用 Skype Online PowerShell 模組https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="9a3b1-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="9a3b1-117">將 PowerShell 會話連線到商務用 Skype Online 端點。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="9a3b1-118">檢查您 `AllowGuestUser` 的設定，如果是 `$False` ，請使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Cmdlet 將它設定為 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="9a3b1-119">您現在可以在貴組織的小組中擁有來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="9a3b1-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="9a3b1-120">來賓存取與外部存取</span><span class="sxs-lookup"><span data-stu-id="9a3b1-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
