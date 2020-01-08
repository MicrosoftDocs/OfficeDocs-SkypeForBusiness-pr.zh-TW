---
title: Lync Server 2013：測試複本服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1a9dca37c30231a2f0f297e94321dfc12405d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a><span data-ttu-id="a8e6e-102">在 Lync Server 2013 中測試複本服務</span><span class="sxs-lookup"><span data-stu-id="a8e6e-102">Testing the replica service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8e6e-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a8e6e-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8e6e-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="a8e6e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a8e6e-105">日常</span><span class="sxs-lookup"><span data-stu-id="a8e6e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8e6e-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="a8e6e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a8e6e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8e6e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8e6e-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="a8e6e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a8e6e-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a8e6e-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsReplica</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsReplica</strong> cmdlet.</span></span> <span data-ttu-id="a8e6e-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a8e6e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a8e6e-112">描述</span><span class="sxs-lookup"><span data-stu-id="a8e6e-112">Description</span></span>

<span data-ttu-id="a8e6e-113">**CsReplica** Cmdlet 會確認 Lync Server 2013 複本服務正在本機電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-113">The **Test-CsReplica** cmdlet verifies that the Lync Server 2013 replica service is running on the local computer.</span></span> <span data-ttu-id="a8e6e-114">**CsReplica** Cmdlet 會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="a8e6e-114">The **Test-CsReplica** cmdlet performs such tasks as:</span></span>

  - <span data-ttu-id="a8e6e-115">檢查複製器代理程式與集中式記錄代理程式服務的狀態</span><span class="sxs-lookup"><span data-stu-id="a8e6e-115">checking the status of the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="a8e6e-116">確認已在 Windows 防火牆中開啟所需的埠</span><span class="sxs-lookup"><span data-stu-id="a8e6e-116">verifying that the required ports were opened in the Windows Firewall</span></span>

  - <span data-ttu-id="a8e6e-117">確定所需的 Active Directory 和本機電腦安全性組存在。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-117">making sure that the necessary Active Directory and local computer security groups exist.</span></span>

<span data-ttu-id="a8e6e-118">請注意，這個 Cmdlet 必須在本機執行。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-118">Note that this cmdlet must be run locally.</span></span> <span data-ttu-id="a8e6e-119">也就是說，它必須在執行複本服務的同一部電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-119">That is, it must be run on the same computer where the replica service is running.</span></span> <span data-ttu-id="a8e6e-120">在遠端伺服器上執行**CsReplica** Cmdlet 沒有任何選項。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-120">There are no options for running the **Test-CsReplica** cmdlet against a remote server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a8e6e-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="a8e6e-121">Running the test</span></span>

<span data-ttu-id="a8e6e-122">範例1中所示的命令會測試本機電腦上的 Lync Server 2013 副本服務。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-122">The command shown in Example 1 tests the Lync Server 2013 replica service on the local computer.</span></span> <span data-ttu-id="a8e6e-123">在這個範例中，Verbose 參數是用來保證有關測試的資訊（包括最終失敗，或測試產生的報告位置）會顯示在畫面上。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-123">In this example the Verbose parameter is used to guarantee that information about the test – including the eventual failure or success of the test and the location of the report generated by the test – is displayed on screen.</span></span>

    Test-CsReplica -Verbose

<span data-ttu-id="a8e6e-124">範例2是範例1中所示命令的變化。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-124">Example 2 is a variation of the command shown in Example 1.</span></span> <span data-ttu-id="a8e6e-125">在這種情況下，會包含報表參數，以指定測試所產生之報表的資料夾路徑和名稱。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-125">In this case, the Report parameter is included to specify a folder path and name for the report generated by the test.</span></span> <span data-ttu-id="a8e6e-126">如果您沒有指定報表路徑，系統會為報表提供自動產生的名稱，類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="a8e6e-126">If you do not specify a report path the report will be given an auto-generated name similar to this:</span></span>

<span data-ttu-id="a8e6e-127">C：\\使用者\\Litwareinc\\AppData\\本機\\溫度\\1\\測試-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e</span><span class="sxs-lookup"><span data-stu-id="a8e6e-127">C:\\Users\\Administrator.Litwareinc\\AppData\\Local\\Temp\\1\\Test-Cs-Replica-3db40ee0-4b5d-4f58-8d3d-b1e61253129e.html</span></span>

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a8e6e-128">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="a8e6e-128">Determining success or failure</span></span>

<span data-ttu-id="a8e6e-129">在此插入章節本文。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-129">Insert section body here.</span></span>

<span data-ttu-id="a8e6e-130">詳細：建立新的記錄檔 "C\\：\\使用者\\測試\\AppData\\本機\\Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c"。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-130">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a8e6e-131">詳細：建立新的記錄檔 "C\\：\\使用者\\測試\\AppData\\本機\\Temp Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c"。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-131">VERBOSE: Creating new log file "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a8e6e-132">詳細：「Test-CsReplica」處理已順利完成。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-132">VERBOSE: "Test-CsReplica" processing has completed successfully.</span></span>

<span data-ttu-id="a8e6e-133">詳細：您可以在「C\\：使用者\\測試\\AppData\\本機\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c .xml」中找到詳細的結果。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-133">VERBOSE: Detailed results can be found at "C:\\Users\\Testing\\AppData\\Local\\Temp\\Test-CsReplica-3cb066b3-dd23-411a-8932-99f01c0f940c.xml".</span></span>

<span data-ttu-id="a8e6e-134">詳細：建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="a8e6e-134">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="a8e6e-135">"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="a8e6e-135">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a8e6e-136">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-136">d3bd0e4a083.xml".</span></span>

<span data-ttu-id="a8e6e-137">詳細：建立新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="a8e6e-137">VERBOSE: Creating new log file</span></span>

<span data-ttu-id="a8e6e-138">"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="a8e6e-138">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a8e6e-139">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-139">d3bd0e4a083.html".</span></span>

<span data-ttu-id="a8e6e-140">警告：測試 CsReplica 失敗。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-140">WARNING: Test-CsReplica failed.</span></span>

<span data-ttu-id="a8e6e-141">警告：您可以在以下網址找到詳細的結果</span><span class="sxs-lookup"><span data-stu-id="a8e6e-141">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="a8e6e-142">"C：\\使用者\\測試\\AppData\\本機\\Temp\\2\\測試-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span><span class="sxs-lookup"><span data-stu-id="a8e6e-142">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsReplica-29fddb35-f56e-4e3c-8f4c-e</span></span>

<span data-ttu-id="a8e6e-143">d3bd0e4a083 "。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-143">d3bd0e4a083.html".</span></span>

<span data-ttu-id="a8e6e-144">測試-CsReplica：命令執行失敗：要求的登錄存取權不是</span><span class="sxs-lookup"><span data-stu-id="a8e6e-144">Test-CsReplica : Command execution failed: Requested registry access is not</span></span>

<span data-ttu-id="a8e6e-145">允許.</span><span class="sxs-lookup"><span data-stu-id="a8e6e-145">allowed.</span></span>

<span data-ttu-id="a8e6e-146">在第一行：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="a8e6e-146">At line:1 char:1</span></span>

<span data-ttu-id="a8e6e-147">\+Test-CsReplica-詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a8e6e-147">\+ Test-CsReplica -Verbose</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="a8e6e-148">\+CategoryInfo： InvalidOperation：（:)\[測試 CsReplica\]、安全性</span><span class="sxs-lookup"><span data-stu-id="a8e6e-148">\+ CategoryInfo : InvalidOperation: (:) \[Test-CsReplica\], Security</span></span>

<span data-ttu-id="a8e6e-149">引發</span><span class="sxs-lookup"><span data-stu-id="a8e6e-149">Exception</span></span>

<span data-ttu-id="a8e6e-150">\+FullyQualifiedErrorId： ProcessingFailed、Microsoft Rtc. Deploy</span><span class="sxs-lookup"><span data-stu-id="a8e6e-150">\+ FullyQualifiedErrorId : ProcessingFailed,Microsoft.Rtc.Management.Deploy</span></span>

<span data-ttu-id="a8e6e-151">）。TestReplicaCmdlet</span><span class="sxs-lookup"><span data-stu-id="a8e6e-151">ment.TestReplicaCmdlet</span></span>

<span data-ttu-id="a8e6e-152">PS C：\\使用者\\測試\></span><span class="sxs-lookup"><span data-stu-id="a8e6e-152">PS C:\\Users\\Testing\></span></span>

<span data-ttu-id="a8e6e-153">PS C：\\使用者\\測試\> Test-CsUcwaConference-TargetFqdn "LyncTest. SelfHost</span><span class="sxs-lookup"><span data-stu-id="a8e6e-153">PS C:\\Users\\Testing\> Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.M</span></span>

<span data-ttu-id="a8e6e-154">icrosoft.com "</span><span class="sxs-lookup"><span data-stu-id="a8e6e-154">icrosoft.com"</span></span>

<span data-ttu-id="a8e6e-155">警告：無法讀取指定之完全限定的註冊機構埠號碼</span><span class="sxs-lookup"><span data-stu-id="a8e6e-155">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a8e6e-156">網功能變數名稱稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-156">domain name (FQDN).</span></span> <span data-ttu-id="a8e6e-157">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-157">Using default Registrar port number.</span></span> <span data-ttu-id="a8e6e-158">引發</span><span class="sxs-lookup"><span data-stu-id="a8e6e-158">Exception:</span></span>

<span data-ttu-id="a8e6e-159">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-159">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a8e6e-160">的</span><span class="sxs-lookup"><span data-stu-id="a8e6e-160">at</span></span>

<span data-ttu-id="a8e6e-161">TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction</span><span class="sxs-lookup"><span data-stu-id="a8e6e-161">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a8e6e-162">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="a8e6e-162">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a8e6e-163">Test-CsUcwaConference：沒有指派測試使用者</span><span class="sxs-lookup"><span data-stu-id="a8e6e-163">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="a8e6e-164">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-164">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="a8e6e-165">驗證測試使用者配置。</span><span class="sxs-lookup"><span data-stu-id="a8e6e-165">Verify test user configuration.</span></span>

<span data-ttu-id="a8e6e-166">在第一行：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="a8e6e-166">At line:1 char:1</span></span>

<span data-ttu-id="a8e6e-167">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="a8e6e-167">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="a8e6e-168">\+CategoryInfo： ResourceUnavailable：（:)\[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="a8e6e-168">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="a8e6e-169">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="a8e6e-169">, InvalidOperationException</span></span>

<span data-ttu-id="a8e6e-170">\+FullyQualifiedErrorId： NotFoundTestUsers，，</span><span class="sxs-lookup"><span data-stu-id="a8e6e-170">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="a8e6e-171">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="a8e6e-171">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a8e6e-172">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="a8e6e-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="a8e6e-173">以下是**測試 CsReplica**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="a8e6e-173">Here are some common reasons why **Test-CsReplica** might fail:</span></span>

  - <span data-ttu-id="a8e6e-174">複製器代理程式與集中式記錄代理程式服務可能會有更大的問題</span><span class="sxs-lookup"><span data-stu-id="a8e6e-174">There may be a larger problem with the Replicator Agent and Centralized Logging Agent services</span></span>

  - <span data-ttu-id="a8e6e-175">所需的埠可能無法在 Windows 防火牆中開啟</span><span class="sxs-lookup"><span data-stu-id="a8e6e-175">The required ports may not be open in the Windows Firewall</span></span>

  - <span data-ttu-id="a8e6e-176">所需的 Active Directory 和本機電腦安全性組可能不存在</span><span class="sxs-lookup"><span data-stu-id="a8e6e-176">The necessary Active Directory and local computer security groups may not exist</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

