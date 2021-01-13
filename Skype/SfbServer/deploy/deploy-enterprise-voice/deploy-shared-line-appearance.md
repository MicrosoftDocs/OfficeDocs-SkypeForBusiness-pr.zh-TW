---
title: 在商務用 Skype Server 2015 中部署共用線外觀
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 閱讀此主題以瞭解如何在商務用 Skype Server 2015，2015累計更新中，部署共用線外觀 (SLA) 。 SLA 是一種功能，可用於處理特定號碼（稱為共用號碼）上的多個通話。
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812403"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="9fdd6-104">在商務用 Skype Server 2015 中部署共用線外觀</span><span class="sxs-lookup"><span data-stu-id="9fdd6-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="9fdd6-105">閱讀此主題以瞭解如何在商務用 Skype Server 2015，2015累計更新中，部署共用線外觀 (SLA) 。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="9fdd6-106">SLA 是一種功能，可用於處理特定號碼（稱為共用號碼）上的多個通話。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="9fdd6-107">如需此功能的相關資訊，請參閱 [在商務用 Skype Server 2015 中規劃共用行的外觀](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="9fdd6-108">共用線外觀 (SLA) 是商務用 Skype Server 中的新功能（2015年11月累積更新）。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="9fdd6-109">若要啟用此功能，您必須先部署此累計更新。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="9fdd6-110">安裝共用線路外觀</span><span class="sxs-lookup"><span data-stu-id="9fdd6-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="9fdd6-111">在商務用 Skype Server 後，已部署11月2015累計更新，請  `SkypeServerUpdateInstaller.exe` 在集區中的每一部前端伺服器上執行修補程式。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="9fdd6-112">安裝程式將會部署最新版本的 SLA 應用程式，但預設不會啟用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="9fdd6-113">遵循下列所述的步驟來啟用它：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="9fdd6-114">a.</span><span class="sxs-lookup"><span data-stu-id="9fdd6-114">a.</span></span> <span data-ttu-id="9fdd6-115">針對每個集區執行下列命令，將 SLA 註冊成伺服器應用程式：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="9fdd6-116">其中，% FQDN% 是集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="9fdd6-117">b.</span><span class="sxs-lookup"><span data-stu-id="9fdd6-117">b.</span></span> <span data-ttu-id="9fdd6-118">執行下列命令，更新 SLA Cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="9fdd6-119">c.</span><span class="sxs-lookup"><span data-stu-id="9fdd6-119">c.</span></span> <span data-ttu-id="9fdd6-120">在所有已安裝並啟用 SLA 的集區中，重新開機所有前端伺服器 (RTCSRV 服務) ：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="9fdd6-121">建立 SLA 群組並新增使用者</span><span class="sxs-lookup"><span data-stu-id="9fdd6-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="9fdd6-122">使用 [CsSlaConfiguration 指令程式](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) 建立 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="9fdd6-123">Set-CsSlaConfiguration Cmdlet 會將 Enterprise Voice 帳戶 SLAGroup1 標示為 SLA 實體，SLAGroup1 數目會變成 SLA 群組的數目。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="9fdd6-124">所有對 SLAGroup1 的呼叫都會撥打整個 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="9fdd6-125">下列範例會為現有的 Enterprise Voice user 和 SLAGroup1 建立 SLA 群組，並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="9fdd6-126">此命令會將新 SLA 群組的並行通話數目上限設定為3，並讓來電超過該限制，以聽到忙碌的信號：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="9fdd6-127">您可以使用 Set-CsSlaConfiguration 建立新的 SLA 群組或修改現有的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fdd6-128">請注意，您指定的  `-Identity` 必須是有效的現有企業語音使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="9fdd6-129">使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) Cmdlet 將委派新增至群組：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="9fdd6-130">下列範例會將使用者新增至 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="9fdd6-131">新增至群組的每個使用者都必須是有效的企業語音啟用使用者：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="9fdd6-132">針對您要新增至群組的每個使用者重複此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="9fdd6-133">使用者只能屬於單一的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="9fdd6-134">設定 SLA 群組忙碌選項</span><span class="sxs-lookup"><span data-stu-id="9fdd6-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="9fdd6-135">使用 [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) Cmdlet 來設定 SLA 群組忙碌選項：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="9fdd6-136">下列範例會將超過最大同時呼叫數目轉接的來電設定為電話號碼202-555-1234。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="9fdd6-137">目標可以是您組織中的使用者，而不是電話號碼;在此情況下，接收轉寄呼叫的使用者語法與您指定代理人時的語法相同：  `sip:<NameofDelegate@domain>` 。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="9fdd6-138">的其他可能的參數  `BusyOption` 為 `Voicemail` ：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="9fdd6-139">設定 SLA 群組未接來電選項</span><span class="sxs-lookup"><span data-stu-id="9fdd6-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="9fdd6-140">使用 [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) Cmdlet 來設定 SLA 群組未接來電選項：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="9fdd6-141">下列範例會指定將未接來電轉寄給名為的使用者  `sla_forward_number` 。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="9fdd6-142">參數的有效選項  `-MissedCallOption` 是 `Forward` 、  `BusySignal` 或  `Disconnect` 。</span><span class="sxs-lookup"><span data-stu-id="9fdd6-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="9fdd6-143">如果您選擇  `Forward` ，您也必須包含  `-MissedCallForwardTarget` 參數，並以使用者或電話號碼做為目標：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="9fdd6-144">從群組中移除代理人</span><span class="sxs-lookup"><span data-stu-id="9fdd6-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="9fdd6-145">使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) Cmdlet 從群組中移除委派：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="9fdd6-146">例如：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="9fdd6-147">刪除 SLA 群組</span><span class="sxs-lookup"><span data-stu-id="9fdd6-147">Delete an SLA group</span></span>

- <span data-ttu-id="9fdd6-148">使用 [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="9fdd6-149">例如：</span><span class="sxs-lookup"><span data-stu-id="9fdd6-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


