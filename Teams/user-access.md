---
title: 管理使用者對 Microsoft 團隊的存取權
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: 瞭解如何在每位使用者上啟用或停用使用者層級的存取。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ee7a8303ed9c46e1b60bbd3588fc36d754f773d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707448"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="4d953-103">管理使用者對 Microsoft 團隊的存取權</span><span class="sxs-lookup"><span data-stu-id="4d953-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="4d953-104">在使用者層級，您可以指派或移除 Microsoft 團隊產品授權，在每位使用者上啟用或停用 Microsoft 團隊的存取權。</span><span class="sxs-lookup"><span data-stu-id="4d953-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="4d953-105">使用來自團隊系統管理中心管理的訊息原則，以控制可供團隊使用者使用的聊天和通道訊息功能。</span><span class="sxs-lookup"><span data-stu-id="4d953-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="4d953-106">您可以針對組織中的人員，使用預設原則或建立一或多個自訂的訊息策略。</span><span class="sxs-lookup"><span data-stu-id="4d953-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="4d953-107">若要深入瞭解，請參閱[管理團隊中的訊息傳遞原則](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4d953-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="4d953-108">Microsoft 建議您針對公司中的所有使用者開啟團隊，讓小組可以針對專案和其他動態方案進行 organically。</span><span class="sxs-lookup"><span data-stu-id="4d953-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="4d953-109">即使您決定要試點，仍可將團隊保持為所有使用者使用，但只有目標是與使用者的試驗群組進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4d953-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="4d953-110">透過 Microsoft 365 系統管理中心管理團隊</span><span class="sxs-lookup"><span data-stu-id="4d953-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="4d953-111">團隊使用者層級授權是透過 Microsoft 365 系統管理中心使用者管理介面直接管理。</span><span class="sxs-lookup"><span data-stu-id="4d953-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="4d953-112">系統管理員可以在建立新的使用者帳戶時指派授權給新的使用者，或指派給現有帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="4d953-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="4d953-113">系統管理員必須擁有 Office 365 全域系統管理員或使用者管理管理員的許可權，才能管理 Microsoft 團隊授權。</span><span class="sxs-lookup"><span data-stu-id="4d953-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="4d953-114">當您將 E3 或 E5 等授權 SKU 指派給使用者時，系統會自動指派 Microsoft 團隊授權，並為 Microsoft 團隊啟用該使用者。</span><span class="sxs-lookup"><span data-stu-id="4d953-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="4d953-115">系統管理員可以對所有 Office 365 服務和授權進行精細的控制，而且可以啟用或停用特定使用者或使用者群組的 Microsoft 團隊授權。</span><span class="sxs-lookup"><span data-stu-id="4d953-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![系統管理中心的 [產品授權] 區段螢幕擷取畫面。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="4d953-117">團隊使用者授權隨時都可以停用。</span><span class="sxs-lookup"><span data-stu-id="4d953-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="4d953-118">授權停用之後，系統就會禁止使用者存取 Microsoft 團隊，而且使用者將無法在 Office 365 應用程式啟動器和首頁中看到團隊。</span><span class="sxs-lookup"><span data-stu-id="4d953-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![顯示 [產品授權] 區段中已選取 [小組] 的螢幕擷取畫面。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="4d953-120">透過 PowerShell 管理</span><span class="sxs-lookup"><span data-stu-id="4d953-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d953-121">新的-MsolLicenseOptions 會啟用先前已停用的所有服務，除非您在自訂腳本中明確標示。</span><span class="sxs-lookup"><span data-stu-id="4d953-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explicitly identified in your customized script.</span></span> <span data-ttu-id="4d953-122">例如，如果您想讓 Exchange & Sway 同時停用，同時又停用小組，您必須在腳本中包含這項功能，否則您已識別的使用者就能使用這兩種 Exchange & Sway。</span><span class="sxs-lookup"><span data-stu-id="4d953-122">As an example, if you wanted to leave both Exchange & Sway disabled while additionally disabling Teams, you'd need to include this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="4d953-123">若要使用 GUI 來管理這項功能，請參閱[Office 365 授權報告和管理工具-指派批量移除授權](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4d953-123">To use a GUI to manage this functionality, see [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) for more information.</span></span>

<span data-ttu-id="4d953-124">透過 PowerShell 啟用和停用團隊作為工作負載授權，就完成了任何其他工作負載。</span><span class="sxs-lookup"><span data-stu-id="4d953-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="4d953-125">Microsoft 團隊的服務方案名稱是 TEAMS1。</span><span class="sxs-lookup"><span data-stu-id="4d953-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="4d953-126">針對 GCC，服務方案名稱是 TEAMS_GOV。</span><span class="sxs-lookup"><span data-stu-id="4d953-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="4d953-127">針對 GCC 高版，服務方案名稱是 TEAMS_GCCHIGH。</span><span class="sxs-lookup"><span data-stu-id="4d953-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="4d953-128">如果是 DoD，服務方案名稱是 TEAMS_DOD （請參閱[使用 Office 365 PowerShell 停用服務的存取權](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)，以取得詳細資訊。）</span><span class="sxs-lookup"><span data-stu-id="4d953-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="4d953-129">**範例：** 以下只是一個快速範例，說明如何針對特定授權類型的每個人停用團隊。</span><span class="sxs-lookup"><span data-stu-id="4d953-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="4d953-130">您必須先執行此動作，然後針對需要試驗的使用者逐一啟用此動作。</span><span class="sxs-lookup"><span data-stu-id="4d953-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="4d953-131">若要顯示貴組織內擁有的訂閱類型，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="4d953-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="4d953-132">填入包括貴組織名稱和學校方案的方案名稱（例如 ContosoSchool： ENTERPRISEPACK_STUDENT），然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4d953-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="4d953-133">若要針對所有擁有您命名方案之有效授權的使用者停用團隊，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4d953-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![代表決策點的圖示](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="4d953-135">決策點</span><span class="sxs-lookup"><span data-stu-id="4d953-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="4d953-136">貴組織在整個組織中要加入哪些小組的方案？</span><span class="sxs-lookup"><span data-stu-id="4d953-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="4d953-137">（試驗或開啟）</span><span class="sxs-lookup"><span data-stu-id="4d953-137">(Pilot or Open)</span></span></li></ul>         |
|![代表後續步驟的圖示](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="4d953-139">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4d953-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="4d953-140">如果您是透過關閉的試運行進行加入，請決定您是否要透過授權或目標通訊來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="4d953-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="4d953-141">根據決定，請採取步驟以確保只有獲允許存取團隊的試驗使用者（視需要）。</span><span class="sxs-lookup"><span data-stu-id="4d953-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="4d953-142">針對將（或將沒有）存取團隊的使用者記錄指導方針。</span><span class="sxs-lookup"><span data-stu-id="4d953-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="4d953-143">在 Office 365 租使用者層級管理團隊</span><span class="sxs-lookup"><span data-stu-id="4d953-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

