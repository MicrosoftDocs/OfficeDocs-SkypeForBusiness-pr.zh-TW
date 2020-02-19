---
title: Lync Server 2013： 測試協力廠商音訊會議
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
ms.openlocfilehash: 8d7012a318a6da720f07af5ba39248090f448a08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a><span data-ttu-id="29ffe-102">在 Lync Server 2013 中進行測試協力廠商音訊會議</span><span class="sxs-lookup"><span data-stu-id="29ffe-102">Testing third-party audio conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29ffe-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="29ffe-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29ffe-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="29ffe-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29ffe-105">每日</span><span class="sxs-lookup"><span data-stu-id="29ffe-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29ffe-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="29ffe-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29ffe-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ffe-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29ffe-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="29ffe-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29ffe-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="29ffe-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29ffe-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Test-csaudioconferencingprovider cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="29ffe-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAudioConferencingProvider cmdlet.</span></span> <span data-ttu-id="29ffe-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="29ffe-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29ffe-112">描述</span><span class="sxs-lookup"><span data-stu-id="29ffe-112">Description</span></span>

<span data-ttu-id="29ffe-113">音訊會議提供者是組織可利用會議服務的協力廠商公司。</span><span class="sxs-lookup"><span data-stu-id="29ffe-113">An audio conferencing provider is a third-party company that provides organizations with conferencing services.</span></span> <span data-ttu-id="29ffe-114">除此之外，音訊會議提供者可讓使用者位於關閉網站，而未連線至公司網路或網際網路，參與會議或會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="29ffe-114">Among other things, audio conferencing providers enable users located off site, and not connected to the corporate network or the Internet, to participate in the audio portion of a conference or meeting.</span></span> <span data-ttu-id="29ffe-115">音訊會議提供者通常會提供高階服務，例如即時翻譯，轉譯，和 live 每個會議的操作員協助。</span><span class="sxs-lookup"><span data-stu-id="29ffe-115">Audio conferencing providers often provide high-end services such as live translation, transcription, and live per-conference operator assistance.</span></span>

<span data-ttu-id="29ffe-116">**Test-csaudioconferencingprovider** cmdlet 用來確認使用者能夠連線至他/她音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="29ffe-116">The **Test-CsAudioConferencingProvider** cmdlet is used to verify that a user is able to make a connection to his or her audio conferencing provider.</span></span> <span data-ttu-id="29ffe-117">請注意，此指令程式可以執行下列兩種方式之一。</span><span class="sxs-lookup"><span data-stu-id="29ffe-117">Note that this cmdlet can be run in one of two ways.</span></span> <span data-ttu-id="29ffe-118">許多系統管理員會使用 CsHealthMonitoringConfiguration Cmdlet 來設定其每個登錄器集區的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="29ffe-118">Many administrators will use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="29ffe-119">這些測試使用者代表一組已經與綜合交易搭配使用預先設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="29ffe-119">These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="29ffe-120">（通常是這些是測試帳戶並不屬於實際使用者的帳戶）。如果測試使用者已為集區，系統管理員可以執行**Test-csaudioconferencingprovider** cmdlet，針對該集區不必指定的身分識別 （和提供的認證） 測試中所涉及的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="29ffe-120">(Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsAudioConferencingProvider** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.</span></span>

<span data-ttu-id="29ffe-121">或者，系統管理員可以執行**Test-csaudioconferencingprovider**指令程式使用的實際使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="29ffe-121">Alternatively, administrators can run the **Test-CsAudioConferencingProvider** cmdlet using an actual user account.</span></span> <span data-ttu-id="29ffe-122">如果您決定要進行測試使用的實際使用者帳戶必須提供登入名稱與該帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="29ffe-122">If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29ffe-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="29ffe-123">Running the test</span></span>

<span data-ttu-id="29ffe-124">範例 1 會檢查以查看所定義的集區 atl-cs-001.litwareinc.com 的測試使用者是否能夠連線至他/她音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="29ffe-124">Example 1 checks to see if a test user defined for the pool atl-cs-001.litwareinc.com is able to connect to his or her audio conferencing provider.</span></span> <span data-ttu-id="29ffe-125">此命令需要至少一個測試使用者定義的集區。</span><span class="sxs-lookup"><span data-stu-id="29ffe-125">This command requires that at least one test user be defined for the pool.</span></span> <span data-ttu-id="29ffe-126">如果沒有任何測試使用者已定義為 atl-cs-001.litwareinc.com，命令將會失敗;這是因為**Test-csaudioconferencingprovider**指令程式不會知道哪些使用者可運用在測試。</span><span class="sxs-lookup"><span data-stu-id="29ffe-126">If no test users have been defined for atl-cs-001.litwareinc.com, then the command will fail; that's because the **Test-CsAudioConferencingProvider** cmdlet will not know which user to employ in the test.</span></span> <span data-ttu-id="29ffe-127">如果您還沒有定義的集區的測試使用者，就必須納入 UserSipAddress 參數，並驗證與音訊會議提供者的連線時，此命令應採用的使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="29ffe-127">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user account that the command should employ when verifying the connection with an audio conferencing provider.</span></span>

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

<span data-ttu-id="29ffe-128">範例 2 所示的命令會測試特定使用者的能力 (litwareinc\\kenmyer) 連線至其音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="29ffe-128">The commands shown in Example 2 test the ability of a specific user (litwareinc\\kenmyer) to connect to his audio conferencing provider.</span></span> <span data-ttu-id="29ffe-129">若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立包含其名稱和密碼的使用者： Ken Myer 的 Windows PowerShell 命令列介面認證物件。</span><span class="sxs-lookup"><span data-stu-id="29ffe-129">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credentials object containing the name and password of the user Ken Myer.</span></span> <span data-ttu-id="29ffe-130">(因為登入名稱 litwareinc\\kenmyer 已經包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken myer 的使用者帳戶的密碼。)產生的認證物件儲存在名為 $credential 的變數。</span><span class="sxs-lookup"><span data-stu-id="29ffe-130">(Because the logon name litwareinc\\kenmyer has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Ken Myer account.) The resulting credentials object is stored in a variable named $credential.</span></span>

<span data-ttu-id="29ffe-131">第二個命令會接著檢查看看是否這個使用者可以連線至其音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="29ffe-131">The second command then checks to see if this user can connect to his audio conferencing provider.</span></span> <span data-ttu-id="29ffe-132">若要執行這項工作，Test-csaudioconferencingprovider 呼叫 cmdlet 時，以及三個參數： TargetFqdn (之登錄器集區 FQDN);UserCredential （包含 Ken Myer 的使用者認證的 Windows PowerShell 物件）;和 UserSipAddress （對應至提供的使用者認證的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="29ffe-132">To carry out this task, the Test-CsAudioConferencingProvider cmdlet is called, along with three parameters: TargetFqdn (the FQDN of the Registrar pool); UserCredential (the Windows PowerShell object containing Ken Myer's user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29ffe-133">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="29ffe-133">Determining success or failure</span></span>

<span data-ttu-id="29ffe-134">如果已正確設定音訊會議提供者，您會收到類似，具有標示為 Result 屬性的輸出**成功：**</span><span class="sxs-lookup"><span data-stu-id="29ffe-134">If the audio conferencing provider is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="29ffe-135">目標 Fqdn: atl-cs-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29ffe-135">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="29ffe-136">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="29ffe-136">Result : Success</span></span>

<span data-ttu-id="29ffe-137">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="29ffe-137">Latency : 00:00:00</span></span>

<span data-ttu-id="29ffe-138">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="29ffe-138">Error Message :</span></span>

<span data-ttu-id="29ffe-139">診斷：</span><span class="sxs-lookup"><span data-stu-id="29ffe-139">Diagnosis :</span></span>

<span data-ttu-id="29ffe-140">如果指定的使用者無法登入或登出，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="29ffe-140">If the specified user can't log on or log off, the Result will be shown as a **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="29ffe-141">目標 Fqdn: atl-cs-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29ffe-141">Target Fqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="29ffe-142">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="29ffe-142">Result : Failure</span></span>

<span data-ttu-id="29ffe-143">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="29ffe-143">Latency : 00:00:00</span></span>

<span data-ttu-id="29ffe-144">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="29ffe-144">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="29ffe-145">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="29ffe-145">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="29ffe-146">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="29ffe-146">established connection failed because connected host has</span></span>

<span data-ttu-id="29ffe-147">失敗回應\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="29ffe-147">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="29ffe-148">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="29ffe-148">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="29ffe-149">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="29ffe-149">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="29ffe-150">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="29ffe-150">time, or established connection failed because connected host</span></span>

<span data-ttu-id="29ffe-151">失敗回應</span><span class="sxs-lookup"><span data-stu-id="29ffe-151">has failed to respond</span></span>

<span data-ttu-id="29ffe-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="29ffe-152">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="29ffe-153">診斷：</span><span class="sxs-lookup"><span data-stu-id="29ffe-153">Diagnosis :</span></span>

<span data-ttu-id="29ffe-154">例如，先前的輸出包含 「 連線的對象並未正確回應 「 附註這通常表示 Edge Server 的問題。</span><span class="sxs-lookup"><span data-stu-id="29ffe-154">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29ffe-155">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="29ffe-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="29ffe-156">以下是一些常見的原因為何**Test-csaudioconferencingprovider**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="29ffe-156">Here are some common reasons why **Test-CsAudioConferencingProvider** might fail:</span></span>

  - <span data-ttu-id="29ffe-157">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="29ffe-157">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="29ffe-158">上述範例所示，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="29ffe-158">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="29ffe-159">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="29ffe-159">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="29ffe-160">請注意，如果**Test-csaudioconferencingprovider**指令程式所採用的使用者尚未指派音訊會議提供者，則測試會失敗。</span><span class="sxs-lookup"><span data-stu-id="29ffe-160">Note that the test will fail if the user employed by the **Test-CsAudioConferencingProvider** cmdlet has not been assigned an audio conferencing provider.</span></span>

  - <span data-ttu-id="29ffe-161">如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="29ffe-161">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

