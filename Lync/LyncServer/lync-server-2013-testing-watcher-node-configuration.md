---
title: Lync Server 2013：測試監視器節點設定
description: Lync Server 2013：測試監視器節點設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546839"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="17b80-103">在 Lync Server 2013 中測試監視器節點設定</span><span class="sxs-lookup"><span data-stu-id="17b80-103">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17b80-104">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="17b80-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17b80-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="17b80-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="17b80-106">每日</span><span class="sxs-lookup"><span data-stu-id="17b80-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17b80-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="17b80-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="17b80-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17b80-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17b80-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="17b80-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="17b80-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="17b80-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="17b80-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsWatcherNodeConfiguration</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="17b80-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="17b80-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="17b80-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="17b80-113">描述</span><span class="sxs-lookup"><span data-stu-id="17b80-113">Description</span></span>

<span data-ttu-id="17b80-114">如果您使用 Microsoft System Center Operations Manager 來監視 Lync Server 2013，您可以選擇設定「觀察程式節點」：定期及自動執行綜合交易的電腦，以驗證 Lync Server 是否如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="17b80-114">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="17b80-115">觀察程式節點會指派給集區，並使用 **CsWatcherNodeConfiguration** Cmdlet 進行管理。</span><span class="sxs-lookup"><span data-stu-id="17b80-115">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="17b80-116">請注意，如果您使用 System Center Operations Manager，便不需要安裝觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="17b80-116">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="17b80-117">您仍可監控系統，而不需要使用監視程式節點。</span><span class="sxs-lookup"><span data-stu-id="17b80-117">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="17b80-118">唯一不同之處在于，您要執行的任何綜合交易都必須手動呼叫，而不是由 Operations Manager 自動呼叫。</span><span class="sxs-lookup"><span data-stu-id="17b80-118">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="17b80-119">**Test-CsWatcherNodeConfiguration** Cmdlet 可讓您確認是否已正確設定或指派給有效的 Lync Server 2013 集區的監看員節點。</span><span class="sxs-lookup"><span data-stu-id="17b80-119">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="17b80-120">請注意，必須在監看員節點本身上執行 **Test-CsWatcherNodeConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="17b80-120">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="17b80-121">無法對遠端電腦執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="17b80-121">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="17b80-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="17b80-122">Running the test</span></span>

<span data-ttu-id="17b80-123">下列命令會驗證組織中所使用之每個監看員節點的設定設定。</span><span class="sxs-lookup"><span data-stu-id="17b80-123">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="17b80-124">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="17b80-124">Determining success or failure</span></span>

<span data-ttu-id="17b80-125">下列成功的範例輸出會顯示具有四部 edge 伺服器的系統。</span><span class="sxs-lookup"><span data-stu-id="17b80-125">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="17b80-126">對照拓撲驗證目標集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="17b80-126">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="17b80-127">成功：目標集區 atl-cs-001.litwareinc.com 存在於拓撲中。</span><span class="sxs-lookup"><span data-stu-id="17b80-127">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="17b80-128">成功：目標集區 atl-cs-001.litwareinc.com 已安裝註冊機構角色。</span><span class="sxs-lookup"><span data-stu-id="17b80-128">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="17b80-129">成功：目標集區 atl-cs-001.litwareinc.com 為支援的版本。</span><span class="sxs-lookup"><span data-stu-id="17b80-129">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="17b80-130">成功：5061目標集區 atl-cs-001.litwareinc.com 的埠號碼是正確的。</span><span class="sxs-lookup"><span data-stu-id="17b80-130">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="17b80-131">已啟動在觀察者節點設定中檢查遺失的集區。</span><span class="sxs-lookup"><span data-stu-id="17b80-131">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="17b80-132">如果偵測到任何錯誤，就會將它列印出來。</span><span class="sxs-lookup"><span data-stu-id="17b80-132">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="17b80-133">在觀察者節點設定中檢查遺失的集區已完成。</span><span class="sxs-lookup"><span data-stu-id="17b80-133">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="17b80-134">已啟動透過檢查監視節點安裝所建立的監看員節點登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="17b80-134">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="17b80-135">如果偵測到任何錯誤，就會將它列印出來。</span><span class="sxs-lookup"><span data-stu-id="17b80-135">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="17b80-136">檢查監視節點安裝所建立的監看員節點登錄機碼已完成。</span><span class="sxs-lookup"><span data-stu-id="17b80-136">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="17b80-137">偵測到驗證類型為 [協商]。</span><span class="sxs-lookup"><span data-stu-id="17b80-137">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="17b80-138">已成功驗證測試使用者的身分憑證 sip 是否存在： user1@ atl-cs-001.litwareinc.com in 認證管理存放區。</span><span class="sxs-lookup"><span data-stu-id="17b80-138">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="17b80-139">已成功驗證測試使用者的身分憑證 sip 是否存在： user2@ atl-cs-001.litwareinc.com in 認證管理存放區。</span><span class="sxs-lookup"><span data-stu-id="17b80-139">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="17b80-140">已啟動在觀察者節點設定中檢查遺失的集區。</span><span class="sxs-lookup"><span data-stu-id="17b80-140">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="17b80-141">如果偵測到任何錯誤，就會將它列印出來。</span><span class="sxs-lookup"><span data-stu-id="17b80-141">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="17b80-142">警告：集區 atl-cs-001.litwareinc.com 有註冊機構</span><span class="sxs-lookup"><span data-stu-id="17b80-142">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="17b80-143">已安裝角色，但沒有為其設定的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="17b80-143">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="17b80-144">在觀察者節點設定中檢查遺失的集區已完成。</span><span class="sxs-lookup"><span data-stu-id="17b80-144">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="17b80-145">檢查監視節點安裝所建立的監看員節點登錄機碼，是</span><span class="sxs-lookup"><span data-stu-id="17b80-145">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="17b80-146">開始。</span><span class="sxs-lookup"><span data-stu-id="17b80-146">started.</span></span> <span data-ttu-id="17b80-147">如果偵測到任何錯誤，就會將它列印出來。</span><span class="sxs-lookup"><span data-stu-id="17b80-147">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="17b80-148">Test-CsWatcherNodeConfiguration：在中找不到健康情況登錄機碼</span><span class="sxs-lookup"><span data-stu-id="17b80-148">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="17b80-149">軟體 \\ Microsoft \\ 即時通訊。</span><span class="sxs-lookup"><span data-stu-id="17b80-149">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="17b80-150">確定 [監看員] 節點 .msi 是</span><span class="sxs-lookup"><span data-stu-id="17b80-150">Make sure watcher node .msi is</span></span>

<span data-ttu-id="17b80-151">正確安裝。</span><span class="sxs-lookup"><span data-stu-id="17b80-151">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="17b80-152">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="17b80-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="17b80-153">以下是一些 **Test-CsWatcherNodeConfiguration** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="17b80-153">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="17b80-154">未正確安裝觀察器節點。</span><span class="sxs-lookup"><span data-stu-id="17b80-154">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="17b80-155">未設定測試使用者。</span><span class="sxs-lookup"><span data-stu-id="17b80-155">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17b80-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17b80-156">See Also</span></span>


[<span data-ttu-id="17b80-157">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="17b80-157">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="17b80-158">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="17b80-158">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="17b80-159">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="17b80-159">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="17b80-160">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="17b80-160">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

