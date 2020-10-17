---
title: 管理使用者對 Microsoft 團隊的存取權
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何指派或移除團隊授權給組織中的使用者，以管理使用者對團隊的存取權。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521380"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="41fc8-103">管理使用者對 Teams 的存取權</span><span class="sxs-lookup"><span data-stu-id="41fc8-103">Manage user access to Teams</span></span>

<span data-ttu-id="41fc8-104">您可以指派或移除 Microsoft 團隊產品授權，在使用者層級管理團隊的存取權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="41fc8-105">貴組織中的每位使用者都必須擁有團隊授權，才能使用團隊。</span><span class="sxs-lookup"><span data-stu-id="41fc8-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="41fc8-106">您可以在建立新的使用者帳戶時指派團隊授權給新使用者，或是使用現有帳戶指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="41fc8-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="41fc8-107">根據預設，當授權方案 (：例如，Microsoft 365 企業版 E3 或 Microsoft 365 Business Premium) 指派給使用者時，系統會自動指派團隊授權，並為團隊啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="41fc8-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="41fc8-108">您可以隨時移除或指派授權，來停用或啟用使用者的團隊。</span><span class="sxs-lookup"><span data-stu-id="41fc8-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="41fc8-109">使用來自 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">團隊系統管理中心</a>管理的訊息原則，以控制可供團隊使用者使用的聊天和通道訊息功能。</span><span class="sxs-lookup"><span data-stu-id="41fc8-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="41fc8-110">您可以針對組織中的人員，使用預設原則或建立一或多個自訂的訊息策略。</span><span class="sxs-lookup"><span data-stu-id="41fc8-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="41fc8-111">若要深入瞭解，請參閱 [管理團隊中的訊息傳遞原則](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="41fc8-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="41fc8-112">您可以在 Microsoft 365 系統管理中心或使用 PowerShell 管理團隊授權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="41fc8-113">您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="41fc8-114">我們建議您為所有使用者啟用團隊，讓團隊可以針對專案和其他動態方案進行 organically。</span><span class="sxs-lookup"><span data-stu-id="41fc8-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="41fc8-115">即使您執行的是試用版，仍可將團隊保持為所有使用者使用，但只有目標是與使用者的試驗群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="41fc8-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="41fc8-116">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="41fc8-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="41fc8-117">團隊使用者層級授權是透過 Microsoft 365 系統管理中心使用者管理介面直接管理。</span><span class="sxs-lookup"><span data-stu-id="41fc8-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="41fc8-118">系統管理員可以在建立新的使用者帳戶時指派授權給新的使用者，或指派給現有帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="41fc8-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="41fc8-119">系統管理員必須具備全域系統管理員或使用者管理管理員的許可權，才能管理 Microsoft 團隊授權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="41fc8-120">使用 Microsoft 365 系統管理中心，分別管理個別使用者或一組小組使用者的小組授權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="41fc8-121">您可以在 [ **授權** ] 頁面上管理多達20個使用者，同時) 或 [作用中 **使用者** ] 頁面上的 [團隊授權] (。</span><span class="sxs-lookup"><span data-stu-id="41fc8-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="41fc8-122">您選擇的方法取決於您是否要管理特定使用者的產品授權，或管理特定產品的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="41fc8-123">如果您需要管理大量使用者（例如幾百或數千位使用者）的團隊授權，請[在 Azure Active Directory 中使用 Powershell 或群組式授權 (AZURE AD) ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。 [use Powershell](#using-powershell)</span><span class="sxs-lookup"><span data-stu-id="41fc8-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="41fc8-124">指派團隊授權</span><span class="sxs-lookup"><span data-stu-id="41fc8-124">Assign a Teams license</span></span>

<span data-ttu-id="41fc8-125">這些步驟會根據您使用的是 [ **授權** ] 頁面或 [作用中 **使用者** ] 頁面而有所不同。</span><span class="sxs-lookup"><span data-stu-id="41fc8-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="41fc8-126">如需逐步指示，請參閱 [指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="41fc8-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![已針對使用者啟用之團隊授權的螢幕擷取畫面](media/assign-teams-licenses-1.png)    | ![已針對使用者啟用之團隊授權的螢幕擷取畫面](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="41fc8-129">移除團隊授權</span><span class="sxs-lookup"><span data-stu-id="41fc8-129">Remove a Teams license</span></span>

<span data-ttu-id="41fc8-130">當您移除使用者的小組授權時，系統會停用該使用者的小組，且不會再在應用程式啟動器或首頁中看到小組。</span><span class="sxs-lookup"><span data-stu-id="41fc8-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="41fc8-131">如需詳細步驟，請參閱 [取消指派給使用者的授權](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="41fc8-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![使用者已停用之小組授權的螢幕擷取畫面](media/remove-teams-licenses-1.png)    | ![使用者已停用之小組授權的螢幕擷取畫面](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="41fc8-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="41fc8-134">Using PowerShell</span></span>

<span data-ttu-id="41fc8-135">使用 PowerShell 管理大量使用者的團隊授權。</span><span class="sxs-lookup"><span data-stu-id="41fc8-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="41fc8-136">您可以透過 PowerShell 啟用和停用團隊，就像在任何其他服務方案授權中一樣。</span><span class="sxs-lookup"><span data-stu-id="41fc8-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="41fc8-137">您需要團隊服務方案的識別碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="41fc8-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="41fc8-138">Microsoft 團隊： TEAMS1</span><span class="sxs-lookup"><span data-stu-id="41fc8-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="41fc8-139">適用于 GCC 的 Microsoft 團隊： TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="41fc8-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="41fc8-140">適用于 DoD 的 Microsoft 團隊： TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="41fc8-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="41fc8-141">大量指派團隊授權</span><span class="sxs-lookup"><span data-stu-id="41fc8-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="41fc8-142">如需詳細步驟，請參閱 [使用 PowerShell 指派授權給使用者帳戶](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="41fc8-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="41fc8-143">大量移除團隊授權</span><span class="sxs-lookup"><span data-stu-id="41fc8-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="41fc8-144">如需詳細步驟，請參閱 [使用 PowerShell 停用服務的存取權](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) ，以及 [在指派使用者授權時停用服務的存取權](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。</span><span class="sxs-lookup"><span data-stu-id="41fc8-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="41fc8-145">範例</span><span class="sxs-lookup"><span data-stu-id="41fc8-145">Example</span></span> 

<span data-ttu-id="41fc8-146">以下是如何使用 [新的 MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 和 [MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) Cmdlet 來針對擁有特定授權方案的使用者停用團隊的範例。</span><span class="sxs-lookup"><span data-stu-id="41fc8-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="41fc8-147">例如，請依照下列步驟，先針對所有擁有特定授權方案的使用者停用團隊。</span><span class="sxs-lookup"><span data-stu-id="41fc8-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="41fc8-148">然後針對應該有權存取團隊的每位使用者，分別啟用團隊。</span><span class="sxs-lookup"><span data-stu-id="41fc8-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41fc8-149">[新的 MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) Cmdlet 會啟用先前已停用的所有服務，除非您在自訂腳本中明確標示。</span><span class="sxs-lookup"><span data-stu-id="41fc8-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="41fc8-150">例如，如果您想要停用 Exchange 和 Sway 同時又停用小組，您必須在腳本中包含這項功能，否則您所識別的使用者將會啟用 Exchange 和 Sway。</span><span class="sxs-lookup"><span data-stu-id="41fc8-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="41fc8-151">執行下列命令，以顯示貴組織中所有可用的授權方案。</span><span class="sxs-lookup"><span data-stu-id="41fc8-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="41fc8-152">若要深入瞭解，請參閱 [使用 PowerShell 來查看授權及服務](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="41fc8-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="41fc8-153">執行下列命令，其中 \<CompanyName:License> 是您的組織名稱，以及您在先前步驟中檢索之授權方案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="41fc8-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="41fc8-154">例如，ContosoSchool： ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="41fc8-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="41fc8-155">執行下列命令，以針對所有擁有授權方案有效授權的使用者停用團隊。</span><span class="sxs-lookup"><span data-stu-id="41fc8-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="41fc8-156">在組織層級管理團隊</span><span class="sxs-lookup"><span data-stu-id="41fc8-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="41fc8-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="41fc8-157">Related topics</span></span>

- [<span data-ttu-id="41fc8-158">團隊附加元件授權</span><span class="sxs-lookup"><span data-stu-id="41fc8-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="41fc8-159">指派團隊附加元件授權</span><span class="sxs-lookup"><span data-stu-id="41fc8-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="41fc8-160">使用 PowerShell 來查看授權與服務</span><span class="sxs-lookup"><span data-stu-id="41fc8-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="41fc8-161">用於授權的產品名稱和服務方案識別碼</span><span class="sxs-lookup"><span data-stu-id="41fc8-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="41fc8-162">教育版 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="41fc8-162">Education SKU reference</span></span>](sku-reference-edu.md)