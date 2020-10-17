---
title: Lync Server 2013：測試在會議中共用
description: Lync Server 2013：測試在會議中共用。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e569a97d102664b64c201af9b60061813df69ef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556239"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="e340f-103">在 Lync Server 2013 中測試在會議中共用</span><span class="sxs-lookup"><span data-stu-id="e340f-103">Testing sharing in conferences in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e340f-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="e340f-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e340f-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="e340f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e340f-106">每日</span><span class="sxs-lookup"><span data-stu-id="e340f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e340f-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="e340f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e340f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e340f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e340f-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e340f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e340f-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e340f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e340f-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsDataConference</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e340f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="e340f-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e340f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e340f-113">描述</span><span class="sxs-lookup"><span data-stu-id="e340f-113">Description</span></span>

<span data-ttu-id="e340f-114">在 Lync Server 2013 中，資料會議是指使用諸如白板或批註等共同作業的任何會議。</span><span class="sxs-lookup"><span data-stu-id="e340f-114">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="e340f-115">**Test-CsDataConference** Cmdlet 可讓您確認一組使用者是否可以參與資料會議。</span><span class="sxs-lookup"><span data-stu-id="e340f-115">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e340f-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="e340f-116">Running the test</span></span>

<span data-ttu-id="e340f-117">範例1所示的命令會驗證是否可以在集區 atl-cs-001.litwareinc.com 上進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="e340f-117">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e340f-118">這個命令假設您已針對指定的集區設定一對測試使用者。</span><span class="sxs-lookup"><span data-stu-id="e340f-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="e340f-119">如果不存在這樣的測試使用者，命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e340f-119">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="e340f-120">範例2所示的命令會測試一對使用者 (litwareinc \\ pilar and litwareinc \\ kenmyer) 登入 Lync Server 2013，然後進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="e340f-120">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="e340f-121">為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 來建立 Windows PowerShell 命令列介面憑證物件，該物件包含使用者 Pilar Ackerman 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="e340f-121">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="e340f-122"> (因為登入名稱 litwareinc \\ pilar 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="e340f-122">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="e340f-123">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="e340f-123">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="e340f-124">使用 credential 物件，第三個命令會判斷這兩位使用者是否可以登入 Lync Server 2013 並進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="e340f-124">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="e340f-125">若要執行此工作，會呼叫 **Test-CsDataConference** Cmdlet，以及下列參數： TargetFqdn (註冊機構集區的 FQDN) ;SenderSipAddress (第一個測試使用者的 SIP 位址) ;SenderCredential (包含此相同使用者之認證的 Windows PowerShell 物件) ;ReceiverSipAddress (其他測試使用者) 的 SIP 位址;和 ReceiverCredential (包含其他測試使用者) 之認證的 Windows PowerShell 物件。</span><span class="sxs-lookup"><span data-stu-id="e340f-125">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e340f-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="e340f-126">Determining success or failure</span></span>

<span data-ttu-id="e340f-127">如果正確設定資料會議，則會收到類似以下的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="e340f-127">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e340f-128">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e340f-128">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e340f-129">結果：成功</span><span class="sxs-lookup"><span data-stu-id="e340f-129">Result : Success</span></span>

<span data-ttu-id="e340f-130">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="e340f-130">Latency : 00:00:00</span></span>

<span data-ttu-id="e340f-131">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="e340f-131">Error Message :</span></span>

<span data-ttu-id="e340f-132">診斷：</span><span class="sxs-lookup"><span data-stu-id="e340f-132">Diagnosis :</span></span>

<span data-ttu-id="e340f-133">如果指定的使用者無法使用資料共用，結果將會顯示為 [ **失敗**]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="e340f-133">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e340f-134">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e340f-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e340f-135">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="e340f-135">Result : Failure</span></span>

<span data-ttu-id="e340f-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="e340f-136">Latency : 00:00:00</span></span>

<span data-ttu-id="e340f-137">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="e340f-137">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="e340f-138">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="e340f-138">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="e340f-139">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="e340f-139">established connection failed because connected host has</span></span>

<span data-ttu-id="e340f-140">無法回應 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="e340f-140">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="e340f-141">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="e340f-141">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="e340f-142">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="e340f-142">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="e340f-143">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="e340f-143">time, or established connection failed because connected host</span></span>

<span data-ttu-id="e340f-144">回應失敗</span><span class="sxs-lookup"><span data-stu-id="e340f-144">has failed to respond</span></span>

<span data-ttu-id="e340f-145">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="e340f-145">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="e340f-146">診斷：</span><span class="sxs-lookup"><span data-stu-id="e340f-146">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e340f-147">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="e340f-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="e340f-148">以下是一些 **Test-CsDataConference** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="e340f-148">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="e340f-149">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="e340f-149">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e340f-150">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e340f-150">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e340f-151">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="e340f-151">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e340f-152">進行資料會議的能力取決於已指派給組織之使用者的會議原則 (**Test-CsDataConference** Cmdlet，也就是 "sender" ) 。</span><span class="sxs-lookup"><span data-stu-id="e340f-152">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="e340f-153">如果召集人不允許在其會議中包含共同作業活動 (例如，如果其會議原則的 EnableDataCollaboration 屬性設定為 False) 則 **Test-CsDataConference** 指令程式將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e340f-153">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="e340f-154">如果 Edge Server 設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e340f-154">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

