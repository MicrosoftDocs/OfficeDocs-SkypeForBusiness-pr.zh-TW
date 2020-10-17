---
title: Lync Server 2013：驗證音訊/視訊會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0bfeef1abcf7b5859c365b7c64b4fcc84f49ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503700"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a><span data-ttu-id="b7150-102">在 Lync Server 2013 中驗證音訊/視訊會議</span><span class="sxs-lookup"><span data-stu-id="b7150-102">Validating audio/video conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7150-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b7150-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7150-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="b7150-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b7150-105">每日</span><span class="sxs-lookup"><span data-stu-id="b7150-105">Daily</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7150-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="b7150-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b7150-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7150-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7150-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="b7150-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b7150-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b7150-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b7150-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAVConference Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b7150-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAVConference cmdlet.</span></span> <span data-ttu-id="b7150-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7150-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b7150-112">描述</span><span class="sxs-lookup"><span data-stu-id="b7150-112">Description</span></span>

<span data-ttu-id="b7150-113">Test-CsAVConference Cmdlet 會檢查是否有兩個測試使用者可以參與音訊/視頻 (A/V) 會議。</span><span class="sxs-lookup"><span data-stu-id="b7150-113">The Test-CsAVConference cmdlet checks whether two test users can participate in an audio/video (A/V) conference.</span></span> <span data-ttu-id="b7150-114">執行 Cmdlet 時，會將兩位使用者登入系統。</span><span class="sxs-lookup"><span data-stu-id="b7150-114">When the cmdlet runs, the two users are logged on to the system.</span></span> <span data-ttu-id="b7150-115">在他們成功登入後，第一個使用者會建立 A/V 會議，然後等候第二位使用者加入該會議。</span><span class="sxs-lookup"><span data-stu-id="b7150-115">After they face successfully logged on, the first user creates an A/V conference, and then waits for the second user to join that conference.</span></span> <span data-ttu-id="b7150-116">資料一開始短暫的交換後，就會刪除會議，而這兩個測試使用者已登出。</span><span class="sxs-lookup"><span data-stu-id="b7150-116">After a brief exchange of data, the conference is deleted and the two tests users are logged off.</span></span>

<span data-ttu-id="b7150-117">請注意，Test-CsAVConference 不會在兩個測試使用者之間進行實際的 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="b7150-117">Note that Test-CsAVConference does not conduct an actual A/V conference between the two test users.</span></span> <span data-ttu-id="b7150-118">相反地，指令程式會驗證這兩個使用者是否可以進行所有必要的連線，以進行這類會議。</span><span class="sxs-lookup"><span data-stu-id="b7150-118">Instead, the cmdlet verifies that the two users can make all the connections necessary to conduct such a conference.</span></span>

<span data-ttu-id="b7150-119">您可以在 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)找到此命令的進一步範例。</span><span class="sxs-lookup"><span data-stu-id="b7150-119">Further examples for this command can be found at [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b7150-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="b7150-120">Running the test</span></span>

<span data-ttu-id="b7150-121">您可以使用一對預先設定的測試帳戶來執行 Test-CsAVConference Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b7150-121">The Test-CsAVConference cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="b7150-122">若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b7150-122">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="b7150-123">例如：</span><span class="sxs-lookup"><span data-stu-id="b7150-123">For example:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="b7150-124">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="b7150-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="b7150-125">然後，您必須在呼叫 Test-CsAVConference 時，包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="b7150-125">You must then include those credentials objects and the SIP addresses of the two accounts when they call Test-CsAVConference:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="b7150-126">如需詳細資訊，請參閱 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="b7150-126">For more information, see the Help documentation for the [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b7150-127">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="b7150-127">Determining Success or Failure</span></span>

<span data-ttu-id="b7150-128">如果指定的使用者可以成功完成 A/V 會議，您會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="b7150-128">If the specified users can successfully complete an A/V conference, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b7150-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7150-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7150-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="b7150-130">Result : Success</span></span>

<span data-ttu-id="b7150-131">延遲：00：00：02.6841765</span><span class="sxs-lookup"><span data-stu-id="b7150-131">Latency : 00:00:02.6841765</span></span>

<span data-ttu-id="b7150-132">錯誤：</span><span class="sxs-lookup"><span data-stu-id="b7150-132">Error :</span></span>

<span data-ttu-id="b7150-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="b7150-133">Diagnosis :</span></span>

<span data-ttu-id="b7150-134">如果使用者無法完成會議，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="b7150-134">If the users can not complete the conference, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b7150-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7150-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7150-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="b7150-136">Result : Failure</span></span>

<span data-ttu-id="b7150-137">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="b7150-137">Latency : 00:00:00</span></span>

<span data-ttu-id="b7150-138">錯誤：404，未找到</span><span class="sxs-lookup"><span data-stu-id="b7150-138">Error : 404, Not Found</span></span>

<span data-ttu-id="b7150-139">診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="b7150-139">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="b7150-140">原因 = 未啟用 SIP 的目的 URI 或不是</span><span class="sxs-lookup"><span data-stu-id="b7150-140">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="b7150-141">存在。</span><span class="sxs-lookup"><span data-stu-id="b7150-141">exist.</span></span>

<span data-ttu-id="b7150-142">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="b7150-142">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="b7150-143">例如，上一個輸出會指出測試失敗的原因是，至少有兩個使用者帳戶之一無效，原因是該帳戶不存在，或是尚未對 Lync Server 啟用該帳戶。</span><span class="sxs-lookup"><span data-stu-id="b7150-143">For example, the previous output states that the test failed because at least one of the two user accounts was not valid, either because the account does not exist or because the account has not been enabled for Lync Server.</span></span> <span data-ttu-id="b7150-144">您可以執行類似如下的命令，確認兩個測試帳戶是否存在，以及是否已為 Lync Server 啟用：</span><span class="sxs-lookup"><span data-stu-id="b7150-144">You can verify the existence of the two test accounts, and whether they were enabled for Lync Server, by running a command similar to the following:</span></span>

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

<span data-ttu-id="b7150-145">如果 Test-CsAVConference 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="b7150-145">If Test-CsAVConference fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="b7150-146">包含 Verbose 參數時 Test-CsAVConference 會傳回每個動作的逐步帳戶，檢查它在檢查指定的使用者是否有權參加 AV 會議時所嘗試的每一個動作。</span><span class="sxs-lookup"><span data-stu-id="b7150-146">When the Verbose parameter is included Test-CsAVConference will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in an AV conference.</span></span> <span data-ttu-id="b7150-147">例如，假設您的測試失敗，且您收到下列診斷：</span><span class="sxs-lookup"><span data-stu-id="b7150-147">For example, suppose that your test fails and you receive the following Diagnosis:</span></span>

<span data-ttu-id="b7150-148">ErrorCode = 1008，Source = accessproxy = litwareinc，Reason = 無法解析 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="b7150-148">ErrorCode=1008,Source=accessproxy.litwareinc.com,Reason=Unable to resolve DNS SRV record</span></span>

<span data-ttu-id="b7150-149">如果您使用 Verbose 參數重新執行測試，傳回的逐步資訊將會包含類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="b7150-149">If you rerun the test using the Verbose parameter, the step-by-step information returned will include output similar to this:</span></span>

<span data-ttu-id="b7150-150">詳細：「註冊」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="b7150-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="b7150-151">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="b7150-151">Sending Registration request:</span></span>

<span data-ttu-id="b7150-152">目標 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7150-152">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7150-153">使用者 Sip 位址 = sip:davidlongmire@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7150-153">User Sip Address = sip:davidlongmire@litwareinc.com</span></span>

<span data-ttu-id="b7150-154">註冊機構埠 = 5061。</span><span class="sxs-lookup"><span data-stu-id="b7150-154">Registrar Port = 5061.</span></span>

<span data-ttu-id="b7150-155">已選取 Auth Type ' Trusted」。</span><span class="sxs-lookup"><span data-stu-id="b7150-155">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="b7150-156">「註冊」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="b7150-156">'Register' activity started.</span></span>

<span data-ttu-id="b7150-157">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="b7150-157">Sending Registration request:</span></span>

<span data-ttu-id="b7150-158">目標 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7150-158">Target Fqdn = atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7150-159">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7150-159">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="b7150-160">註冊機構埠 = 5061。</span><span class="sxs-lookup"><span data-stu-id="b7150-160">Registrar Port = 5061.</span></span>

<span data-ttu-id="b7150-161">已選取 Auth Type ' Trusted」。</span><span class="sxs-lookup"><span data-stu-id="b7150-161">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="b7150-162">無法註冊端點的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="b7150-162">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="b7150-163">如需特定原因，請參閱 ErrorCode。 '</span><span class="sxs-lookup"><span data-stu-id="b7150-163">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="b7150-164">工作流程期間發生</span><span class="sxs-lookup"><span data-stu-id="b7150-164">occurred during Workflow</span></span>

<span data-ttu-id="b7150-165">該輸出的最後一行指出使用者 sip:kenmyer@litwareinc.com 無法向 Lync Server 註冊。</span><span class="sxs-lookup"><span data-stu-id="b7150-165">The last line in that output indicates that the user sip:kenmyer@litwareinc.com was unable to register with Lync Server.</span></span> <span data-ttu-id="b7150-166">這表示您應該確認 SIP 位址 sip:kenmyer@litwareinc.com 是否有效，以及是否已為 Lync Server 啟用相關聯的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7150-166">That means that you should verify that the SIP address sip:kenmyer@litwareinc.com is valid, and that the associated user is enabled for Lync Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b7150-167">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="b7150-167">Reasons why the test might have failed</span></span>

<span data-ttu-id="b7150-168">以下是一些 Test-CsAVConference 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="b7150-168">Here are some common reasons why Test-CsAVConference might fail:</span></span>

  - <span data-ttu-id="b7150-169">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="b7150-169">You specified a user account that is not valid.</span></span> <span data-ttu-id="b7150-170">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="b7150-170">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b7150-171">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b7150-171">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b7150-172">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="b7150-172">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b7150-173">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7150-173">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

