---
title: Lync Server 2013：測試觀察程式節點配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d2c79de4f86e490244ef63948c263d8f387fc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="40d9d-102">在 Lync Server 2013 中測試觀察程式節點配置</span><span class="sxs-lookup"><span data-stu-id="40d9d-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40d9d-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="40d9d-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40d9d-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="40d9d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="40d9d-105">日常</span><span class="sxs-lookup"><span data-stu-id="40d9d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40d9d-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="40d9d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="40d9d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="40d9d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40d9d-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="40d9d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="40d9d-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="40d9d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="40d9d-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsWatcherNodeConfiguration</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="40d9d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="40d9d-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="40d9d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="40d9d-112">描述</span><span class="sxs-lookup"><span data-stu-id="40d9d-112">Description</span></span>

<span data-ttu-id="40d9d-113">如果您使用 Microsoft System Center Operations Manager 來監視 Lync Server 2013，就可以選擇設定「觀察程式節點」：定期及自動執行綜合交易的電腦，以驗證 Lync Server 的運作方式正確.</span><span class="sxs-lookup"><span data-stu-id="40d9d-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="40d9d-114">系統會將觀察程式節點指派給 pool，並使用**CsWatcherNodeConfiguration** Cmdlet 進行管理。</span><span class="sxs-lookup"><span data-stu-id="40d9d-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="40d9d-115">請注意，如果您使用的是系統中心作業管理員，則不需要安裝觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="40d9d-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="40d9d-116">您仍可在不使用觀察程式節點的情況下監控您的系統。</span><span class="sxs-lookup"><span data-stu-id="40d9d-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="40d9d-117">唯一的差異是，您必須手動呼叫任何您想要執行的綜合交易，而不是由 Operations Manager 自動呼叫。</span><span class="sxs-lookup"><span data-stu-id="40d9d-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="40d9d-118">**CsWatcherNodeConfiguration** Cmdlet 可讓您確認已正確設定觀察程式節點，且指派給有效的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="40d9d-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="40d9d-119">請注意， **CsWatcherNodeConfiguration** Cmdlet 必須在 [觀察程式] 節點本身上執行。</span><span class="sxs-lookup"><span data-stu-id="40d9d-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="40d9d-120">無法針對遠端電腦執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="40d9d-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="40d9d-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="40d9d-121">Running the test</span></span>

<span data-ttu-id="40d9d-122">下列命令會驗證組織中使用的每個觀察程式節點的配置設定。</span><span class="sxs-lookup"><span data-stu-id="40d9d-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="40d9d-123">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="40d9d-123">Determining success or failure</span></span>

<span data-ttu-id="40d9d-124">下列成功的範例輸出顯示具有四個邊緣伺服器的系統。</span><span class="sxs-lookup"><span data-stu-id="40d9d-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="40d9d-125">對照拓朴驗證目標池 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="40d9d-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="40d9d-126">成功：在拓撲中存在目標池 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="40d9d-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="40d9d-127">成功：目標池 atl-cs-001.litwareinc.com 已安裝註冊機構角色。</span><span class="sxs-lookup"><span data-stu-id="40d9d-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="40d9d-128">成功：目標 pool atl-cs-001.litwareinc.com 是受支援的版本。</span><span class="sxs-lookup"><span data-stu-id="40d9d-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="40d9d-129">成功：5061目標池 atl-cs-001.litwareinc.com 的埠號碼正確無誤。</span><span class="sxs-lookup"><span data-stu-id="40d9d-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="40d9d-130">已啟動在 [觀察程式節點設定] 中檢查遺失的池。</span><span class="sxs-lookup"><span data-stu-id="40d9d-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="40d9d-131">如果偵測到任何錯誤，就會列印出來。</span><span class="sxs-lookup"><span data-stu-id="40d9d-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="40d9d-132">在觀察程式節點設定中檢查遺失的池已完成。</span><span class="sxs-lookup"><span data-stu-id="40d9d-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="40d9d-133">檢查已啟動由觀察程式節點安裝所建立的觀察程式節點登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="40d9d-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="40d9d-134">如果偵測到任何錯誤，就會列印出來。</span><span class="sxs-lookup"><span data-stu-id="40d9d-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="40d9d-135">檢查由觀察程式節點安裝所建立的觀察程式節點登錄機碼已完成。</span><span class="sxs-lookup"><span data-stu-id="40d9d-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="40d9d-136">偵測到驗證類型為 [協商]。</span><span class="sxs-lookup"><span data-stu-id="40d9d-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="40d9d-137">已成功驗證測試使用者的認證 sip 是否存在： user1@ atl-cs-001.litwareinc.com 認證管理儲存區中。</span><span class="sxs-lookup"><span data-stu-id="40d9d-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="40d9d-138">已成功驗證測試使用者的認證 sip 是否存在： user2@ atl-cs-001.litwareinc.com 認證管理儲存區中。</span><span class="sxs-lookup"><span data-stu-id="40d9d-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="40d9d-139">已啟動在 [觀察程式節點設定] 中檢查遺失的池。</span><span class="sxs-lookup"><span data-stu-id="40d9d-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="40d9d-140">如果偵測到任何錯誤，就會列印出來。</span><span class="sxs-lookup"><span data-stu-id="40d9d-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="40d9d-141">警告： Pool atl-cs-001.litwareinc.com 有註冊機構</span><span class="sxs-lookup"><span data-stu-id="40d9d-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="40d9d-142">已安裝角色，但沒有為其設定的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="40d9d-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="40d9d-143">在觀察程式節點設定中檢查遺失的池已完成。</span><span class="sxs-lookup"><span data-stu-id="40d9d-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="40d9d-144">檢查由觀察程式節點安裝所建立的觀察程式節點登錄機碼，是</span><span class="sxs-lookup"><span data-stu-id="40d9d-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="40d9d-145">起步.</span><span class="sxs-lookup"><span data-stu-id="40d9d-145">started.</span></span> <span data-ttu-id="40d9d-146">如果偵測到任何錯誤，就會列印出來。</span><span class="sxs-lookup"><span data-stu-id="40d9d-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="40d9d-147">CsWatcherNodeConfiguration：在下列情況中找不到健康情況登錄機碼</span><span class="sxs-lookup"><span data-stu-id="40d9d-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="40d9d-148">軟體\\Microsoft\\即時通訊。</span><span class="sxs-lookup"><span data-stu-id="40d9d-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="40d9d-149">請確定 [觀察程式] 節點為 [msi]</span><span class="sxs-lookup"><span data-stu-id="40d9d-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="40d9d-150">安裝正確。</span><span class="sxs-lookup"><span data-stu-id="40d9d-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="40d9d-151">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="40d9d-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="40d9d-152">以下是**測試 CsWatcherNodeConfiguration**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="40d9d-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="40d9d-153">未正確安裝 [觀察程式] 節點。</span><span class="sxs-lookup"><span data-stu-id="40d9d-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="40d9d-154">未設定測試使用者。</span><span class="sxs-lookup"><span data-stu-id="40d9d-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40d9d-155">請參閱</span><span class="sxs-lookup"><span data-stu-id="40d9d-155">See Also</span></span>


[<span data-ttu-id="40d9d-156">CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="40d9d-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="40d9d-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="40d9d-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="40d9d-158">移除-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="40d9d-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="40d9d-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="40d9d-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

