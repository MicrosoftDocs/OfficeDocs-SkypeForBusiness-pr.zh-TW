---
title: Lync Server 2013：測試應用程式共用
description: Lync Server 2013：測試應用程式共用。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560719"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="1cd81-103">在 Lync Server 2013 中測試應用程式共用</span><span class="sxs-lookup"><span data-stu-id="1cd81-103">Testing application sharing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cd81-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="1cd81-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cd81-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="1cd81-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1cd81-106">每日</span><span class="sxs-lookup"><span data-stu-id="1cd81-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cd81-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="1cd81-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1cd81-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1cd81-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cd81-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="1cd81-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1cd81-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1cd81-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1cd81-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsASConference Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="1cd81-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="1cd81-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1cd81-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1cd81-113">描述</span><span class="sxs-lookup"><span data-stu-id="1cd81-113">Description</span></span>

<span data-ttu-id="1cd81-114">**Test-CsASConference** Cmdlet 會驗證一組測試使用者是否可以參與包含應用程式共用的線上會議。</span><span class="sxs-lookup"><span data-stu-id="1cd81-114">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="1cd81-115">若要這麼做，指令程式會向 Lync Server 2013 註冊兩位使用者，然後使用其中一個使用者帳戶來建立包含應用程式共用的新會議。</span><span class="sxs-lookup"><span data-stu-id="1cd81-115">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="1cd81-116">然後，此 Cmdlet 會驗證第二個使用者是否可以加入該會議。</span><span class="sxs-lookup"><span data-stu-id="1cd81-116">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1cd81-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="1cd81-117">Running the test</span></span>

<span data-ttu-id="1cd81-118">範例1所示的命令會驗證是否可以在集區 atl-cs-001.litwareinc.com 上進行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="1cd81-118">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1cd81-119">這個命令假設您已針對指定的集區設定一對測試使用者。</span><span class="sxs-lookup"><span data-stu-id="1cd81-119">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="1cd81-120">如果不存在這樣的測試使用者，命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1cd81-120">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="1cd81-121">範例2會測試 Join 啟動器服務加入集區 atl-cs-001.litwareinc.com 上的應用程式共用會議的能力。</span><span class="sxs-lookup"><span data-stu-id="1cd81-121">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="1cd81-122">請注意，此命令只會測試服務本身;您不需要任何行動裝置即可執行命令。</span><span class="sxs-lookup"><span data-stu-id="1cd81-122">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="1cd81-123">範例2所示的命令會測試一對使用者 (litwareinc \\ pilar and litwareinc \\ kenmyer) 登入 Lync Server 2013，然後執行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="1cd81-123">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="1cd81-124">為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面憑證物件，該物件包含使用者 Pilar Ackerman 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="1cd81-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="1cd81-125"> (因為登入名稱 litwareinc \\ pilar 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="1cd81-125">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="1cd81-126">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="1cd81-126">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="1cd81-127">使用 credential 物件，第三個命令會判斷這兩位使用者是否可以登入 Lync Server 2013 並執行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="1cd81-127">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="1cd81-128">若要執行此工作，會呼叫 **Test-CsASConference** Cmdlet，以及下列參數： TargetFqdn (註冊機構集區的 FQDN) ;SenderSipAddress (第一個測試使用者的 SIP 位址) ;SenderCredential (包含此相同使用者之認證的 Windows PowerShell 物件) ;ReceiverSipAddress (其他測試使用者) 的 SIP 位址;和 ReceiverCredential (包含其他測試使用者) 之認證的 Windows PowerShell 物件。</span><span class="sxs-lookup"><span data-stu-id="1cd81-128">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1cd81-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="1cd81-129">Determining success or failure</span></span>

<span data-ttu-id="1cd81-130">若應用程式共用已正確設定，則會收到類似以下的輸出，其 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="1cd81-130">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1cd81-131">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1cd81-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1cd81-132">結果：成功</span><span class="sxs-lookup"><span data-stu-id="1cd81-132">Result : Success</span></span>

<span data-ttu-id="1cd81-133">延遲：00:00:01</span><span class="sxs-lookup"><span data-stu-id="1cd81-133">Latency : 00:00:01</span></span>

<span data-ttu-id="1cd81-134">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="1cd81-134">Error Message :</span></span>

<span data-ttu-id="1cd81-135">診斷：</span><span class="sxs-lookup"><span data-stu-id="1cd81-135">Diagnosis :</span></span>

<span data-ttu-id="1cd81-136">如果指定的使用者無法共用應用程式，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="1cd81-136">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1cd81-137">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1cd81-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1cd81-138">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="1cd81-138">Result : Failure</span></span>

<span data-ttu-id="1cd81-139">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="1cd81-139">Latency : 00:00:00</span></span>

<span data-ttu-id="1cd81-140">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="1cd81-140">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="1cd81-141">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="1cd81-141">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="1cd81-142">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="1cd81-142">established connection failed because connected host has</span></span>

<span data-ttu-id="1cd81-143">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="1cd81-143">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="1cd81-144">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="1cd81-144">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="1cd81-145">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="1cd81-145">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="1cd81-146">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="1cd81-146">time, or established connection failed because connected host</span></span>

<span data-ttu-id="1cd81-147">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="1cd81-147">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="1cd81-148">診斷：</span><span class="sxs-lookup"><span data-stu-id="1cd81-148">Diagnosis :</span></span>

<span data-ttu-id="1cd81-149">例如，上一個輸出包含的附注「連接的團體沒有正確回應」，這通常表示 Edge Server 發生問題。</span><span class="sxs-lookup"><span data-stu-id="1cd81-149">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1cd81-150">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="1cd81-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="1cd81-151">以下是一些 **Test-CsASConference** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="1cd81-151">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="1cd81-152">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="1cd81-152">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="1cd81-153">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1cd81-153">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="1cd81-154">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="1cd81-154">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="1cd81-155">如果測試使用者已獲指派會議原則，可防止使用者使用應用程式共用，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1cd81-155">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="1cd81-156">如果 Edge Server 設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1cd81-156">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1cd81-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1cd81-157">See Also</span></span>


[<span data-ttu-id="1cd81-158">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cd81-158">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="1cd81-159">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="1cd81-159">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

