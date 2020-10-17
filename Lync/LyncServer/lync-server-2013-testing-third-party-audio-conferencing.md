---
title: Lync Server 2013：測試協力廠商音訊會議
description: Lync Server 2013：測試協力廠商音訊會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f009d95834768d8a4e6619a79ff1f3be0a2b92bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556099"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="7e198-103">在 Lync Server 2013 中測試協力廠商音訊會議</span><span class="sxs-lookup"><span data-stu-id="7e198-103">Testing third-party audio conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e198-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="7e198-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e198-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="7e198-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7e198-106">每日</span><span class="sxs-lookup"><span data-stu-id="7e198-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e198-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="7e198-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7e198-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e198-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e198-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="7e198-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7e198-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7e198-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7e198-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAudioConferencingProvider Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7e198-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="7e198-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7e198-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7e198-113">描述</span><span class="sxs-lookup"><span data-stu-id="7e198-113">Description</span></span>

<span data-ttu-id="7e198-114">音訊會議提供者是協力廠商公司，為組織提供會議服務。</span><span class="sxs-lookup"><span data-stu-id="7e198-114">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="7e198-115">除了其他事項之外，音訊會議提供者也可讓使用者進入離站網站，而不是連線至公司網路或網際網路，以參與會議或會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="7e198-115">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="7e198-116">音訊會議提供者通常會提供高端服務，例如即時翻譯、會議和即時的每一會議操作員協助。</span><span class="sxs-lookup"><span data-stu-id="7e198-116">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="7e198-117">**Test-CsAudioConferencingProvider** Cmdlet 是用來確認使用者是否可以連線到其音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="7e198-117">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="7e198-118">請注意，此 Cmdlet 可以以兩種方式之一執行。</span><span class="sxs-lookup"><span data-stu-id="7e198-118">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="7e198-119">許多系統管理員會使用 CsHealthMonitoringConfiguration Cmdlet 來設定其每個登錄器集區的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="7e198-119">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="7e198-120">這些測試使用者代表一組已預先設定為搭配綜合交易的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7e198-120">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="7e198-121"> (通常是測試帳戶，而不是屬於實際使用者的帳戶。 ) 如果針對集區設定測試使用者，系統管理員可以對該集區執行 **Test-CsAudioConferencingProvider** Cmdlet，而不需要指定 (的身分識別，並為) 所涉及的使用者帳戶提供認證。</span><span class="sxs-lookup"><span data-stu-id="7e198-121">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="7e198-122">管理員也可以使用實際的使用者帳戶來執行 **Test-CsAudioConferencingProvider** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7e198-122">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="7e198-123">如果您決定使用實際的使用者帳戶進行測試，則需要提供該帳戶的登入名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="7e198-123">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7e198-124">執行測試</span><span class="sxs-lookup"><span data-stu-id="7e198-124">Running the test</span></span>

<span data-ttu-id="7e198-125">範例1會檢查是否為集區 atl-cs-001.litwareinc.com 定義的測試使用者能夠連線到其音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="7e198-125">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="7e198-126">這個命令要求為集區至少定義一個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="7e198-126">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="7e198-127">若尚未定義 atl-cs-001.litwareinc.com 的測試使用者，命令將會失敗。這是因為 **Test-CsAudioConferencingProvider** Cmdlet 不會知道要在測試中使用哪個使用者。</span><span class="sxs-lookup"><span data-stu-id="7e198-127">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="7e198-128">若尚未定義集區的測試使用者，您必須加入 UserSipAddress 參數，以及在使用音訊會議提供者驗證連線時，應使用該命令的使用者帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="7e198-128">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="7e198-129">範例2所示的命令會測試特定使用者 (litwareinc \\ kenmyer) 的功能，以連接到他的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="7e198-129">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="7e198-130">為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面認證物件，該物件包含使用者 Ken Myer 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="7e198-130">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="7e198-131"> (因為登入名稱 litwareinc \\ kenmyer 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Ken Myer 帳戶的密碼。 ) 產生的認證物件會儲存在名為 $credential 的變數中。</span><span class="sxs-lookup"><span data-stu-id="7e198-131">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="7e198-132">然後，第二個命令會檢查此使用者是否可以連接到其音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="7e198-132">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="7e198-133">若要執行此工作，會呼叫 Test-CsAudioConferencingProvider Cmdlet 及三個參數： TargetFqdn (註冊機構集區的 FQDN) ;UserCredential (包含 Ken Myer 之使用者認證) 的 Windows PowerShell 物件。和 UserSipAddress (與所提供使用者認證) 相對應的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="7e198-133">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7e198-134">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="7e198-134">Determining success or failure</span></span>

<span data-ttu-id="7e198-135">如果已正確設定音訊會議提供者，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="7e198-135">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7e198-136">目標 Fqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e198-136">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="7e198-137">結果：成功</span><span class="sxs-lookup"><span data-stu-id="7e198-137">Result : Success</span></span>

<span data-ttu-id="7e198-138">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="7e198-138">Latency : 00:00:00</span></span>

<span data-ttu-id="7e198-139">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="7e198-139">Error Message :</span></span>

<span data-ttu-id="7e198-140">診斷：</span><span class="sxs-lookup"><span data-stu-id="7e198-140">Diagnosis :</span></span>

<span data-ttu-id="7e198-141">如果指定的使用者無法登入或登出，結果將會顯示為 **失敗**，而且會在錯誤和診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="7e198-141">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7e198-142">目標 Fqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7e198-142">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="7e198-143">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="7e198-143">Result : Failure</span></span>

<span data-ttu-id="7e198-144">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="7e198-144">Latency : 00:00:00</span></span>

<span data-ttu-id="7e198-145">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="7e198-145">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="7e198-146">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="7e198-146">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="7e198-147">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="7e198-147">established connection failed because connected host has</span></span>

<span data-ttu-id="7e198-148">無法回應 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="7e198-148">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="7e198-149">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="7e198-149">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="7e198-150">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="7e198-150">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="7e198-151">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="7e198-151">time, or established connection failed because connected host</span></span>

<span data-ttu-id="7e198-152">回應失敗</span><span class="sxs-lookup"><span data-stu-id="7e198-152">has failed to respond</span></span>

<span data-ttu-id="7e198-153">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="7e198-153">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="7e198-154">診斷：</span><span class="sxs-lookup"><span data-stu-id="7e198-154">Diagnosis :</span></span>

<span data-ttu-id="7e198-155">例如，上一個輸出包含的附注「連接的團體沒有正確回應」，這通常表示 Edge Server 發生問題。</span><span class="sxs-lookup"><span data-stu-id="7e198-155">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7e198-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="7e198-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="7e198-157">以下是一些 **Test-CsAudioConferencingProvider** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="7e198-157">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="7e198-158">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="7e198-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="7e198-159">如先前的範例所示，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="7e198-159">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="7e198-160">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="7e198-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="7e198-161">請注意，如果 **Test-CsAudioConferencingProvider** Cmdlet 所採用的使用者尚未獲指派音訊會議提供者，則測試會失敗。</span><span class="sxs-lookup"><span data-stu-id="7e198-161">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="7e198-162">如果 Edge Server 設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="7e198-162">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

