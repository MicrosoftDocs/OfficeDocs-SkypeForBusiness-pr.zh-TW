---
title: Lync Server 2013：測試會議中的共用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="8357e-102">在 Lync Server 2013 中測試在會議中共用</span><span class="sxs-lookup"><span data-stu-id="8357e-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8357e-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="8357e-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8357e-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="8357e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8357e-105">日常</span><span class="sxs-lookup"><span data-stu-id="8357e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8357e-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="8357e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8357e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8357e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8357e-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="8357e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8357e-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8357e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8357e-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsDataConference</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="8357e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="8357e-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8357e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8357e-112">描述</span><span class="sxs-lookup"><span data-stu-id="8357e-112">Description</span></span>

<span data-ttu-id="8357e-113">在 Lync Server 2013 中，資料會議是使用諸如 whiteboarding 或批註等共同作業的任何會議。</span><span class="sxs-lookup"><span data-stu-id="8357e-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="8357e-114">**Test CsDataConference** Cmdlet 可讓您確認一組使用者可以參與資料會議。</span><span class="sxs-lookup"><span data-stu-id="8357e-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8357e-115">執行測試</span><span class="sxs-lookup"><span data-stu-id="8357e-115">Running the test</span></span>

<span data-ttu-id="8357e-116">範例1中所示的命令會確認您可以在 [pool atl-cs-001.litwareinc.com] 上進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="8357e-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="8357e-117">這個命令假設您已為指定的池子設定一對測試使用者。</span><span class="sxs-lookup"><span data-stu-id="8357e-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="8357e-118">如果不存在這樣的測試使用者，命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="8357e-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="8357e-119">範例2所示的命令會測試一對使用者（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登入 Lync Server 2013，然後進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="8357e-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="8357e-120">若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，包含使用者 Pilar 方的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="8357e-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="8357e-121">（因為登入名稱（litwareinc\\pilar）已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="8357e-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="8357e-122">第二個命令會執行相同的動作，這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="8357e-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="8357e-123">使用身分認證物件時，第三個命令會判斷這兩個使用者是否可以登入 Lync Server 2013 並進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="8357e-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="8357e-124">若要執行這項工作，請呼叫**CsDataConference** Cmdlet，以及下列參數： TargetFqdn （註冊機構池的 FQDN）;SenderSipAddress （第一個測試使用者的 SIP 位址）;SenderCredential （包含此相同使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;與 ReceiverCredential （包含其他測試使用者認證的 Windows PowerShell 物件）。</span><span class="sxs-lookup"><span data-stu-id="8357e-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8357e-125">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="8357e-125">Determining success or failure</span></span>

<span data-ttu-id="8357e-126">如果已正確設定資料會議，您將會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="8357e-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8357e-127">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8357e-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8357e-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="8357e-128">Result : Success</span></span>

<span data-ttu-id="8357e-129">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="8357e-129">Latency : 00:00:00</span></span>

<span data-ttu-id="8357e-130">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="8357e-130">Error Message :</span></span>

<span data-ttu-id="8357e-131">自檢</span><span class="sxs-lookup"><span data-stu-id="8357e-131">Diagnosis :</span></span>

<span data-ttu-id="8357e-132">如果指定的使用者無法使用資料共用，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="8357e-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8357e-133">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8357e-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8357e-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="8357e-134">Result : Failure</span></span>

<span data-ttu-id="8357e-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="8357e-135">Latency : 00:00:00</span></span>

<span data-ttu-id="8357e-136">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="8357e-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="8357e-137">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="8357e-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="8357e-138">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="8357e-138">established connection failed because connected host has</span></span>

<span data-ttu-id="8357e-139">無法回應\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="8357e-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="8357e-140">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="8357e-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="8357e-141">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="8357e-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="8357e-142">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="8357e-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="8357e-143">無法回應</span><span class="sxs-lookup"><span data-stu-id="8357e-143">has failed to respond</span></span>

<span data-ttu-id="8357e-144">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061</span><span class="sxs-lookup"><span data-stu-id="8357e-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="8357e-145">自檢</span><span class="sxs-lookup"><span data-stu-id="8357e-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8357e-146">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="8357e-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="8357e-147">以下是**測試 CsDataConference**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="8357e-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="8357e-148">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="8357e-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="8357e-149">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8357e-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="8357e-150">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="8357e-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="8357e-151">執行資料會議的能力取決於已指派給組織會議之使用者的會議原則（在**CsDataConference** Cmdlet 中為「寄件者」）。</span><span class="sxs-lookup"><span data-stu-id="8357e-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="8357e-152">如果召集人不能在會議中加入共同作業（例如，如果他/她的會議原則將 EnableDataCollaboration 屬性設為 False），則**CsDataConference** Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8357e-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="8357e-153">如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="8357e-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

