---
title: Lync Server 2013：測試複本服務
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
ms.openlocfilehash: e30d0b8c0e570605c8c6556d42224a205741a821
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503960"
---
# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="c9829-102">在 Lync Server 2013 中測試複本服務</span><span class="sxs-lookup"><span data-stu-id="c9829-102">Testing the replica service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9829-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="c9829-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9829-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="c9829-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c9829-105">每日</span><span class="sxs-lookup"><span data-stu-id="c9829-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9829-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="c9829-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c9829-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9829-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9829-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="c9829-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c9829-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c9829-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c9829-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsReplica</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c9829-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="c9829-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9829-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c9829-112">描述</span><span class="sxs-lookup"><span data-stu-id="c9829-112">Description</span></span>

<span data-ttu-id="c9829-113">**Test-CsReplica** Cmdlet 會驗證 Lync Server 2013 複本服務是否正在本機電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c9829-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="c9829-114">**Test-CsReplica** Cmdlet 會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c9829-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="c9829-115">檢查複製器代理程式的狀態及集中式記錄代理程式服務</span><span class="sxs-lookup"><span data-stu-id="c9829-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="c9829-116">確認已在 Windows 防火牆中開啟必要的埠</span><span class="sxs-lookup"><span data-stu-id="c9829-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="c9829-117">確定所需的 Active Directory 和本機電腦安全性組都存在。</span><span class="sxs-lookup"><span data-stu-id="c9829-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="c9829-118">請注意，此 Cmdlet 必須在本機執行。</span><span class="sxs-lookup"><span data-stu-id="c9829-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="c9829-119">也就是說，您必須在執行複本服務的同一部電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="c9829-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="c9829-120">在遠端伺服器上執行 **Test-CsReplica** Cmdlet 沒有任何選項。</span><span class="sxs-lookup"><span data-stu-id="c9829-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c9829-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="c9829-121">Running the test</span></span>

<span data-ttu-id="c9829-122">範例1所示的命令會測試本機電腦上的 Lync Server 2013 複本服務。</span><span class="sxs-lookup"><span data-stu-id="c9829-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="c9829-123">在此範例中，Verbose 參數是用來保證有關測試的資訊（包括測試的最終失敗或測試的成功所在位置）顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="c9829-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="c9829-124">範例 2 是範例 1 所示命令的變化。</span><span class="sxs-lookup"><span data-stu-id="c9829-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="c9829-125">在此情況下，Report 參數會包含在內，以指定測試所產生之報告的資料夾路徑和名稱。</span><span class="sxs-lookup"><span data-stu-id="c9829-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="c9829-126">如果您未指定報告路徑，將會為報告指定自動產生的名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c9829-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="c9829-127">C： \\ 使用者 \\ Litwareinc \\ AppData \\ 本機 \\ Temp \\ 1 \\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span><span class="sxs-lookup"><span data-stu-id="c9829-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c9829-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="c9829-128">Determining success or failure</span></span>

<span data-ttu-id="c9829-129">在此處插入區段主體。</span><span class="sxs-lookup"><span data-stu-id="c9829-129">Insert section body here.</span></span>

<span data-ttu-id="c9829-130">詳細：建立新的記錄檔 "C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。</span><span class="sxs-lookup"><span data-stu-id="c9829-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c9829-131">詳細：建立新的記錄檔 "C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml"。</span><span class="sxs-lookup"><span data-stu-id="c9829-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c9829-132">詳細： "Test-CsReplica" 處理已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c9829-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="c9829-133">詳細：請參閱 "C： \\ 使用者 \\ 測試 \\ AppData \\ Local \\ Temp \\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml" 的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="c9829-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="c9829-134">詳細：建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="c9829-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="c9829-135">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="c9829-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c9829-136">d3bd0e4a083.xml "。</span><span class="sxs-lookup"><span data-stu-id="c9829-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="c9829-137">詳細：建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="c9829-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="c9829-138">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="c9829-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c9829-139">d3bd0e4a083.html "。</span><span class="sxs-lookup"><span data-stu-id="c9829-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="c9829-140">警告： Test-CsReplica 失敗。</span><span class="sxs-lookup"><span data-stu-id="c9829-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="c9829-141">警告：您可以在以下位置找到詳細的結果：</span><span class="sxs-lookup"><span data-stu-id="c9829-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="c9829-142">"C： \\ 使用者 \\ 測試 \\ AppData \\ 本機 \\ Temp \\ 2 \\ Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e"</span><span class="sxs-lookup"><span data-stu-id="c9829-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="c9829-143">d3bd0e4a083.html "。</span><span class="sxs-lookup"><span data-stu-id="c9829-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="c9829-144">Test-CsReplica：命令執行失敗：要求的登錄存取不是</span><span class="sxs-lookup"><span data-stu-id="c9829-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="c9829-145">允許。</span><span class="sxs-lookup"><span data-stu-id="c9829-145">allowed.</span></span>

<span data-ttu-id="c9829-146">線上：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="c9829-146">At line:1 char:1</span></span>

<span data-ttu-id="c9829-147">\+ Test-CsReplica-Verbose</span><span class="sxs-lookup"><span data-stu-id="c9829-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c9829-148">\+ CategoryInfo： InvalidOperation： (： ) \[ Test-CsReplica \] ，安全性</span><span class="sxs-lookup"><span data-stu-id="c9829-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="c9829-149">Exception</span><span class="sxs-lookup"><span data-stu-id="c9829-149">Exception</span></span>

<span data-ttu-id="c9829-150">\+ FullyQualifiedErrorId： ProcessingFailed，Microsoft，.Deploy</span><span class="sxs-lookup"><span data-stu-id="c9829-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="c9829-151">。TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="c9829-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="c9829-152">PS C： \\ 使用者 \\ 測試\></span><span class="sxs-lookup"><span data-stu-id="c9829-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="c9829-153">PS C： \\ 使用者 \\ 測試 \> Test-CsUcwaConference-TargetFqdn "SelfHost"</span><span class="sxs-lookup"><span data-stu-id="c9829-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="c9829-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="c9829-154">icrosoft.com"</span></span>

<span data-ttu-id="c9829-155">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="c9829-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c9829-156">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="c9829-156">domain name (FQDN).</span></span> <span data-ttu-id="c9829-157">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="c9829-157">Using default Registrar port number.</span></span> <span data-ttu-id="c9829-158">例外：</span><span class="sxs-lookup"><span data-stu-id="c9829-158">Exception:</span></span>

<span data-ttu-id="c9829-159">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="c9829-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c9829-160">在</span><span class="sxs-lookup"><span data-stu-id="c9829-160">at</span></span>

<span data-ttu-id="c9829-161">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="c9829-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c9829-162">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="c9829-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c9829-163">Test-CsUcwaConference：沒有指派的測試使用者</span><span class="sxs-lookup"><span data-stu-id="c9829-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="c9829-164">\[LyncTest.SelfHost.Corp.Microsoft.com \] 。</span><span class="sxs-lookup"><span data-stu-id="c9829-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="c9829-165">驗證測試使用者設定。</span><span class="sxs-lookup"><span data-stu-id="c9829-165">Verify test user configuration.</span></span>

<span data-ttu-id="c9829-166">線上：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="c9829-166">At line:1 char:1</span></span>

<span data-ttu-id="c9829-167">\+ Test-CsUcwaConference TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="c9829-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="c9829-168">\+ CategoryInfo： ResourceUnavailable： (： ) \[ Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="c9829-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="c9829-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="c9829-169">, InvalidOperationException</span></span>

<span data-ttu-id="c9829-170">\+ FullyQualifiedErrorId： NotFoundTestUsers、、Microsoft Rtc。合成</span><span class="sxs-lookup"><span data-stu-id="c9829-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="c9829-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="c9829-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c9829-172">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="c9829-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="c9829-173">以下是一些 **Test-CsReplica** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="c9829-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="c9829-174">複寫器代理程式和集中式記錄代理程式服務可能會發生較大的問題</span><span class="sxs-lookup"><span data-stu-id="c9829-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="c9829-175">在 Windows 防火牆中，可能未開啟必要的埠</span><span class="sxs-lookup"><span data-stu-id="c9829-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="c9829-176">必要的 Active Directory 和本機電腦安全性組可能不存在</span><span class="sxs-lookup"><span data-stu-id="c9829-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

