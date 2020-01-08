---
title: Lync Server 2013：部署共用線條外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da81073fc239822a682f926e1b782c8555153bf6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40975846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="ebf4d-102">在 Lync Server 2013 中部署共用線條外觀</span><span class="sxs-lookup"><span data-stu-id="ebf4d-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebf4d-103">_**主題上次修改日期：** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="ebf4d-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="ebf4d-104">請閱讀本主題，瞭解如何在 Lync Server 2013 中部署共用線條外觀（SLA），累加更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="ebf4d-105">SLA 是一項功能，可在稱為共用號碼的特定號碼上處理多個通話。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="ebf4d-106">如需此功能的詳細資訊，請參閱[Lync Server 2013 中的共用線條外觀規劃](lync-server-2013-plan-for-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="ebf4d-107">共用線路外觀（SLA）是 Lync Server 2013 中的新功能，累積更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="ebf4d-108">若要啟用此功能，您必須先部署此累積更新。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="ebf4d-109">安裝共用線條外觀</span><span class="sxs-lookup"><span data-stu-id="ebf4d-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="ebf4d-110">在 Lync Server 2013 之後，將部署 4 2016 月的累計更新，且預設不會啟用 SLA 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="ebf4d-111">若要啟用應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="ebf4d-112">針對每個池執行下列命令，以伺服器應用程式的方式來註冊 SLA：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="ebf4d-113">其中% FQDN% 是該池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="ebf4d-114">執行下列命令以更新 SLA Cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="ebf4d-115">在已安裝並啟用 SLA 的所有池中，重新開機所有前端伺服器（RTCSRV 服務）：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="ebf4d-116">建立 SLA 群組並新增使用者</span><span class="sxs-lookup"><span data-stu-id="ebf4d-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="ebf4d-117">使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 建立 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="ebf4d-118">CsSlaConfiguration Cmdlet 會將企業語音帳戶 SLAGroup1 為 SLA 實體，而 SLAGroup1 的數量會成為 SLA 群組的數位。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-118">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="ebf4d-119">SLAGroup1 的所有呼叫都會撥打整個 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-119">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="ebf4d-120">下列範例會建立現有企業語音使用者的 SLA 群組，SLAGroup1，並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="ebf4d-121">此命令會將新 SLA 群組的最大併發呼叫數量設為3，並將超過該限制的通話數設定為聽到占線信號：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="ebf4d-122">您可以使用 [設定] CsSlaConfiguration 來建立新的 SLA 群組或修改現有的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebf4d-123">請注意，您指定的<CODE>-Identity</CODE>內容必須是有效的現有企業語音使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="ebf4d-124">使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) Cmdlet 在群組中新增代理人：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="ebf4d-125">下列範例會將使用者新增至 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="ebf4d-126">新增至群組的每個使用者都必須是有效的企業語音使用者：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="ebf4d-127">針對您要新增到群組的每個使用者重複此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-127">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="ebf4d-128">使用者只能屬於單一的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-128">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="ebf4d-129">設定 SLA 群組 Busy 選項</span><span class="sxs-lookup"><span data-stu-id="ebf4d-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="ebf4d-130">使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)SLA 群組 Busy 選項：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="ebf4d-131">下列範例會將超過最大併發呼叫數的來電轉接到電話號碼202-555-1234。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="ebf4d-132">目標可能是貴組織中的使用者，而不是電話號碼;在這種情況下，收件者接收轉寄來電的語法就與您指定代理人的方式相同： `sip:<NameofDelegate@domain>`。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="ebf4d-133">其他可能的參數`BusyOption`為： `Voicemail`</span><span class="sxs-lookup"><span data-stu-id="ebf4d-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="ebf4d-134">設定 SLA 群組 [未接來電] 選項</span><span class="sxs-lookup"><span data-stu-id="ebf4d-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="ebf4d-135">使用[CsSlaConfiguration Cmdlet 設定](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration)SLA 群組未接來電選項：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="ebf4d-136">下列範例指定將未接來電轉寄給名為`sla_forward_number`的使用者。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="ebf4d-137">`-MissedCallOption`參數的有效選項為`Forward`、 `BusySignal`或`Disconnect`。</span><span class="sxs-lookup"><span data-stu-id="ebf4d-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="ebf4d-138">如果您選擇`Forward`，您也必須包含`-MissedCallForwardTarget`參數，並將使用者或電話號碼做為目標：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="ebf4d-139">從群組中移除代理人</span><span class="sxs-lookup"><span data-stu-id="ebf4d-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="ebf4d-140">使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) Cmdlet 移除群組中的代理人：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="ebf4d-141">例如：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="ebf4d-142">刪除 SLA 群組</span><span class="sxs-lookup"><span data-stu-id="ebf4d-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="ebf4d-143">使用[CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="ebf4d-144">例如：</span><span class="sxs-lookup"><span data-stu-id="ebf4d-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

