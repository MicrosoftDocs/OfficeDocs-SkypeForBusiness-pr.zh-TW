---
title: Lync Server 2013：測試協力廠商音訊會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="95925-102">在 Lync Server 2013 中測試協力廠商音訊會議</span><span class="sxs-lookup"><span data-stu-id="95925-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95925-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="95925-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95925-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="95925-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="95925-105">日常</span><span class="sxs-lookup"><span data-stu-id="95925-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95925-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="95925-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="95925-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95925-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95925-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="95925-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="95925-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="95925-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="95925-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsAudioConferencingProvider Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="95925-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="95925-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="95925-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="95925-112">描述</span><span class="sxs-lookup"><span data-stu-id="95925-112">Description</span></span>

<span data-ttu-id="95925-113">音訊會議提供者是協力廠商的公司，提供含會議服務的組織。</span><span class="sxs-lookup"><span data-stu-id="95925-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="95925-114">除了其他事項之外，音訊會議提供者還能讓使用者離開網站，而且未連線至公司網路或網際網路，以參與會議或會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="95925-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="95925-115">音訊會議提供者通常會提供高端服務，例如即時翻譯、操作，以及每個會議的即時操作員協助。</span><span class="sxs-lookup"><span data-stu-id="95925-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="95925-116">**CsAudioConferencingProvider** Cmdlet 可用來驗證使用者是否能夠連線到他的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="95925-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="95925-117">請注意，這個 Cmdlet 可以使用兩種方法的其中一種執行。</span><span class="sxs-lookup"><span data-stu-id="95925-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="95925-118">許多系統管理員會使用 CsHealthMonitoringConfiguration Cmdlet 來針對其每個註冊機構池設定測試使用者。</span><span class="sxs-lookup"><span data-stu-id="95925-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="95925-119">這些測試使用者代表一組預配置的使用者帳戶，可與綜合交易搭配使用。</span><span class="sxs-lookup"><span data-stu-id="95925-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="95925-120">（通常，這些是測試帳戶，而不是屬於實際使用者的帳戶。）如果測試使用者是針對某個池進行設定，系統管理員可以針對該池執行**Test CsAudioConferencingProvider** Cmdlet，而不需指定測試中所涉及之使用者帳戶的身分識別（並提供認證）。</span><span class="sxs-lookup"><span data-stu-id="95925-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="95925-121">或者，管理員可以使用實際的使用者帳戶來執行**Test CsAudioConferencingProvider** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95925-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="95925-122">如果您決定使用實際的使用者帳戶進行測試，您將需要提供該帳戶的登入名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="95925-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="95925-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="95925-123">Running the test</span></span>

<span data-ttu-id="95925-124">範例1會檢查是否可連線至其音訊會議提供者，以查看為 [池 atl-cs-001.litwareinc.com] 定義的測試使用者是否能夠連線。</span><span class="sxs-lookup"><span data-stu-id="95925-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="95925-125">這個命令要求至少為池子定義一個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="95925-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="95925-126">如果沒有為 atl-cs-001.litwareinc.com 定義測試使用者，則命令會失敗;這是因為**CsAudioConferencingProvider** Cmdlet 不會知道要在測試中使用哪個使用者。</span><span class="sxs-lookup"><span data-stu-id="95925-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="95925-127">如果您沒有為某個池定義測試使用者，則您必須在驗證與音訊會議提供者的連線時，加入 UserSipAddress 參數以及該命令應使用的使用者帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="95925-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="95925-128">範例2所示的命令會測試特定使用者（litwareinc\\kenmyer）的功能，以連接到他的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="95925-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="95925-129">若要這樣做，範例中的第一個命令會使用 [取得認證 Cmdlet] 來建立 Windows PowerShell 命令列介面認證物件，包含使用者 Ken Myer 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="95925-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="95925-130">（因為登入名稱 litwareinc\\kenmyer 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken Myer 帳戶的密碼）。產生的認證物件會儲存在名為 $credential 的變數中。</span><span class="sxs-lookup"><span data-stu-id="95925-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="95925-131">然後，第二個命令會檢查此使用者是否可以連線到他的音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="95925-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="95925-132">若要執行這項工作，請呼叫 CsAudioConferencingProvider Cmdlet，以及三個參數： TargetFqdn （註冊機構池的 FQDN）;UserCredential （包含 Ken Myer 使用者認證的 Windows PowerShell 物件）;與 UserSipAddress （與提供的使用者認證相對應的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="95925-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="95925-133">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="95925-133">Determining success or failure</span></span>

<span data-ttu-id="95925-134">如果音訊會議提供者設定正確，您將會收到與此類似的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="95925-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="95925-135">目標 Fqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="95925-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="95925-136">結果：成功</span><span class="sxs-lookup"><span data-stu-id="95925-136">Result : Success</span></span>

<span data-ttu-id="95925-137">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="95925-137">Latency : 00:00:00</span></span>

<span data-ttu-id="95925-138">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="95925-138">Error Message :</span></span>

<span data-ttu-id="95925-139">自檢</span><span class="sxs-lookup"><span data-stu-id="95925-139">Diagnosis :</span></span>

<span data-ttu-id="95925-140">如果指定的使用者無法登入或登出，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="95925-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="95925-141">目標 Fqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="95925-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="95925-142">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="95925-142">Result : Failure</span></span>

<span data-ttu-id="95925-143">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="95925-143">Latency : 00:00:00</span></span>

<span data-ttu-id="95925-144">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="95925-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="95925-145">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="95925-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="95925-146">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="95925-146">established connection failed because connected host has</span></span>

<span data-ttu-id="95925-147">無法回應\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="95925-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="95925-148">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="95925-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="95925-149">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="95925-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="95925-150">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="95925-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="95925-151">無法回應</span><span class="sxs-lookup"><span data-stu-id="95925-151">has failed to respond</span></span>

<span data-ttu-id="95925-152">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="95925-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="95925-153">自檢</span><span class="sxs-lookup"><span data-stu-id="95925-153">Diagnosis :</span></span>

<span data-ttu-id="95925-154">例如，前一個輸出包含「已連接的一方沒有正確回應」的筆記，這通常表示邊緣伺服器發生問題。</span><span class="sxs-lookup"><span data-stu-id="95925-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="95925-155">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="95925-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="95925-156">以下是**測試 CsAudioConferencingProvider**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="95925-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="95925-157">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="95925-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="95925-158">如上一個範例所示，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="95925-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="95925-159">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="95925-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="95925-160">請注意，如果**CsAudioConferencingProvider** Cmdlet 所使用的使用者尚未獲指派音訊會議提供者，測試就會失敗。</span><span class="sxs-lookup"><span data-stu-id="95925-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="95925-161">如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="95925-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

