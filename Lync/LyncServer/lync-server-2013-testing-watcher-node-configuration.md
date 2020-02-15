---
title: Lync Server 2013： 測試監看員節點組態
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
ms.openlocfilehash: a8d0fe8500bd676ef1a9a33c9197dfeac7783c10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="57bb2-102">Lync Server 2013 中的測試監看員節點組態</span><span class="sxs-lookup"><span data-stu-id="57bb2-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57bb2-103">_**上次修改主題：** 2014年-11-03_</span><span class="sxs-lookup"><span data-stu-id="57bb2-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57bb2-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="57bb2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="57bb2-105">每日</span><span class="sxs-lookup"><span data-stu-id="57bb2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57bb2-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="57bb2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="57bb2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="57bb2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57bb2-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="57bb2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="57bb2-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="57bb2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="57bb2-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-cswatchernodeconfiguration</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="57bb2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="57bb2-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="57bb2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="57bb2-112">描述</span><span class="sxs-lookup"><span data-stu-id="57bb2-112">Description</span></span>

<span data-ttu-id="57bb2-113">如果您使用 Microsoft System Center Operations Manager 監視 Lync Server 2013，則您可以設定 「 監看員節點 」 的選擇： 定期，並自動執行綜合交易，若要驗證為正常到 Lync Server 的電腦預期的。</span><span class="sxs-lookup"><span data-stu-id="57bb2-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="57bb2-114">監看員節點指派給集區]，並使用**CsWatcherNodeConfiguration** cmdlet 所管理。</span><span class="sxs-lookup"><span data-stu-id="57bb2-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="57bb2-115">請注意，您不需要安裝監看員節點，如果您使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="57bb2-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="57bb2-116">您仍然可以監視您的系統，而不需使用監看員節點。</span><span class="sxs-lookup"><span data-stu-id="57bb2-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="57bb2-117">唯一的差別在於，任何您想要執行的綜合交易必須叫用手動方式而不是自動叫用 Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="57bb2-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="57bb2-118">**Test-cswatchernodeconfiguration** cmdlet 可讓您確認監看員節點已正確設定，並指派給有效的 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="57bb2-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="57bb2-119">請注意，必須在本身的監看員節點上執行**Test-cswatchernodeconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="57bb2-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="57bb2-120">此 cmdlet 無法執行對遠端電腦。</span><span class="sxs-lookup"><span data-stu-id="57bb2-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="57bb2-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="57bb2-121">Running the test</span></span>

<span data-ttu-id="57bb2-122">下列命令會確認已採用組織中每個監看員節點組態設定。</span><span class="sxs-lookup"><span data-stu-id="57bb2-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="57bb2-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="57bb2-123">Determining success or failure</span></span>

<span data-ttu-id="57bb2-124">下列成功的範例輸出顯示具有四個 edge server 的系統。</span><span class="sxs-lookup"><span data-stu-id="57bb2-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="57bb2-125">驗證目標集區 atl-cs-001.litwareinc.com 針對拓樸。</span><span class="sxs-lookup"><span data-stu-id="57bb2-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="57bb2-126">成功： 目標集區 atl-cs-001.litwareinc.com 存在於拓撲中。</span><span class="sxs-lookup"><span data-stu-id="57bb2-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="57bb2-127">成功： 目標集區 atl-cs-001.litwareinc.com 已安裝登錄器角色。</span><span class="sxs-lookup"><span data-stu-id="57bb2-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="57bb2-128">成功： 目標集區 atl-cs-001.litwareinc.com 是支援的版本。</span><span class="sxs-lookup"><span data-stu-id="57bb2-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="57bb2-129">成功： 5061 目標集區 atl-cs-001.litwareinc.com 的連接埠號碼正確。</span><span class="sxs-lookup"><span data-stu-id="57bb2-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="57bb2-130">檢查監看員節點設定中遺漏的集區已啟動。</span><span class="sxs-lookup"><span data-stu-id="57bb2-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="57bb2-131">如果偵測到任何錯誤，它將會列印。</span><span class="sxs-lookup"><span data-stu-id="57bb2-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="57bb2-132">檢查遺漏的集區在監看員節點組態便已完成。</span><span class="sxs-lookup"><span data-stu-id="57bb2-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="57bb2-133">檢查安裝監看員節點所建立的監看員節點登錄機碼，便會啟動。</span><span class="sxs-lookup"><span data-stu-id="57bb2-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="57bb2-134">如果偵測到任何錯誤，它將會列印。</span><span class="sxs-lookup"><span data-stu-id="57bb2-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="57bb2-135">檢查安裝監看員節點所建立的監看員節點登錄機碼，已完成。</span><span class="sxs-lookup"><span data-stu-id="57bb2-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="57bb2-136">偵測到的驗證類型是交涉。</span><span class="sxs-lookup"><span data-stu-id="57bb2-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="57bb2-137">在成功驗證測試使用者的認證 sip: user1 @ atl-cs-001.litwareinc.com 認證管理存放區中存在。</span><span class="sxs-lookup"><span data-stu-id="57bb2-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="57bb2-138">在成功驗證測試使用者的認證 sip: user2 @ atl-cs-001.litwareinc.com 認證管理存放區中存在。</span><span class="sxs-lookup"><span data-stu-id="57bb2-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="57bb2-139">檢查監看員節點設定中遺漏的集區已啟動。</span><span class="sxs-lookup"><span data-stu-id="57bb2-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="57bb2-140">如果偵測到任何錯誤，它將會列印。</span><span class="sxs-lookup"><span data-stu-id="57bb2-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="57bb2-141">警告： 集區 atl-cs-001.litwareinc.com 已註冊機構</span><span class="sxs-lookup"><span data-stu-id="57bb2-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="57bb2-142">角色安裝，但沒有測試使用者為其設定。</span><span class="sxs-lookup"><span data-stu-id="57bb2-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="57bb2-143">檢查遺漏的集區在監看員節點組態便已完成。</span><span class="sxs-lookup"><span data-stu-id="57bb2-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="57bb2-144">檢查安裝監看員節點所建立的監看員節點登錄機碼，是</span><span class="sxs-lookup"><span data-stu-id="57bb2-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="57bb2-145">啟動。</span><span class="sxs-lookup"><span data-stu-id="57bb2-145">started.</span></span> <span data-ttu-id="57bb2-146">如果偵測到任何錯誤，它將會列印。</span><span class="sxs-lookup"><span data-stu-id="57bb2-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="57bb2-147">Test-cswatchernodeconfiguration： 找不到健康情況登錄機碼</span><span class="sxs-lookup"><span data-stu-id="57bb2-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="57bb2-148">軟體\\Microsoft\\即時通訊。</span><span class="sxs-lookup"><span data-stu-id="57bb2-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="57bb2-149">請確定監看員節點.msi 是</span><span class="sxs-lookup"><span data-stu-id="57bb2-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="57bb2-150">正確安裝。</span><span class="sxs-lookup"><span data-stu-id="57bb2-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="57bb2-151">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="57bb2-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="57bb2-152">以下是一些常見的原因為何**Test-cswatchernodeconfiguration**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="57bb2-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="57bb2-153">未正確地安裝監看員節點。</span><span class="sxs-lookup"><span data-stu-id="57bb2-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="57bb2-154">沒有測試使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="57bb2-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57bb2-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="57bb2-155">See Also</span></span>


[<span data-ttu-id="57bb2-156">Get-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="57bb2-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="57bb2-157">New-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="57bb2-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="57bb2-158">Remove-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="57bb2-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="57bb2-159">Set-cswatchernodeconfiguration</span><span class="sxs-lookup"><span data-stu-id="57bb2-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

