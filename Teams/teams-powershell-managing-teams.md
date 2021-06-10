---
title: 使用 powerShell Teams管理Microsoft Teams
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何使用 PowerShell Microsoft Teams管理Teams程式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71f68c813a1379c29cf64ad732eb5da1ffe4d188
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238969"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="6534a-103">使用 powerShell Teams管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6534a-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="6534a-104">本文將說明如何使用 PowerShell Microsoft Teams管理Teams商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="6534a-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="6534a-105">使用本指南與[Cmdlet](/powershell/teams/?view=teams-ps) Microsoft Teams及[Cmdlet 商務用 Skype一起使用](/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6534a-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="6534a-106">使用 PowerShell 建立及管理團隊</span><span class="sxs-lookup"><span data-stu-id="6534a-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="6534a-107">建立及管理團隊的 Cmdlet 會Microsoft Teams [PowerShell 模組中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。</span><span class="sxs-lookup"><span data-stu-id="6534a-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="6534a-108">Teams群組Office 365，因此當您建立團隊時，即會建立群組。</span><span class="sxs-lookup"><span data-stu-id="6534a-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="6534a-109">有一組 Cmdlet 提供在核心小組及其設定 (、) 、管理小組使用者 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` (、) ，以及管理團隊 (、) 頻道的 ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6534a-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="6534a-110">所有這些 Cmdlet 都可以以使用者方式執行，但只能在您擁有或成員的團隊中執行。</span><span class="sxs-lookup"><span data-stu-id="6534a-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="6534a-111">如果您是全域系統管理員或Teams系統管理員，就可以對貴組織的所有團隊採取行動。</span><span class="sxs-lookup"><span data-stu-id="6534a-111">If you are a Global Admin or Teams Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> <span data-ttu-id="6534a-112">**PowerShell** 模組 Cmdlet Microsoft Teams中使用的 GroupId 與 PowerShell 模組中所Exchange的 ``Get-UnifiedGroup`` Identity 屬性相同。</span><span class="sxs-lookup"><span data-stu-id="6534a-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="6534a-113">透過 PowerShell 管理政策</span><span class="sxs-lookup"><span data-stu-id="6534a-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="6534a-114">商務用 Skype線上連接器正在合併到 powerShell Teams中。</span><span class="sxs-lookup"><span data-stu-id="6534a-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="6534a-115">目前可在公開預覽中使用。</span><span class="sxs-lookup"><span data-stu-id="6534a-115">It is currently available in public preview.</span></span> <span data-ttu-id="6534a-116">一段時間之後，商務用 Skype PowerShell 模組中Teams內提供適用于 Teams Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6534a-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="6534a-117">安裝步驟可在[PowerShell](teams-powershell-install.md) Teams中提供。</span><span class="sxs-lookup"><span data-stu-id="6534a-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="6534a-118">一旦連線到線上，Cmdlet 就會在 PowerShell 會話中商務用 Skype使用。</span><span class="sxs-lookup"><span data-stu-id="6534a-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="6534a-119">如需詳細資訊，請參閱使用[PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)商務用 Skype管理 Office 365 Online 。</span><span class="sxs-lookup"><span data-stu-id="6534a-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="6534a-120">在 Cmdlet 模組中尋找管理商務用 Skype[的 Cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="6534a-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="6534a-121">原則是一組可精細地適用于個別使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="6534a-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="6534a-122">每個策略類型都有一組自己的 Cmdlet，用於建立、檢視、刪除和更新策略本身，然後將那些策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6534a-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="6534a-123">一般結構為：</span><span class="sxs-lookup"><span data-stu-id="6534a-123">The general structure is:</span></span>

- <span data-ttu-id="6534a-124">**GET** 命令 (例如) ：會返回可供您指派在貴組織中使用的政策檔，包括 Microsoft 建立供您使用的政策，以及您建立之自訂策略。 ``Get-CsTeamsMeetingPolicy``</span><span class="sxs-lookup"><span data-stu-id="6534a-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="6534a-125">若要只尋找您于組織中建立自訂策略，請使用 ``-Filter "tag:*"`` 。</span><span class="sxs-lookup"><span data-stu-id="6534a-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="6534a-126">**新的** (例如) ：為貴組織建立新策略，以指派 ``New-CsTeamsMeetingPolicy`` 給貴組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="6534a-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="6534a-127">並非所有策略都支援建立自訂策略。</span><span class="sxs-lookup"><span data-stu-id="6534a-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="6534a-128">這通常是為了確保貴組織使用的策略具有支援的設定組合。</span><span class="sxs-lookup"><span data-stu-id="6534a-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="6534a-129">**SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy`` ，) ：設定特定策略上的特定值。</span><span class="sxs-lookup"><span data-stu-id="6534a-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="6534a-130">有些策略沒有 SET 命令可用，或包含無法自訂于該策略的參數。</span><span class="sxs-lookup"><span data-stu-id="6534a-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="6534a-131">PowerShell 描述會告訴您哪些參數無法自訂。</span><span class="sxs-lookup"><span data-stu-id="6534a-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="6534a-132">若要編輯預設會指派給組織中未指派自訂策略的使用者的策略，請執行 ``Set-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="6534a-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="6534a-133">**移除** (命令，例如) ：刪除已在租使用者中建立 ``Remove-CsTeamsMeetingPolicy`` 自訂策略。</span><span class="sxs-lookup"><span data-stu-id="6534a-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="6534a-134">如果您刪除已指派給貴組織中至少一位使用者的自訂策略，該使用者會回到全域原則。</span><span class="sxs-lookup"><span data-stu-id="6534a-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="6534a-135">您實際上無法移除貴組織的全域原則，但如果您想要將貴組織的全域原則重設為 Microsoft 提供的預設設定，請執行 ``Remove-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="6534a-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="6534a-136">**例如** ， (GRANT 命令 ``Grant-CsTeamsMeetingPolicy``) ：指派一個策略給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="6534a-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="6534a-137">若要移除自訂策略指派，讓使用者回到貴組織的預設策略，請執行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。</span><span class="sxs-lookup"><span data-stu-id="6534a-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="6534a-138">並非所有策略都允許建立自訂策略，而有些策略有無法自訂 (因此您可以查看設定，但無法設定自訂值 ``set-`` ``new-``) 。</span><span class="sxs-lookup"><span data-stu-id="6534a-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="6534a-139">每個 Cmdlet 的檔會指出客戶是否可以使用參數。</span><span class="sxs-lookup"><span data-stu-id="6534a-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="6534a-140">常用參數：</span><span class="sxs-lookup"><span data-stu-id="6534a-140">Common parameters:</span></span>

- <span data-ttu-id="6534a-141">**身分** 識別： ``Get-`` 對於 ``Set-`` 、 ``New-`` 和 ``Remove-`` **，Identity** 參數一定會參照特定的策略實例。</span><span class="sxs-lookup"><span data-stu-id="6534a-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="6534a-142">針對 ``Grant`` ， **身分識別** 參數是指要採用原則的特定使用者物件。</span><span class="sxs-lookup"><span data-stu-id="6534a-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="6534a-143">透過 PowerShell 管理配置</span><span class="sxs-lookup"><span data-stu-id="6534a-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="6534a-144">在 Cmdlet 模組中尋找管理您商務用 Skype [Cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="6534a-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="6534a-145">設定是服務中維護的設定容器，無法以使用者層級指定。</span><span class="sxs-lookup"><span data-stu-id="6534a-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="6534a-146">設定一直適用于整個組織。</span><span class="sxs-lookup"><span data-stu-id="6534a-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="6534a-147">您的通用群組組是貴組織中唯一有效的組組。</span><span class="sxs-lookup"><span data-stu-id="6534a-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="6534a-148">每個組式類型都隨附兩個主要 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6534a-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="6534a-149">``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：</span><span class="sxs-lookup"><span data-stu-id="6534a-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="6534a-150">SET 命令 (例如 ``Set-CsTeamsClientConfiguration`` ，) ：設定該類型設定中的屬性。</span><span class="sxs-lookup"><span data-stu-id="6534a-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="6534a-151">指定要修改的參數。</span><span class="sxs-lookup"><span data-stu-id="6534a-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="6534a-152">您可以用以下兩種方式之一來參照要修改的組式：指定 -**身分識別全域**，或按 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。</span><span class="sxs-lookup"><span data-stu-id="6534a-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="6534a-153">每個系統管理員角色可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="6534a-153">What can each admin role do?</span></span>

<span data-ttu-id="6534a-154">請參閱[使用Microsoft Teams系統管理員角色來管理](using-admin-roles.md)Teams瞭解哪些系統管理員角色可以執行每個 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6534a-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6534a-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="6534a-155">Related topics</span></span>

[<span data-ttu-id="6534a-156">安裝 powerShell Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6534a-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="6534a-157">TeamsPowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="6534a-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="6534a-158">Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="6534a-158">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="6534a-159">商務用 Skype Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="6534a-159">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="6534a-160">使用 Teams 系統管理員角色來管理 Teams</span><span class="sxs-lookup"><span data-stu-id="6534a-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)