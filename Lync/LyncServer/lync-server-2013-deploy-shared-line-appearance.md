---
title: Lync Server 2013：部署共用線路外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d0bffd92c4c2e2448938c467eec73c9bab1a94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531410"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="0d47b-102">在 Lync Server 2013 中部署共用線路外觀</span><span class="sxs-lookup"><span data-stu-id="0d47b-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d47b-103">_**主題上次修改日期：** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="0d47b-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="0d47b-104">閱讀此主題以瞭解如何在 Lync Server 2013 中 (SLA) 部署共用行外觀，累積更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="0d47b-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="0d47b-105">SLA 是一種功能，可用於處理特定號碼（稱為共用號碼）上的多個通話。</span><span class="sxs-lookup"><span data-stu-id="0d47b-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="0d47b-106">如需此功能的相關資訊，請參閱 [在 Lync Server 2013 中規劃共用行外觀](lync-server-2013-plan-for-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="0d47b-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="0d47b-107">共用線路外觀 (SLA) 是 Lync Server 2013 中的新功能，累積更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="0d47b-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="0d47b-108">若要啟用此功能，您必須先部署此累計更新。</span><span class="sxs-lookup"><span data-stu-id="0d47b-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="0d47b-109">安裝共用線路外觀</span><span class="sxs-lookup"><span data-stu-id="0d47b-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="0d47b-110">在 Lync Server 2013 中，部署了累計更新4月2016，預設不會啟用 SLA 應用程式。</span><span class="sxs-lookup"><span data-stu-id="0d47b-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="0d47b-111">若要啟用此應用程式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0d47b-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="0d47b-112">針對每個集區執行下列命令，將 SLA 註冊成伺服器應用程式：</span><span class="sxs-lookup"><span data-stu-id="0d47b-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="0d47b-113">其中，% FQDN% 是集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="0d47b-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="0d47b-114">執行下列命令，更新 SLA Cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="0d47b-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="0d47b-115">在所有已安裝並啟用 SLA 的集區中，重新開機所有前端伺服器 (RTCSRV 服務) ：</span><span class="sxs-lookup"><span data-stu-id="0d47b-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="0d47b-116">建立 SLA 群組並新增使用者</span><span class="sxs-lookup"><span data-stu-id="0d47b-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="0d47b-117">使用 [CsSlaConfiguration 指令程式](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) 建立 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="0d47b-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="0d47b-118">Set-CsSlaConfiguration Cmdlet 會將 Enterprise Voice 帳戶 SLAGroup1 標示為 SLA 實體，SLAGroup1 數目會變成 SLA 群組的數目。</span><span class="sxs-lookup"><span data-stu-id="0d47b-118">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="0d47b-119">所有對 SLAGroup1 的呼叫都會撥打整個 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="0d47b-119">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="0d47b-120">下列範例會為現有的 Enterprise Voice user 和 SLAGroup1 建立 SLA 群組，並使用指派給 SLAGroup1 的號碼做為 SLA 主線編號。</span><span class="sxs-lookup"><span data-stu-id="0d47b-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="0d47b-121">此命令會將新 SLA 群組的並行通話數目上限設定為3，並讓來電超過該限制，以聽到忙碌的信號：</span><span class="sxs-lookup"><span data-stu-id="0d47b-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="0d47b-122">您可以使用 Set-CsSlaConfiguration 建立新的 SLA 群組或修改現有的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="0d47b-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0d47b-123">請注意，您指定的 <CODE>-Identity</CODE> 必須是有效的現有企業語音使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0d47b-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="0d47b-124">使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) Cmdlet 將委派新增至群組：</span><span class="sxs-lookup"><span data-stu-id="0d47b-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="0d47b-125">下列範例會將使用者新增至 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="0d47b-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="0d47b-126">新增至群組的每個使用者都必須是有效的企業語音啟用使用者：</span><span class="sxs-lookup"><span data-stu-id="0d47b-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="0d47b-127">針對您要新增至群組的每個使用者重複此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d47b-127">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="0d47b-128">使用者只能屬於單一的 SLA 群組。</span><span class="sxs-lookup"><span data-stu-id="0d47b-128">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="0d47b-129">設定 SLA 群組忙碌選項</span><span class="sxs-lookup"><span data-stu-id="0d47b-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="0d47b-130">使用 [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) Cmdlet 來設定 SLA 群組忙碌選項：</span><span class="sxs-lookup"><span data-stu-id="0d47b-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="0d47b-131">下列範例會將超過最大同時呼叫數目轉接的來電設定為電話號碼202-555-1234。</span><span class="sxs-lookup"><span data-stu-id="0d47b-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="0d47b-132">目標可以是您組織中的使用者，而不是電話號碼;在此情況下，接收轉寄呼叫的使用者語法與您指定代理人時的語法相同： `sip:<NameofDelegate@domain>` 。</span><span class="sxs-lookup"><span data-stu-id="0d47b-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="0d47b-133">的其他可能的參數 `BusyOption` 為 `Voicemail` ：</span><span class="sxs-lookup"><span data-stu-id="0d47b-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="0d47b-134">設定 SLA 群組未接來電選項</span><span class="sxs-lookup"><span data-stu-id="0d47b-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="0d47b-135">使用 [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) Cmdlet 來設定 SLA 群組未接來電選項：</span><span class="sxs-lookup"><span data-stu-id="0d47b-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="0d47b-136">下列範例會指定將未接來電轉寄給名為的使用者 `sla_forward_number` 。</span><span class="sxs-lookup"><span data-stu-id="0d47b-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="0d47b-137">參數的有效選項 `-MissedCallOption` 是 `Forward` 、 `BusySignal` 或 `Disconnect` 。</span><span class="sxs-lookup"><span data-stu-id="0d47b-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="0d47b-138">如果您選擇 `Forward` ，您也必須包含 `-MissedCallForwardTarget` 參數，並以使用者或電話號碼做為目標：</span><span class="sxs-lookup"><span data-stu-id="0d47b-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="0d47b-139">從群組中移除代理人</span><span class="sxs-lookup"><span data-stu-id="0d47b-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="0d47b-140">使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) Cmdlet 從群組中移除委派：</span><span class="sxs-lookup"><span data-stu-id="0d47b-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="0d47b-141">例如：</span><span class="sxs-lookup"><span data-stu-id="0d47b-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="0d47b-142">刪除 SLA 群組</span><span class="sxs-lookup"><span data-stu-id="0d47b-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="0d47b-143">使用 [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 刪除 SLA 群組：</span><span class="sxs-lookup"><span data-stu-id="0d47b-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="0d47b-144">例如：</span><span class="sxs-lookup"><span data-stu-id="0d47b-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

