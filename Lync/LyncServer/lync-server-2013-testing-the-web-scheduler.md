---
title: Lync Server 2013：測試 Web 計畫程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b385184486cdbf8e2ee18956df1546d09335e6c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503940"
---
# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="ee4e9-102">在 Lync Server 2013 中測試 Web 計畫程式</span><span class="sxs-lookup"><span data-stu-id="ee4e9-102">Testing the Web scheduler in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee4e9-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="ee4e9-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee4e9-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ee4e9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ee4e9-105">每日</span><span class="sxs-lookup"><span data-stu-id="ee4e9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4e9-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="ee4e9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ee4e9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee4e9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee4e9-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="ee4e9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ee4e9-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ee4e9-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsWebScheduler</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="ee4e9-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ee4e9-112">描述</span><span class="sxs-lookup"><span data-stu-id="ee4e9-112">Description</span></span>

<span data-ttu-id="ee4e9-113">**Test-CsWebScheduler** Cmdlet 可讓您判斷特定使用者是否可以使用 Web 排程器排程會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="ee4e9-114">Web 排程器可讓未執行 Outlook 的使用者排程線上會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="ee4e9-115">此外，這項新功能 (會結合 Microsoft Lync Server 2010 資源套件隨附的 Web 排程器工具中所提供的功能，) 讓使用者能夠：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="ee4e9-116">排程新的線上會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="ee4e9-117">列出自己所排程的所有會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="ee4e9-118">檢視/修改現有的會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="ee4e9-119">刪除現有的會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="ee4e9-120">使用預先設定的 SMTP 郵件伺服器，傳送電子郵件邀請給會議參與者。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="ee4e9-121">加入現有的會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ee4e9-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="ee4e9-122">Running the test</span></span>

<span data-ttu-id="ee4e9-123">下列範例會驗證集區 atl-cs-001.litwareinc.com 的 Web 調度程式。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ee4e9-124">只有針對集區 atl-cs-001.litwareinc.com 定義測試使用者時，此命令才會運作。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="ee4e9-125">如果有的話，此命令會判斷第一個測試使用者是否可以使用 Web 排程器排程線上會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="ee4e9-126">若未定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="ee4e9-127">若尚未定義集區的測試使用者，則必須包括 UserSipAddress 參數，以及在嘗試登入時，該命令應該使用之使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="ee4e9-128">下一個範例中所示的命令會測試特定使用者 (litwareinc \\ kenmeyer) 的功能，以使用 Web 排程器排程線上會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="ee4e9-129">為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Ken Meyer 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="ee4e9-130"> (因為登入名稱 litwareinc \\ kenmeyer 包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Ken Meyer 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="ee4e9-131">然後，第二個命令會檢查此使用者是否可以登入集區 atl-cs-001.litwareinc.com 及排程線上會議。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="ee4e9-132">若要執行此工作，會呼叫 **Test-CsWebScheduler** Cmdlet 及三個參數： TargetFqdn (註冊機構集區的 FQDN) ;UserCredential (包含 Pilar Ackerman 使用者認證) 的 Windows PowerShell 物件。和 UserSipAddress (與所提供使用者認證) 相對應的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ee4e9-133">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ee4e9-133">Determining success or failure</span></span>

<span data-ttu-id="ee4e9-134">如果 web 排程器設定正確，您會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功**]：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="ee4e9-135">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ee4e9-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ee4e9-136">目標 Uri： HTTPs://atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="ee4e9-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="ee4e9-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="ee4e9-138">結果：成功</span><span class="sxs-lookup"><span data-stu-id="ee4e9-138">Result : Success</span></span>

<span data-ttu-id="ee4e9-139">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ee4e9-139">Latency : 00:00:00</span></span>

<span data-ttu-id="ee4e9-140">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-140">Error Message :</span></span>

<span data-ttu-id="ee4e9-141">診斷：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-141">Diagnosis :</span></span>

<span data-ttu-id="ee4e9-142">如果未正確設定 web 排程器，結果將會顯示為 [ **失敗**]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ee4e9-143">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="ee4e9-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="ee4e9-144">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-144">domain name (FQDN).</span></span> <span data-ttu-id="ee4e9-145">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-145">Using default Registrar port number.</span></span> <span data-ttu-id="ee4e9-146">例外：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-146">Exception:</span></span>

<span data-ttu-id="ee4e9-147">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="ee4e9-148">在</span><span class="sxs-lookup"><span data-stu-id="ee4e9-148">at</span></span>

<span data-ttu-id="ee4e9-149">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="ee4e9-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="ee4e9-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="ee4e9-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="ee4e9-151">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ee4e9-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ee4e9-152">目標 Uri：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-152">Target Uri :</span></span>

<span data-ttu-id="ee4e9-153">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="ee4e9-153">Result : Failure</span></span>

<span data-ttu-id="ee4e9-154">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="ee4e9-154">Latency : 00:00:00</span></span>

<span data-ttu-id="ee4e9-155">錯誤訊息：在拓撲中找不到相符的集群。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="ee4e9-156">診斷：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ee4e9-157">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ee4e9-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="ee4e9-158">以下是一些 **Test-CsWebScheduler** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="ee4e9-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="ee4e9-159">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ee4e9-160">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ee4e9-161">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ee4e9-162">如果 Web 排程器設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ee4e9-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee4e9-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee4e9-163">See Also</span></span>


[<span data-ttu-id="ee4e9-164">Set-CsWebServer</span><span class="sxs-lookup"><span data-stu-id="ee4e9-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

