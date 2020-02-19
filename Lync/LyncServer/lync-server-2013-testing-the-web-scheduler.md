---
title: Lync Server 2013： 測試 Web 排程器
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
ms.openlocfilehash: f6cd00192a7e2a9695a078768a6cf6ad9fac5873
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a><span data-ttu-id="e3dc2-102">在 Lync Server 2013 中進行測試 Web 排程器</span><span class="sxs-lookup"><span data-stu-id="e3dc2-102">Testing the Web scheduler in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3dc2-103">_**上次修改主題：** 2014年-11-03_</span><span class="sxs-lookup"><span data-stu-id="e3dc2-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dc2-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="e3dc2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e3dc2-105">每日</span><span class="sxs-lookup"><span data-stu-id="e3dc2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dc2-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="e3dc2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e3dc2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3dc2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dc2-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e3dc2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e3dc2-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e3dc2-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-cswebscheduler</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWebScheduler</strong> cmdlet.</span></span> <span data-ttu-id="e3dc2-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e3dc2-112">描述</span><span class="sxs-lookup"><span data-stu-id="e3dc2-112">Description</span></span>

<span data-ttu-id="e3dc2-113">**Test-cswebscheduler** cmdlet 可讓您判斷特定的使用者是否可以排程會議使用 Web 排程器。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-113">The **Test-CsWebScheduler** cmdlet enables you to determine whether a specific user can schedule a meeting using the Web Scheduler.</span></span> <span data-ttu-id="e3dc2-114">Web 排程器可讓使用者不執行 Outlook 重新排程線上會議。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-114">The Web Scheduler enables users who are not running Outlook to schedule online meetings.</span></span> <span data-ttu-id="e3dc2-115">除此之外，這項新功能 （，並包含 Web Scheduler 工具所隨附的 Microsoft Lync Server 2010 resource kit 中找到的功能） 可讓使用者：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-115">Among other things, this new feature (which incorporates the functionality found in the Web Scheduler tool that was included with the Microsoft Lync Server 2010 resource kit) enables users to:</span></span>

  - <span data-ttu-id="e3dc2-116">排程新的線上會議。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-116">Schedule a new online meeting.</span></span>

  - <span data-ttu-id="e3dc2-117">列出自己所排程的所有會議。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-117">List all meetings that he or she has scheduled.</span></span>

  - <span data-ttu-id="e3dc2-118">檢視/修改現有的會議。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-118">View/modify an existing meeting.</span></span>

  - <span data-ttu-id="e3dc2-119">刪除現有的會議。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-119">Delete an existing meeting.</span></span>

  - <span data-ttu-id="e3dc2-120">使用預先設定的 SMTP 郵件伺服器，傳送電子郵件邀請給會議參與者。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-120">Send an email invitation to meeting participants by using a preconfigured SMTP mail server.</span></span>

  - <span data-ttu-id="e3dc2-121">加入現有的會議。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-121">Join an existing conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e3dc2-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="e3dc2-122">Running the test</span></span>

<span data-ttu-id="e3dc2-123">下列範例會驗證的 Web 排程器集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-123">The following example verifies the Web Scheduler for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e3dc2-124">這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-124">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e3dc2-125">如果他們有命令將會判斷第一個測試使用者是否可以排程線上會議使用 Web 排程器。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-125">If they have, then the command will determine whether the first test user can schedule an online meeting using the Web Scheduler.</span></span>

<span data-ttu-id="e3dc2-126">如果沒有定義的測試使用者，然後將會失敗命令，因為它不會知道哪些使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-126">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="e3dc2-127">如果您還沒有定義的集區的測試使用者，就必須納入 UserSipAddress 參數，此命令應使用時，嘗試登入使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user the command should use when trying to log on.</span></span>

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e3dc2-128">下一個範例所示的命令會測試特定使用者的能力 (litwareinc\\kenmeyer) 排程線上會議使用 Web 排程器。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-128">The commands shown in the next example test the ability of a specific user (litwareinc\\kenmeyer) to schedule an online meeting using the Web scheduler.</span></span> <span data-ttu-id="e3dc2-129">若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼的使用者 Ken Meyer。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-129">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Ken Meyer.</span></span> <span data-ttu-id="e3dc2-130">(因為登入名稱 litwareinc\\kenmeyer 是包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken Meyer 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-130">(Because the logon name litwareinc\\kenmeyer is included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Meyer account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="e3dc2-131">此使用者是否可以登入集區 atl-cs-001.litwareinc.com 及排程線上會議，然後會檢查第二個命令。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-131">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and schedule an online meeting.</span></span> <span data-ttu-id="e3dc2-132">若要執行這項工作， **Test-cswebscheduler** cmdlet 會呼叫，以及三個參數： TargetFqdn (之登錄器集區 FQDN);UserCredential （包含為 Pilar Ackerman 的使用者認證的 Windows PowerShell 物件）;和 UserSipAddress （會對應至提供的使用者認證的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-132">To run this task, the **Test-CsWebScheduler** cmdlet is called, together with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e3dc2-133">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="e3dc2-133">Determining success or failure</span></span>

<span data-ttu-id="e3dc2-134">如果 web 排程器已正確設定，您會收到類似，具有標示為 [**成功**結果屬性的輸出：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-134">If the web scheduler is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="e3dc2-135">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e3dc2-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e3dc2-136">目標 Uri: https:// atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-136">Target Uri : https:// atl-cs-001.litwareinc.com.</span></span>

<span data-ttu-id="e3dc2-137">litwareinc.com:443/Scheduler</span><span class="sxs-lookup"><span data-stu-id="e3dc2-137">litwareinc.com:443/Scheduler</span></span>

<span data-ttu-id="e3dc2-138">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="e3dc2-138">Result : Success</span></span>

<span data-ttu-id="e3dc2-139">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e3dc2-139">Latency : 00:00:00</span></span>

<span data-ttu-id="e3dc2-140">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-140">Error Message :</span></span>

<span data-ttu-id="e3dc2-141">診斷：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-141">Diagnosis :</span></span>

<span data-ttu-id="e3dc2-142">如果未正確地設定 web 排程器，結果會顯示為**失敗**，及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-142">If the web scheduler is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e3dc2-143">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="e3dc2-143">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="e3dc2-144">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-144">domain name (FQDN).</span></span> <span data-ttu-id="e3dc2-145">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-145">Using default Registrar port number.</span></span> <span data-ttu-id="e3dc2-146">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-146">Exception:</span></span>

<span data-ttu-id="e3dc2-147">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-147">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="e3dc2-148">在</span><span class="sxs-lookup"><span data-stu-id="e3dc2-148">at</span></span>

<span data-ttu-id="e3dc2-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="e3dc2-149">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="e3dc2-150">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="e3dc2-150">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="e3dc2-151">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e3dc2-151">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e3dc2-152">目標 Uri:</span><span class="sxs-lookup"><span data-stu-id="e3dc2-152">Target Uri :</span></span>

<span data-ttu-id="e3dc2-153">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="e3dc2-153">Result : Failure</span></span>

<span data-ttu-id="e3dc2-154">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e3dc2-154">Latency : 00:00:00</span></span>

<span data-ttu-id="e3dc2-155">錯誤訊息： 在拓撲中找到不到相符叢集。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-155">Error Message : No matching cluster found in topology.</span></span>

<span data-ttu-id="e3dc2-156">診斷：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e3dc2-157">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="e3dc2-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="e3dc2-158">以下是一些常見的原因為何**Test-cswebscheduler**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="e3dc2-158">Here are some common reasons why **Test-CsWebScheduler** might fail:</span></span>

  - <span data-ttu-id="e3dc2-159">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e3dc2-160">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e3dc2-161">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e3dc2-162">如果設定錯誤或尚未部署 Web Scheduler，此命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="e3dc2-162">This command will fail if the Web Scheduler is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3dc2-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e3dc2-163">See Also</span></span>


[<span data-ttu-id="e3dc2-164">Set-cswebserver</span><span class="sxs-lookup"><span data-stu-id="e3dc2-164">Set-CsWebServer</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

