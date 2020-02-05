---
title: 在商務用 Skype Server 2015 中部署共用線外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 請閱讀本主題，瞭解如何在商務用 Skype Server 2015 （2015年11月累計更新）中部署共用線條外觀（SLA）。 SLA 是一項功能，可在稱為共用號碼的特定號碼上處理多個通話。
ms.openlocfilehash: c9c4eef43de2f03be32e92c23e8384020e24b099
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767506"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="d18c0-104">在商務用 Skype Server 2015 中部署共用線外觀</span><span class="sxs-lookup"><span data-stu-id="d18c0-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="d18c0-105">請閱讀本主題，瞭解如何在商務用 Skype Server 2015 （2015年11月累計更新）中部署共用線條外觀（SLA）。</span><span class="sxs-lookup"><span data-stu-id="d18c0-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d18c0-106">SLA 是一項功能，可在稱為共用號碼的特定號碼上處理多個通話。</span><span class="sxs-lookup"><span data-stu-id="d18c0-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="d18c0-107">如需此功能的詳細資訊，請參閱[在商務用 Skype Server 2015 中規劃共用線外觀](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="d18c0-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="d18c0-108">共用線外觀（SLA）是商務用 Skype Server 中的新功能，2015年11月累計更新。</span><span class="sxs-lookup"><span data-stu-id="d18c0-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d18c0-109">若要啟用此功能，您必須先部署此累積更新。</span><span class="sxs-lookup"><span data-stu-id="d18c0-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="d18c0-110">安裝共用線條外觀</span><span class="sxs-lookup"><span data-stu-id="d18c0-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="d18c0-111">在商務用 Skype Server 之後，已部署2015年11月累計更新`SkypeServerUpdateInstaller.exe` ，請在池中的每個前端伺服器上執行修補程式。</span><span class="sxs-lookup"><span data-stu-id="d18c0-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="d18c0-112">安裝程式將會部署最新版本的 SLA 應用程式，但是預設不會啟用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="d18c0-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="d18c0-113">您可以依照以下所述的步驟啟用：</span><span class="sxs-lookup"><span data-stu-id="d18c0-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="d18c0-114">是.</span><span class="sxs-lookup"><span data-stu-id="d18c0-114">a.</span></span> <span data-ttu-id="d18c0-115">針對每個池執行下列命令，以伺服器應用程式的方式來註冊 SLA：</span><span class="sxs-lookup"><span data-stu-id="d18c0-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="d18c0-116">其中% FQDN% 是該池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="d18c0-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="d18c0-117">乙.</span><span class="sxs-lookup"><span data-stu-id="d18c0-117">b.</span></span> <span data-ttu-id="d18c0-118">執行下列命令以更新 SLA Cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="d18c0-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="d18c0-119">c-clip.</span><span class="sxs-lookup"><span data-stu-id="d18c0-119">c.</span></span> <span data-ttu-id="d18c0-120">在已安裝並啟用 SLA 的所有池中，重新開機所有前端伺服器（RTCSRV 服務）：</span><span class="sxs-lookup"><span data-stu-id="d18c0-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="d18c0-121">建立 SLA 群組並新增使用者</span><span class="sxs-lookup"><span data-stu-id="d18c0-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="d18c0-122">使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) CMDLET 建立 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="d18c0-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="d18c0-123">CsSlaConfiguration Cmdlet 會將企業語音帳戶 SLAGroup1 為 SLA 實體，而 SLAGroup1 的數量會成為 SLA 群組的數位。</span><span class="sxs-lookup"><span data-stu-id="d18c0-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="d18c0-124">SLAGroup1 的所有呼叫都會撥打整個 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="d18c0-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="d18c0-125">下列範例會建立現有企業語音使用者的 SLA 群組，SLAGroup1，並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。</span><span class="sxs-lookup"><span data-stu-id="d18c0-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="d18c0-126">此命令會將新 SLA 群組的最大併發呼叫數量設為3，並將超過該限制的通話數設定為聽到占線信號：</span><span class="sxs-lookup"><span data-stu-id="d18c0-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="d18c0-127">您可以使用 [設定] CsSlaConfiguration 來建立新的 SLA 群組或修改現有的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="d18c0-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d18c0-128">請注意，您指定的`-Identity`內容必須是有效的現有企業語音使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d18c0-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="d18c0-129">使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) Cmdlet 在群組中新增代理人：</span><span class="sxs-lookup"><span data-stu-id="d18c0-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="d18c0-130">下列範例會將使用者新增至 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="d18c0-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="d18c0-131">新增至群組的每個使用者都必須是有效的企業語音使用者：</span><span class="sxs-lookup"><span data-stu-id="d18c0-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="d18c0-132">針對您要新增到群組的每個使用者重複此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d18c0-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="d18c0-133">使用者只能屬於單一的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="d18c0-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="d18c0-134">設定 SLA 群組 Busy 選項</span><span class="sxs-lookup"><span data-stu-id="d18c0-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="d18c0-135">使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)SLA 群組 Busy 選項：</span><span class="sxs-lookup"><span data-stu-id="d18c0-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="d18c0-136">下列範例會將超過最大併發呼叫數的來電轉接到電話號碼202-555-1234。</span><span class="sxs-lookup"><span data-stu-id="d18c0-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="d18c0-137">目標可能是貴組織中的使用者，而不是電話號碼;在這種情況下，收件者接收轉寄來電的語法就與您指定代理人的方式相同： `sip:<NameofDelegate@domain>`。</span><span class="sxs-lookup"><span data-stu-id="d18c0-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="d18c0-138">其他可能的參數`BusyOption`為： `Voicemail`</span><span class="sxs-lookup"><span data-stu-id="d18c0-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="d18c0-139">設定 SLA 群組 [未接來電] 選項</span><span class="sxs-lookup"><span data-stu-id="d18c0-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="d18c0-140">使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)SLA 群組未接來電選項：</span><span class="sxs-lookup"><span data-stu-id="d18c0-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="d18c0-141">下列範例指定將未接來電轉寄給名為`sla_forward_number`的使用者。</span><span class="sxs-lookup"><span data-stu-id="d18c0-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="d18c0-142">`-MissedCallOption`參數的有效選項為`Forward`、 `BusySignal`或`Disconnect`。</span><span class="sxs-lookup"><span data-stu-id="d18c0-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="d18c0-143">如果您選擇`Forward`，您也必須包含`-MissedCallForwardTarget`參數，並將使用者或電話號碼做為目標：</span><span class="sxs-lookup"><span data-stu-id="d18c0-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="d18c0-144">從群組中移除代理人</span><span class="sxs-lookup"><span data-stu-id="d18c0-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="d18c0-145">使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) Cmdlet 移除群組中的代理人：</span><span class="sxs-lookup"><span data-stu-id="d18c0-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="d18c0-146">例如：</span><span class="sxs-lookup"><span data-stu-id="d18c0-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="d18c0-147">刪除 SLA 群組</span><span class="sxs-lookup"><span data-stu-id="d18c0-147">Delete an SLA group</span></span>

- <span data-ttu-id="d18c0-148">使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="d18c0-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="d18c0-149">例如：</span><span class="sxs-lookup"><span data-stu-id="d18c0-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


