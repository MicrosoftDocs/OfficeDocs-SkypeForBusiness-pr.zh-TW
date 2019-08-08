---
title: 使用 PowerShell 控制團隊的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 使用 PowerShell 來允許或封鎖對 Microsoft 團隊中的小組的來賓存取權。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e106dc56f56b5e26dd56384931deeecdd889305
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235874"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="27a94-103">使用 PowerShell 控制團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="27a94-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="27a94-104">除了使用 Microsoft 365 系統管理中心以及 Azure Active Directory (Azure AD) 入口網站之外, 您還可以使用 Windows PowerShell 來控制來賓存取。</span><span class="sxs-lookup"><span data-stu-id="27a94-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="27a94-105">您可以在 PowerShell 中執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="27a94-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="27a94-106">允許或封鎖來賓對所有團隊和 Office 365 群組的存取權</span><span class="sxs-lookup"><span data-stu-id="27a94-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="27a94-107">允許將來賓新增至所有團隊和 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="27a94-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="27a94-108">允許或封鎖來自特定小組或 Office 365 群組的來賓使用者</span><span class="sxs-lookup"><span data-stu-id="27a94-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="27a94-109">如需詳細資訊, 請參閱[管理 Office 365 群組中的來賓存取](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)中的「使用 PowerShell 控制來賓存取」。</span><span class="sxs-lookup"><span data-stu-id="27a94-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="27a94-110">您也可以使用 PowerShell 根據其網域來允許或封鎖來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="27a94-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="27a94-111">例如, 假設您的企業 (Contoso) 與另一個業務 (Fabrikam) 有合作關係。</span><span class="sxs-lookup"><span data-stu-id="27a94-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="27a94-112">您可以將 Fabrikam 新增至您的允許清單, 讓您的使用者可以將這些來賓新增到他們的群組中。</span><span class="sxs-lookup"><span data-stu-id="27a94-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="27a94-113">如需詳細資訊, 請參閱[允許/封鎖 Office 365 群組的來賓存取權](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="27a94-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="27a94-114">如果您想要封鎖團隊中的來賓, 但仍要允許他們存取 SharePoint 網站, 您可以使用 Azure AD Powershell Cmdlet 停用公司物件上的 AllowGuestsToAccessGroups 參數 (假設已開啟適用于 SharePoint 網站的外部共用).</span><span class="sxs-lookup"><span data-stu-id="27a94-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="27a94-115">來賓存取與外部存取</span><span class="sxs-lookup"><span data-stu-id="27a94-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
