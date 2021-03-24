---
title: 管理 Microsoft Teams 的使用者存取權
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何指派或移除 Teams 授權給貴組織的使用者來管理 Teams 的使用者存取權。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29cf3f6816b3c1e0b00026b1ba4ad961a6a92aa6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093537"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="a2d51-103">管理使用者對 Teams 的存取權</span><span class="sxs-lookup"><span data-stu-id="a2d51-103">Manage user access to Teams</span></span>

<span data-ttu-id="a2d51-104">您可以指派或移除 Microsoft Teams 產品授權，以管理使用者層級的 Teams 存取權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="a2d51-105">除了匿名加入 Teams 會議之外，貴組織的每個使用者都必須擁有 Teams 授權，才能使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="a2d51-106">您可以在建立新使用者帳戶時指派 Teams 授權給新使用者，或指派給擁有現有帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2d51-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="a2d51-107">根據預設，當授權方案 (例如 Microsoft 365 企業版 E3 或 Microsoft 365 商務進級版) 指派給使用者時，系統會自動指派 Teams 授權，且該使用者已啟用 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="a2d51-108">您隨時都可以移除或指派授權，為使用者停用或啟用 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="a2d51-109">使用從 Teams 系統管理中心管理的訊息策略，控制 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">哪些</a>聊天和頻道傳訊功能可供 Teams 中的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a2d51-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="a2d51-110">您可以使用預設策略，或為貴組織人員建立一或多個自訂訊息策略。</span><span class="sxs-lookup"><span data-stu-id="a2d51-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="a2d51-111">若要深入瞭解，請參閱 [在 Teams 中管理訊息策略](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a2d51-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="a2d51-112">您可以在 Microsoft 365 系統管理中心或使用 PowerShell 管理 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="a2d51-113">您必須是全域系統管理員或使用者管理系統管理員，才能管理授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="a2d51-114">我們建議您為所有使用者啟用 Teams，以便針對專案和其他動態計畫，以組織方式組成團隊。</span><span class="sxs-lookup"><span data-stu-id="a2d51-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="a2d51-115">即使您進行試驗，讓所有使用者都保持 Teams 啟用可能仍然很有説明，但只會將通訊目標鎖定至試驗使用者群組。</span><span class="sxs-lookup"><span data-stu-id="a2d51-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="a2d51-116">使用 Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="a2d51-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="a2d51-117">Teams 使用者層級授權會透過 Microsoft 365 系統管理中心使用者管理介面直接管理。</span><span class="sxs-lookup"><span data-stu-id="a2d51-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="a2d51-118">系統管理員可以在建立新使用者帳戶時指派授權給新使用者，或指派給擁有現有帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2d51-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a2d51-119">系統管理員必須擁有全域系統管理員或使用者管理系統管理員許可權，才能管理 Microsoft Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="a2d51-120">使用 Microsoft 365 系統管理中心一次管理個別使用者或少數使用者的 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="a2d51-121">您可以在授權頁面或 (管理Teams 授權) 最多 20 **個使用者。**</span><span class="sxs-lookup"><span data-stu-id="a2d51-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="a2d51-122">您選擇的方法取決於您要管理特定使用者的產品授權，或管理特定產品的使用者授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="a2d51-123">如果您需要管理大量使用者的 Teams 授權 ，例如數百或數千個使用者，請使用[Azure Active Directory ](/azure/active-directory/users-groups-roles/licensing-groups-assign) (Azure AD) 中的[PowerShell](#using-powershell)或群組授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="a2d51-124">指派 Teams 授權</span><span class="sxs-lookup"><span data-stu-id="a2d51-124">Assign a Teams license</span></span>

<span data-ttu-id="a2d51-125">步驟會根據您使用授權頁面或活動 **使用者頁面\*\*\*\*而** 不同。</span><span class="sxs-lookup"><span data-stu-id="a2d51-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="a2d51-126">有關逐步指示，請參閱指派 [授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="a2d51-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![使用者已啟用 Teams 授權之螢幕擷取畫面](media/assign-teams-licenses-1.png)    | ![使用者已啟用 Teams 授權之螢幕擷取畫面](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="a2d51-129">移除 Teams 授權</span><span class="sxs-lookup"><span data-stu-id="a2d51-129">Remove a Teams license</span></span>

<span data-ttu-id="a2d51-130">當您從使用者移除 Teams 授權時，該使用者的 Teams 會停用，而且他們不會再在應用程式啟動器或首頁中看到 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="a2d51-131">有關詳細步驟，請參閱 [取消使用者授權](/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="a2d51-131">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![已停用使用者的 Teams 授權螢幕擷取畫面](media/remove-teams-licenses-1.png)    | ![已停用使用者的 Teams 授權螢幕擷取畫面](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="a2d51-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2d51-134">Using PowerShell</span></span>

<span data-ttu-id="a2d51-135">使用 PowerShell 大量管理使用者的 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="a2d51-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="a2d51-136">您透過 PowerShell 啟用和停用 Teams 的方式，與任何其他服務方案授權相同。</span><span class="sxs-lookup"><span data-stu-id="a2d51-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="a2d51-137">您需要 Teams 服務方案識別碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2d51-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="a2d51-138">Microsoft Teams：TEAMS1</span><span class="sxs-lookup"><span data-stu-id="a2d51-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="a2d51-139">GCC 的 Microsoft Teams：TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="a2d51-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="a2d51-140">Microsoft Teams for DoD：TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="a2d51-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="a2d51-141">大量指派 Teams 授權</span><span class="sxs-lookup"><span data-stu-id="a2d51-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="a2d51-142">有關詳細步驟，請參閱使用 [PowerShell 將授權指派給使用者帳戶](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a2d51-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="a2d51-143">大量移除 Teams 授權</span><span class="sxs-lookup"><span data-stu-id="a2d51-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="a2d51-144">有關詳細步驟，請參閱停用 [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 服務存取權，以及指派使用者授權 [時停用服務存取權](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。</span><span class="sxs-lookup"><span data-stu-id="a2d51-144">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="a2d51-145">範例</span><span class="sxs-lookup"><span data-stu-id="a2d51-145">Example</span></span> 

<span data-ttu-id="a2d51-146">以下是如何使用 [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) 和 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) Cmdlet 來停用 Teams 的範例，供擁有特定授權方案的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a2d51-146">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="a2d51-147">例如，請遵循下列步驟，針對擁有特定授權計畫的所有使用者，先停用 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="a2d51-148">然後針對應具有 Teams 存取權的每個個別使用者啟用 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2d51-149">[New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) Cmdlet 會啟用先前停用的所有服務，除非您在自訂腳本中明確識別。</span><span class="sxs-lookup"><span data-stu-id="a2d51-149">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="a2d51-150">例如，如果您想要同時停用 Exchange 和 Sway，同時停用 Teams，您必須在腳本中納入此功能，否則將針對您識別的使用者啟用 Exchange 和 Sway。</span><span class="sxs-lookup"><span data-stu-id="a2d51-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="a2d51-151">執行下列命令以顯示貴組織中所有可用的授權方案。</span><span class="sxs-lookup"><span data-stu-id="a2d51-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="a2d51-152">若要深入瞭解，請參閱 [使用 PowerShell 來查看授權和服務](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a2d51-152">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="a2d51-153">執行下列命令，即貴組織的名稱，以及您先前步驟中所提取之授權計畫的 \<CompanyName:License> 識別碼。</span><span class="sxs-lookup"><span data-stu-id="a2d51-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="a2d51-154">例如，ContosoSchool：ENTERPRISEPACK_STUDENT。</span><span class="sxs-lookup"><span data-stu-id="a2d51-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="a2d51-155">請執行下列命令，針對擁有授權方案有效授權之所有使用者停用 Teams。</span><span class="sxs-lookup"><span data-stu-id="a2d51-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="a2d51-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="a2d51-156">Related topics</span></span>

- [<span data-ttu-id="a2d51-157">Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="a2d51-157">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="a2d51-158">指派 Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="a2d51-158">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="a2d51-159">使用 PowerShell 查看授權和服務</span><span class="sxs-lookup"><span data-stu-id="a2d51-159">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="a2d51-160">用於授權的產品名稱和服務方案識別碼</span><span class="sxs-lookup"><span data-stu-id="a2d51-160">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="a2d51-161">教育用 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="a2d51-161">Education SKU reference</span></span>](sku-reference-edu.md)