---
title: Lync Server 2013：測試複本服務
description: Lync Server 2013：測試複本服務。
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
ms.openlocfilehash: a61751b95115da3d6519f20f52262b7159ffcbfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556159"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="d3d2b-103">在 Lync Server 2013 中測試複本服務</span><span class="sxs-lookup"><span data-stu-id="d3d2b-103">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3d2b-104">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="d3d2b-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3d2b-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="d3d2b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d3d2b-106">每日</span><span class="sxs-lookup"><span data-stu-id="d3d2b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3d2b-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="d3d2b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d3d2b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3d2b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3d2b-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d3d2b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d3d2b-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d3d2b-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsReplica</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="d3d2b-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d3d2b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d3d2b-113">描述</span><span class="sxs-lookup"><span data-stu-id="d3d2b-113">Description</span></span>

<span data-ttu-id="d3d2b-114">**Test-CsReplica** Cmdlet 會驗證 Lync Server 2013 複本服務是否正在本機電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-114">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="d3d2b-115">**Test-CsReplica** Cmdlet 會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="d3d2b-115">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="d3d2b-116">檢查複製器代理程式的狀態及集中式記錄代理程式服務</span><span class="sxs-lookup"><span data-stu-id="d3d2b-116">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="d3d2b-117">確認已在 Windows 防火牆中開啟必要的埠</span><span class="sxs-lookup"><span data-stu-id="d3d2b-117">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="d3d2b-118">確定所需的 Active Directory 和本機電腦安全性組都存在。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-118">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="d3d2b-119">請注意，此 Cmdlet 必須在本機執行。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-119">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="d3d2b-120">也就是說，您必須在執行複本服務的同一部電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-120">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="d3d2b-121">在遠端伺服器上執行 **Test-CsReplica** Cmdlet 沒有任何選項。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-121">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d3d2b-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="d3d2b-122">Running the test</span></span>

<span data-ttu-id="d3d2b-123">範例1所示的命令會測試本機電腦上的 Lync Server 2013 複本服務。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-123">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="d3d2b-124">在此範例中，Verbose 參數是用來保證有關測試的資訊（包括測試的最終失敗或測試的成功所在位置）顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-124">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="d3d2b-125">範例 2 是範例 1 所示命令的變化。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-125">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="d3d2b-126">在此情況下，Report 參數會包含在內，以指定測試所產生之報告的資料夾路徑和名稱。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-126">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="d3d2b-127">如果您未指定報告路徑，將會為報告指定自動產生的名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d2b-127">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="d3d2b-128">C： \\ 使用者 \\ Litwareinc \\ AppData \\ 本機 \\ Temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="d3d2b-128">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d3d2b-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="d3d2b-129">Determining success or failure</span></span>

<span data-ttu-id="d3d2b-130">在此處插入區段主體。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-130">Insert section body here.</span></span>

<span data-ttu-id="d3d2b-131">詳細：建立新的記錄檔 "C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="d3d2b-132">詳細：建立新的記錄檔 "C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-132">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="d3d2b-133">詳細： "Test-CsReplica" 處理已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-133">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="d3d2b-134">詳細：請參閱 "C： \\ 使用者 \\ 測試 \\ AppData \\ Local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml" 的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-134">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="d3d2b-135">詳細：建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="d3d2b-135">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="d3d2b-136">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="d3d2b-136">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="d3d2b-137">d3bd0e4a083.xml "。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-137">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="d3d2b-138">詳細：建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="d3d2b-138">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="d3d2b-139">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="d3d2b-139">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="d3d2b-140">d3bd0e4a083.html "。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-140">d3bd0e4a083.html".</span></span>

<span data-ttu-id="d3d2b-141">警告： Test-CsReplica 失敗。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-141">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="d3d2b-142">警告：您可以在以下位置找到詳細的結果：</span><span class="sxs-lookup"><span data-stu-id="d3d2b-142">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="d3d2b-143">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="d3d2b-143">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="d3d2b-144">d3bd0e4a083.html "。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-144">d3bd0e4a083.html".</span></span>

<span data-ttu-id="d3d2b-145">Test-CsReplica：命令執行失敗：要求的登錄存取不是</span><span class="sxs-lookup"><span data-stu-id="d3d2b-145">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="d3d2b-146">允許。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-146">allowed.</span></span>

<span data-ttu-id="d3d2b-147">線上：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="d3d2b-147">At line:1 char:1</span></span>

<span data-ttu-id="d3d2b-148">\+ Test-CsReplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="d3d2b-148">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="d3d2b-149">\+ CategoryInfo： InvalidOperation： (： ) \[ Test-CsReplica \] ，安全性</span><span class="sxs-lookup"><span data-stu-id="d3d2b-149">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="d3d2b-150">Exception</span><span class="sxs-lookup"><span data-stu-id="d3d2b-150">Exception</span></span>

<span data-ttu-id="d3d2b-151">\+ FullyQualifiedErrorId： ProcessingFailed，Microsoft，.Deploy</span><span class="sxs-lookup"><span data-stu-id="d3d2b-151">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="d3d2b-152">。TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="d3d2b-152">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="d3d2b-153">PS C： \\ 使用者 \\ 測試\></span><span class="sxs-lookup"><span data-stu-id="d3d2b-153">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="d3d2b-154">PS C： \\ 使用者 \\ 測試 \> Test-CsUcwaConference-TargetFqdn "SelfHost"</span><span class="sxs-lookup"><span data-stu-id="d3d2b-154">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="d3d2b-155">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="d3d2b-155">icrosoft.com"</span></span>

<span data-ttu-id="d3d2b-156">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="d3d2b-156">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="d3d2b-157">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-157">domain name (FQDN).</span></span> <span data-ttu-id="d3d2b-158">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-158">Using default Registrar port number.</span></span> <span data-ttu-id="d3d2b-159">例外：</span><span class="sxs-lookup"><span data-stu-id="d3d2b-159">Exception:</span></span>

<span data-ttu-id="d3d2b-160">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-160">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="d3d2b-161">在</span><span class="sxs-lookup"><span data-stu-id="d3d2b-161">at</span></span>

<span data-ttu-id="d3d2b-162">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="d3d2b-162">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="d3d2b-163">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="d3d2b-163">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="d3d2b-164">Test-CsUcwaConference：沒有指派的測試使用者</span><span class="sxs-lookup"><span data-stu-id="d3d2b-164">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="d3d2b-165">\[LyncTest.SelfHost.Corp.Microsoft.com \] 。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-165">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="d3d2b-166">驗證測試使用者設定。</span><span class="sxs-lookup"><span data-stu-id="d3d2b-166">Verify test user configuration.</span></span>

<span data-ttu-id="d3d2b-167">線上：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="d3d2b-167">At line:1 char:1</span></span>

<span data-ttu-id="d3d2b-168">\+ Test-CsUcwaConference TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="d3d2b-168">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="d3d2b-169">\+ CategoryInfo： ResourceUnavailable： (： ) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="d3d2b-169">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="d3d2b-170">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="d3d2b-170">, InvalidOperationException</span></span>

<span data-ttu-id="d3d2b-171">\+ FullyQualifiedErrorId： NotFoundTestUsers、、Microsoft Rtc。合成</span><span class="sxs-lookup"><span data-stu-id="d3d2b-171">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="d3d2b-172">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="d3d2b-172">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d3d2b-173">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="d3d2b-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="d3d2b-174">以下是一些 **Test-CsReplica** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="d3d2b-174">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="d3d2b-175">複寫器代理程式和集中式記錄代理程式服務可能會發生較大的問題</span><span class="sxs-lookup"><span data-stu-id="d3d2b-175">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="d3d2b-176">在 Windows 防火牆中，可能未開啟必要的埠</span><span class="sxs-lookup"><span data-stu-id="d3d2b-176">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="d3d2b-177">必要的 Active Directory 和本機電腦安全性組可能不存在</span><span class="sxs-lookup"><span data-stu-id="d3d2b-177">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

