---
title: Lync Server 2013： 測試複本服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2784796d0eaca5d37aa841ee3db351a841c3c397
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="56e53-102">Lync Server 2013 中的測試複本服務</span><span class="sxs-lookup"><span data-stu-id="56e53-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56e53-103">_**上次修改主題：** 2014年-11-03_</span><span class="sxs-lookup"><span data-stu-id="56e53-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56e53-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="56e53-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="56e53-105">每日</span><span class="sxs-lookup"><span data-stu-id="56e53-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56e53-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="56e53-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="56e53-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56e53-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56e53-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="56e53-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="56e53-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="56e53-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="56e53-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csreplica</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="56e53-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="56e53-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="56e53-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="56e53-112">描述</span><span class="sxs-lookup"><span data-stu-id="56e53-112">Description</span></span>

<span data-ttu-id="56e53-113">**Test-csreplica** cmdlet 會驗證 Lync Server 2013 複本服務在本機電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="56e53-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="56e53-114">**Test-csreplica** cmdlet 所執行的這類的工作：</span><span class="sxs-lookup"><span data-stu-id="56e53-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="56e53-115">檢查複寫器代理程式和集中式記錄代理程式服務的狀態</span><span class="sxs-lookup"><span data-stu-id="56e53-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="56e53-116">驗證在 [Windows 防火牆已開啟的必要連接埠</span><span class="sxs-lookup"><span data-stu-id="56e53-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="56e53-117">確定本機電腦的安全性群組與必要的 Active Directory 存在。</span><span class="sxs-lookup"><span data-stu-id="56e53-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="56e53-118">請注意，必須在本機上執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56e53-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="56e53-119">也就是說，它必須執行相同的電腦上的複本服務執行所在。</span><span class="sxs-lookup"><span data-stu-id="56e53-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="56e53-120">沒有針對遠端伺服器執行**Test-csreplica** cmdlet 選項。</span><span class="sxs-lookup"><span data-stu-id="56e53-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="56e53-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="56e53-121">Running the test</span></span>

<span data-ttu-id="56e53-122">範例 1 所示的命令會測試本機電腦上的 Lync Server 2013 複本服務。</span><span class="sxs-lookup"><span data-stu-id="56e53-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="56e53-123">本範例會在 Verbose 參數用於保證 – 包括最終失敗或成功的測試和測試所產生的報告的位置 – 測試的相關資訊會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="56e53-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="56e53-124">範例 2 是範例 1 所示命令的變化。</span><span class="sxs-lookup"><span data-stu-id="56e53-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="56e53-125">在此情況下，Report 參數是包含指定的資料夾路徑和測試所產生的報表名稱。</span><span class="sxs-lookup"><span data-stu-id="56e53-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="56e53-126">如果您未指定報表的路徑報表會提供類似自動產生名稱：</span><span class="sxs-lookup"><span data-stu-id="56e53-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="56e53-127">C:\\使用者\\Administrator.Litwareinc\\AppData\\本機\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="56e53-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="56e53-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="56e53-128">Determining success or failure</span></span>

<span data-ttu-id="56e53-129">在此處插入區段主體。</span><span class="sxs-lookup"><span data-stu-id="56e53-129">Insert section body here.</span></span>

<span data-ttu-id="56e53-130">VERBOSE： 建立新的記錄檔 」 c:\\使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml 」。</span><span class="sxs-lookup"><span data-stu-id="56e53-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="56e53-131">VERBOSE： 建立新的記錄檔 」 c:\\使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml 」。</span><span class="sxs-lookup"><span data-stu-id="56e53-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="56e53-132">VERBOSE: 「 Test-csreplica 」 處理已順利完成。</span><span class="sxs-lookup"><span data-stu-id="56e53-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="56e53-133">VERBOSE： 可以在找到詳細的結果 」 c:\\使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml 」。</span><span class="sxs-lookup"><span data-stu-id="56e53-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="56e53-134">VERBOSE： 建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="56e53-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="56e53-135">「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="56e53-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="56e53-136">d3bd0e4a083.xml 」。</span><span class="sxs-lookup"><span data-stu-id="56e53-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="56e53-137">VERBOSE： 建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="56e53-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="56e53-138">「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="56e53-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="56e53-139">d3bd0e4a083.html 」。</span><span class="sxs-lookup"><span data-stu-id="56e53-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="56e53-140">警告： Test-csreplica 失敗。</span><span class="sxs-lookup"><span data-stu-id="56e53-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="56e53-141">警告： 可以在找到詳細的結果</span><span class="sxs-lookup"><span data-stu-id="56e53-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="56e53-142">「 C:\\使用者\\測試\\AppData\\本機\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="56e53-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="56e53-143">d3bd0e4a083.html 」。</span><span class="sxs-lookup"><span data-stu-id="56e53-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="56e53-144">Test-csreplica： 命令執行失敗： 要求不是登錄的存取</span><span class="sxs-lookup"><span data-stu-id="56e53-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="56e53-145">允許。</span><span class="sxs-lookup"><span data-stu-id="56e53-145">allowed.</span></span>

<span data-ttu-id="56e53-146">在線條： 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="56e53-146">At line:1 char:1</span></span>

<span data-ttu-id="56e53-147">\+Test-csreplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="56e53-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="56e53-148">\+CategoryInfo: InvalidOperation: （:）\[Test-csreplica\]，安全性</span><span class="sxs-lookup"><span data-stu-id="56e53-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="56e53-149">Exception</span><span class="sxs-lookup"><span data-stu-id="56e53-149">Exception</span></span>

<span data-ttu-id="56e53-150">\+FullyQualifiedErrorId: ProcessingFailed,Microsoft.Rtc.Management.Deploy</span><span class="sxs-lookup"><span data-stu-id="56e53-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="56e53-151">ment。TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="56e53-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="56e53-152">PS C:>\\使用者\\測試\></span><span class="sxs-lookup"><span data-stu-id="56e53-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="56e53-153">PS C:>\\使用者\\測試\>Test-csucwaconference TargetFqdn 」 LyncTest.SelfHost.Corp.M</span><span class="sxs-lookup"><span data-stu-id="56e53-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="56e53-154">icrosoft.com 」</span><span class="sxs-lookup"><span data-stu-id="56e53-154">icrosoft.com"</span></span>

<span data-ttu-id="56e53-155">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="56e53-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="56e53-156">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="56e53-156">domain name (FQDN).</span></span> <span data-ttu-id="56e53-157">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="56e53-157">Using default Registrar port number.</span></span> <span data-ttu-id="56e53-158">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="56e53-158">Exception:</span></span>

<span data-ttu-id="56e53-159">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="56e53-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="56e53-160">在</span><span class="sxs-lookup"><span data-stu-id="56e53-160">at</span></span>

<span data-ttu-id="56e53-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="56e53-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="56e53-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="56e53-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="56e53-163">Test-csucwaconference： 沒有指派的測試使用者</span><span class="sxs-lookup"><span data-stu-id="56e53-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="56e53-164">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="56e53-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="56e53-165">驗證測試使用者設定。</span><span class="sxs-lookup"><span data-stu-id="56e53-165">Verify test user configuration.</span></span>

<span data-ttu-id="56e53-166">在線條： 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="56e53-166">At line:1 char:1</span></span>

<span data-ttu-id="56e53-167">\+Test-csucwaconference TargetFqdn 「 LyncTest.SelfHost.Corp.Microsoft.com 」</span><span class="sxs-lookup"><span data-stu-id="56e53-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="56e53-168">\+CategoryInfo: ResourceUnavailable: （:）\[Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="56e53-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="56e53-169">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="56e53-169">, InvalidOperationException</span></span>

<span data-ttu-id="56e53-170">\+FullyQualifiedErrorId: NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span><span class="sxs-lookup"><span data-stu-id="56e53-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="56e53-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="56e53-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="56e53-172">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="56e53-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="56e53-173">以下是一些常見的原因為何**Test-csreplica**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="56e53-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="56e53-174">可能會有較大的複寫器代理程式和集中式記錄代理程式服務問題</span><span class="sxs-lookup"><span data-stu-id="56e53-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="56e53-175">必要的連接埠可能無法開啟在 [Windows 防火牆</span><span class="sxs-lookup"><span data-stu-id="56e53-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="56e53-176">本機電腦的安全性群組與必要的 Active Directory 可能不存在</span><span class="sxs-lookup"><span data-stu-id="56e53-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

