---
title: 使用 Microsoft 團隊 PowerShell 管理團隊
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
description: 瞭解如何使用團隊 PowerShell 管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944100"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="1a07f-103">使用 Microsoft 團隊 PowerShell 管理團隊</span><span class="sxs-lookup"><span data-stu-id="1a07f-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="1a07f-104">本文說明如何使用 Microsoft 團隊 PowerShell 來管理團隊及商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="1a07f-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="1a07f-105">請將本指南與[Microsoft 團隊 Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)及商務用[Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1a07f-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="1a07f-106">使用 PowerShell 建立及管理團隊</span><span class="sxs-lookup"><span data-stu-id="1a07f-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="1a07f-107">建立及管理團隊的 Cmdlet 位於[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。</span><span class="sxs-lookup"><span data-stu-id="1a07f-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="1a07f-108">團隊是由 Office 365 群組支援，因此當您建立小組時，就會建立群組。</span><span class="sxs-lookup"><span data-stu-id="1a07f-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="1a07f-109">提供一組 Cmdlet 來在核心團隊及其設定（ ``new-team`` 、 ``get-team`` 、 ``set-team`` ）、管理團隊使用者（、），以及 ``add-teamuser`` ``remove-teamuser`` 管理團隊通道（ ``new-teamchannel`` 、）的 Cmdlet ``remove-teamchannel`` 中進行操作。</span><span class="sxs-lookup"><span data-stu-id="1a07f-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="1a07f-110">所有這些 Cmdlet 都可以以使用者身分執行，但它們只能在您擁有或隸屬于您擁有的小組中運作。</span><span class="sxs-lookup"><span data-stu-id="1a07f-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="1a07f-111">如果您是全域系統管理員或團隊服務系統管理員，您就可以在組織中的所有團隊進行動作。</span><span class="sxs-lookup"><span data-stu-id="1a07f-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> <span data-ttu-id="1a07f-112">Microsoft 團隊 PowerShell 模組 Cmdlet 中使用的**GroupId**與 Exchange PowerShell 模組中傳回的身分**識別**屬性相同 ``Get-UnifiedGroup`` 。</span><span class="sxs-lookup"><span data-stu-id="1a07f-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="1a07f-113">透過 PowerShell 管理原則</span><span class="sxs-lookup"><span data-stu-id="1a07f-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="1a07f-114">商務用 Skype Online 連接器會整合成團隊 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a07f-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="1a07f-115">它目前可在公用預覽中取得。</span><span class="sxs-lookup"><span data-stu-id="1a07f-115">It is currently available in public preview.</span></span> <span data-ttu-id="1a07f-116">在時間裡，適用于團隊的商務用 Skype Online Cmdlet 會在團隊 PowerShell 模組中自行提供。</span><span class="sxs-lookup"><span data-stu-id="1a07f-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="1a07f-117">您可以在[安裝團隊 PowerShell](teams-powershell-install.md)文章中取得安裝步驟。</span><span class="sxs-lookup"><span data-stu-id="1a07f-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="1a07f-118">在您連線到商務用 Skype Online 之後，您的 PowerShell 會話中就會提供 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a07f-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="1a07f-119">如需詳細資訊，請參閱[使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1a07f-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="1a07f-120">在[商務用 Skype Cmdlet 模組](https://www.microsoft.com/download/details.aspx?id=39366)中尋找管理原則的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a07f-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="1a07f-121">原則是一組設定，可將它們精確套用至個別使用者。</span><span class="sxs-lookup"><span data-stu-id="1a07f-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="1a07f-122">每個原則類型都有自己的一組 Cmdlet，可用於建立、查看、刪除及更新原則，然後將這些原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1a07f-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="1a07f-123">一般結構如下：</span><span class="sxs-lookup"><span data-stu-id="1a07f-123">The general structure is:</span></span>

- <span data-ttu-id="1a07f-124">**取得**命令（例如， ``Get-CsTeamsMeetingPolicy`` ）：傳回您在組織中可指派的原則檔，包括由 Microsoft 建立的原則，以及您所建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="1a07f-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="1a07f-125">若只要尋找您在組織中建立的自訂原則，請使用 ``-Filter "tag:*"`` 。</span><span class="sxs-lookup"><span data-stu-id="1a07f-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="1a07f-126">**新**命令（例如 ``New-CsTeamsMeetingPolicy`` ）：為貴組織建立新的原則，以指派給貴組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="1a07f-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="1a07f-127">並非所有原則都支援建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="1a07f-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="1a07f-128">通常，這是為了確保您在組織中使用的原則具有受支援的設定組合。</span><span class="sxs-lookup"><span data-stu-id="1a07f-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="1a07f-129">**SET**命令（例如 ``Set-CsTeamsMeetingPolicy`` ）：設定指定原則上的特定值。</span><span class="sxs-lookup"><span data-stu-id="1a07f-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="1a07f-130">有些原則沒有可用的 SET 命令，或它們包含無法在原則中自訂的參數。</span><span class="sxs-lookup"><span data-stu-id="1a07f-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="1a07f-131">PowerShell 描述告訴您無法自訂哪些參數。</span><span class="sxs-lookup"><span data-stu-id="1a07f-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="1a07f-132">若要編輯預設將指派給貴組織中未指派自訂策略之使用者的原則，請執行 ``Set-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="1a07f-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="1a07f-133">**移除**命令（例如 ``Remove-CsTeamsMeetingPolicy`` ）：刪除已在您的租使用者中建立的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="1a07f-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="1a07f-134">如果您刪除已指派給貴組織中至少一個使用者的自訂原則，該使用者會回到全域原則。</span><span class="sxs-lookup"><span data-stu-id="1a07f-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="1a07f-135">您不能實際移除貴組織中的全域原則，但如果您想要將貴組織中的全域原則重設為 Microsoft 提供的預設設定，請執行 ``Remove-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="1a07f-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="1a07f-136">**GRANT**命令（例如 ``Grant-CsTeamsMeetingPolicy`` ）：指派原則給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="1a07f-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="1a07f-137">若要移除自訂原則指派，並讓使用者回到貴組織中的預設原則，請執行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。</span><span class="sxs-lookup"><span data-stu-id="1a07f-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="1a07f-138">並非所有原則都允許建立自訂原則，而且有些原則擁有您無法自訂的設定（所以您可以在與期間中查看設定，但不能設定自訂值 ``set-`` ``new-`` ）。</span><span class="sxs-lookup"><span data-stu-id="1a07f-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="1a07f-139">每個 Cmdlet 的檔都要指出是否可供客戶使用參數。</span><span class="sxs-lookup"><span data-stu-id="1a07f-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="1a07f-140">一般參數：</span><span class="sxs-lookup"><span data-stu-id="1a07f-140">Common parameters:</span></span>

- <span data-ttu-id="1a07f-141">身分**識別**：對於 ``Get-`` 、、 ``Set-`` ``New-`` 和 ``Remove-`` ，身分**識別**參數會永遠參照特定原則實例。</span><span class="sxs-lookup"><span data-stu-id="1a07f-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="1a07f-142">針對 ``Grant`` ，身分**識別**參數會參照要套用原則的特定使用者物件。</span><span class="sxs-lookup"><span data-stu-id="1a07f-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="1a07f-143">透過 PowerShell 管理設定</span><span class="sxs-lookup"><span data-stu-id="1a07f-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="1a07f-144">在[商務用 Skype Cmdlet 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中尋找管理您的設定的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a07f-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="1a07f-145">[配置] 是服務中維護的 [設定] 桶，不能在使用者層級指定。</span><span class="sxs-lookup"><span data-stu-id="1a07f-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="1a07f-146">設定總是在整個組織內套用。</span><span class="sxs-lookup"><span data-stu-id="1a07f-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="1a07f-147">您的全域設定是貴組織中的唯一有效配置。</span><span class="sxs-lookup"><span data-stu-id="1a07f-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="1a07f-148">每個配置類型都有兩個主要的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1a07f-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="1a07f-149">``Get-Cs<ConfigurationName>``（例如， ``Get-CsTeamsClientConfiguration`` ）：</span><span class="sxs-lookup"><span data-stu-id="1a07f-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="1a07f-150">SET 命令（例如 ``Set-CsTeamsClientConfiguration`` ）：設定該類型的配置中的屬性。</span><span class="sxs-lookup"><span data-stu-id="1a07f-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="1a07f-151">指定您要修改的參數。</span><span class="sxs-lookup"><span data-stu-id="1a07f-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="1a07f-152">您可以透過兩種方式的其中一種來參考您要修改的設定：指定**全域身分識別**，或執行 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。</span><span class="sxs-lookup"><span data-stu-id="1a07f-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="1a07f-153">每個管理員角色可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="1a07f-153">What can each admin role do?</span></span>

<span data-ttu-id="1a07f-154">[閱讀][使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md)，以瞭解哪些管理員角色可以執行每個 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a07f-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a07f-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="1a07f-155">Related topics</span></span>

[<span data-ttu-id="1a07f-156">安裝團隊 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a07f-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="1a07f-157">團隊 PowerShell 版本資訊</span><span class="sxs-lookup"><span data-stu-id="1a07f-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="1a07f-158">團隊 Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="1a07f-158">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="1a07f-159">商務用 Skype Cmdlet 參考</span><span class="sxs-lookup"><span data-stu-id="1a07f-159">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="1a07f-160">使用 Teams 系統管理員角色來管理 Teams</span><span class="sxs-lookup"><span data-stu-id="1a07f-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)