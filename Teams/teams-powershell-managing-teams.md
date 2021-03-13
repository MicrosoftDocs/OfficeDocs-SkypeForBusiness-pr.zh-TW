---
title: 使用 Microsoft Teams PowerShell 管理 Teams
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
description: 瞭解如何使用 Teams PowerShell 管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4200c23f6320e67781353e62363d588c230fceb7
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756152"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="9b4fa-103">使用 Microsoft Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="9b4fa-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="9b4fa-104">本文將說明如何使用 Microsoft Teams PowerShell 來管理 Teams 和商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="9b4fa-105">請結合 Microsoft Teams [Cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps) 參考和商務 [用 Skype Cmdlet 參考，使用本指引](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="9b4fa-106">使用 PowerShell 建立及管理團隊</span><span class="sxs-lookup"><span data-stu-id="9b4fa-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="9b4fa-107">用於建立及管理團隊的 Cmdlet 在 [Microsoft Teams PowerShell 模組中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="9b4fa-108">Teams 由 Office 365 群組支援，因此當您建立團隊時，會建立群組。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="9b4fa-109">提供一組 Cmdlet 以在核心團隊及其設定 (、) 、管理小組使用者 ``new-team`` ``get-team``  ``set-team`` (、) ，以及管理團隊 ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` (、) ``remove-teamchannel`` 頻道的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="9b4fa-110">所有這些 Cmdlet 都可以以使用者方式執行，但只能在您擁有或為成員的團隊中執行。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="9b4fa-111">如果您是全域系統管理員或 Teams 服務系統管理員，您可以在貴組織的所有團隊上採取行動。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> <span data-ttu-id="9b4fa-112">Microsoft Teams PowerShell 模組 Cmdlet 中使用的 **GroupId** 與Exchange PowerShell 模組中所返回的 ``Get-UnifiedGroup`` 身分識別屬性相同。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="9b4fa-113">透過 PowerShell 管理原則</span><span class="sxs-lookup"><span data-stu-id="9b4fa-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="9b4fa-114">商務用 Skype Online Connector 正在整合到 Teams PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="9b4fa-115">目前可在公開預覽版中使用。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-115">It is currently available in public preview.</span></span> <span data-ttu-id="9b4fa-116">一段時間之後，適用于 Teams 的商務用 Skype Online Cmdlet 將會原生地在 Teams PowerShell 模組中提供。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="9b4fa-117">安裝步驟可在安裝 [Teams PowerShell](teams-powershell-install.md) 一文中提供。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="9b4fa-118">一旦連線到商務用 Skype Online，Cmdlet 就會在 PowerShell 會話中使用。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="9b4fa-119">如需詳細資訊，請參閱使用 [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)管理商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="9b4fa-120">在商務用 Skype Cmdlet 模組中尋找管理原則[的 Cmdlet。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="9b4fa-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="9b4fa-121">原則是一組可細微地適用于個別使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="9b4fa-122">每一個策略類型都有一組自己的 Cmdlet，用於建立、檢視、刪除和更新該政策本身，然後將那些策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="9b4fa-123">一般結構為：</span><span class="sxs-lookup"><span data-stu-id="9b4fa-123">The general structure is:</span></span>

- <span data-ttu-id="9b4fa-124">**GET** 命令 (例如) ：會返回可供您指派在貴組織中使用之政策檔，包括 Microsoft 建立供您使用以及您建立之自訂政策。 ``Get-CsTeamsMeetingPolicy``</span><span class="sxs-lookup"><span data-stu-id="9b4fa-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="9b4fa-125">若要只尋找您建立于貴組織的自訂策略，請使用 ``-Filter "tag:*"`` 。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="9b4fa-126">**新的** (例如) ：為貴組織建立新策略以指派 ``New-CsTeamsMeetingPolicy`` 給貴組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="9b4fa-127">並非所有策略都支援建立自訂策略。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="9b4fa-128">這通常是為了確保您組織使用的策略具有支援的設定組合。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="9b4fa-129">**SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy``) ：設定特定策略的特定值。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="9b4fa-130">某些策略沒有可用的 SET 命令，或包含無法自訂于該策略的參數。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="9b4fa-131">PowerShell 描述會告訴您哪些參數無法自訂。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="9b4fa-132">若要編輯預設會指派給貴組織中未指派自訂策略的使用者之策略，請執行 ``Set-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="9b4fa-133">**REMOVE** 命令 (例如) ：刪除已在租使用者 ``Remove-CsTeamsMeetingPolicy`` 中建立自訂策略。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="9b4fa-134">如果您刪除已指派給貴組織中至少一位使用者的自訂策略，該使用者會回到全域原則。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="9b4fa-135">您實際上無法移除貴組織的全域原則，但如果您想要將貴組織的全域原則重設為 Microsoft 提供的預設設定，請執行 ``Remove-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="9b4fa-136">**GRANT** 命令 (例如 ``Grant-CsTeamsMeetingPolicy`` ，) ：指派一個策略給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="9b4fa-137">若要移除自訂策略指派，並讓使用者回到貴組織的預設策略，請執行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="9b4fa-138">並非所有策略都允許建立自訂策略，而有些策略有無法自訂 (因此您可以在設定期間和期間設定自訂 ``set-`` ``new-`` 值) 。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="9b4fa-139">每個 Cmdlet 的檔會說明客戶是否可以使用參數。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="9b4fa-140">一般參數：</span><span class="sxs-lookup"><span data-stu-id="9b4fa-140">Common parameters:</span></span>

- <span data-ttu-id="9b4fa-141">**身分** 識別：對於 ``Get-`` ``Set-`` ``New-`` 、、和 ``Remove-`` **，Identity** 參數一定會參照特定的策略實例。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="9b4fa-142">針對 ``Grant`` ， **身分識別** 參數是指要將原則所針對的特定使用者物件。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="9b4fa-143">透過 PowerShell 管理組式</span><span class="sxs-lookup"><span data-stu-id="9b4fa-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="9b4fa-144">在商務用 Skype Cmdlet 模組中尋找管理您配置的[Cmdlet。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="9b4fa-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="9b4fa-145">設定是服務中維護的設定，無法以使用者層級指定。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="9b4fa-146">設定一直適用于整個組織。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="9b4fa-147">您的通用群組配置是貴組織中唯一有效的組配置。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="9b4fa-148">每個組式類型都隨附兩個主要 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b4fa-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="9b4fa-149">``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：</span><span class="sxs-lookup"><span data-stu-id="9b4fa-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="9b4fa-150">SET 命令 (例如 ``Set-CsTeamsClientConfiguration``) ：設定該類型的屬性。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="9b4fa-151">指定要修改的參數。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="9b4fa-152">您可以用兩種方式之一來參照要修改的組式：指定 - 身分識別 **全域**，或是按程式。 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``</span><span class="sxs-lookup"><span data-stu-id="9b4fa-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="9b4fa-153">每個系統管理員角色可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="9b4fa-153">What can each admin role do?</span></span>

<span data-ttu-id="9b4fa-154">請閱讀 [使用 Microsoft Teams 系統管理員角色來管理 Teams，](using-admin-roles.md) 以瞭解哪些系統管理員角色可以執行每個 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b4fa-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b4fa-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="9b4fa-155">Related topics</span></span>

[<span data-ttu-id="9b4fa-156">安裝 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b4fa-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="9b4fa-157">Teams PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="9b4fa-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="9b4fa-158">Teams Cmdlet 參照</span><span class="sxs-lookup"><span data-stu-id="9b4fa-158">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="9b4fa-159">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="9b4fa-159">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="9b4fa-160">使用 Teams 系統管理員角色來管理 Teams</span><span class="sxs-lookup"><span data-stu-id="9b4fa-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
