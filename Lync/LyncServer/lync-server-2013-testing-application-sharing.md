---
title: Lync Server 2013：測試應用程式共用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77a65e2dbea8ca0df01fab37c08f47c8e7d0c5b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="fce8f-102">在 Lync Server 2013 中測試應用程式共用</span><span class="sxs-lookup"><span data-stu-id="fce8f-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fce8f-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="fce8f-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fce8f-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="fce8f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fce8f-105">日常</span><span class="sxs-lookup"><span data-stu-id="fce8f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fce8f-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="fce8f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fce8f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fce8f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fce8f-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="fce8f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fce8f-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fce8f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fce8f-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsASConference Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="fce8f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="fce8f-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fce8f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fce8f-112">描述</span><span class="sxs-lookup"><span data-stu-id="fce8f-112">Description</span></span>

<span data-ttu-id="fce8f-113">**Test CsASConference** Cmdlet 會確認一組測試使用者可以參與包含應用程式共用的線上會議。</span><span class="sxs-lookup"><span data-stu-id="fce8f-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="fce8f-114">若要這樣做，Cmdlet 會使用 Lync Server 2013 登錄兩個使用者，然後使用其中一個使用者帳戶來建立包含應用程式共用的新會議。</span><span class="sxs-lookup"><span data-stu-id="fce8f-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="fce8f-115">然後，此 Cmdlet 會驗證第二個使用者是否可以加入該會議。</span><span class="sxs-lookup"><span data-stu-id="fce8f-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fce8f-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="fce8f-116">Running the test</span></span>

<span data-ttu-id="fce8f-117">範例1中所示的命令會驗證是否可以在 [pool atl-cs-001.litwareinc.com] 上執行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="fce8f-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fce8f-118">這個命令假設您已為指定的池子設定一對測試使用者。</span><span class="sxs-lookup"><span data-stu-id="fce8f-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="fce8f-119">如果不存在這樣的測試使用者，命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="fce8f-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="fce8f-120">範例2測試 Join 啟動器服務參與 [池 atl-cs-001.litwareinc.com] 上的應用程式共用會議的能力。</span><span class="sxs-lookup"><span data-stu-id="fce8f-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="fce8f-121">請注意，這個命令只會測試服務本身，若要執行命令，您不需要任何行動裝置。</span><span class="sxs-lookup"><span data-stu-id="fce8f-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="fce8f-122">範例2所示的命令會測試一對使用者（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登入 Lync Server 2013，然後執行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="fce8f-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="fce8f-123">若要這樣做，範例中的第一個命令會使用取得認證 Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，包含使用者 Pilar 方的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="fce8f-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="fce8f-124">（因為登入名稱（litwareinc\\pilar）已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="fce8f-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="fce8f-125">第二個命令會執行相同的動作，這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="fce8f-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="fce8f-126">使用身分認證物件時，第三個命令會判斷這兩個使用者是否可以登入 Lync Server 2013，並執行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="fce8f-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="fce8f-127">若要執行這項工作，請呼叫**CsASConference** Cmdlet，以及下列參數： TargetFqdn （註冊機構池的 FQDN）;SenderSipAddress （第一個測試使用者的 SIP 位址）;SenderCredential （包含此相同使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;與 ReceiverCredential （包含其他測試使用者認證的 Windows PowerShell 物件）。</span><span class="sxs-lookup"><span data-stu-id="fce8f-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fce8f-128">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="fce8f-128">Determining success or failure</span></span>

<span data-ttu-id="fce8f-129">如果應用程式共用設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="fce8f-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="fce8f-130">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fce8f-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fce8f-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="fce8f-131">Result : Success</span></span>

<span data-ttu-id="fce8f-132">延遲：00:00:01</span><span class="sxs-lookup"><span data-stu-id="fce8f-132">Latency : 00:00:01</span></span>

<span data-ttu-id="fce8f-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="fce8f-133">Error Message :</span></span>

<span data-ttu-id="fce8f-134">自檢</span><span class="sxs-lookup"><span data-stu-id="fce8f-134">Diagnosis :</span></span>

<span data-ttu-id="fce8f-135">如果指定的使用者無法共用應用程式，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="fce8f-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fce8f-136">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fce8f-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fce8f-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="fce8f-137">Result : Failure</span></span>

<span data-ttu-id="fce8f-138">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="fce8f-138">Latency : 00:00:00</span></span>

<span data-ttu-id="fce8f-139">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="fce8f-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="fce8f-140">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="fce8f-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="fce8f-141">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="fce8f-141">established connection failed because connected host has</span></span>

<span data-ttu-id="fce8f-142">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="fce8f-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="fce8f-143">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="fce8f-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="fce8f-144">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="fce8f-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="fce8f-145">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="fce8f-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="fce8f-146">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="fce8f-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="fce8f-147">自檢</span><span class="sxs-lookup"><span data-stu-id="fce8f-147">Diagnosis :</span></span>

<span data-ttu-id="fce8f-148">例如，前一個輸出包含「已連接的一方沒有正確回應」的筆記，這通常表示邊緣伺服器發生問題。</span><span class="sxs-lookup"><span data-stu-id="fce8f-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fce8f-149">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="fce8f-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="fce8f-150">以下是**測試 CsASConference**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="fce8f-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="fce8f-151">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="fce8f-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="fce8f-152">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="fce8f-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="fce8f-153">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="fce8f-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="fce8f-154">如果測試使用者指派的會議原則無法使用應用程式共用，這個命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="fce8f-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="fce8f-155">如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="fce8f-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fce8f-156">請參閱</span><span class="sxs-lookup"><span data-stu-id="fce8f-156">See Also</span></span>


[<span data-ttu-id="fce8f-157">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="fce8f-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="fce8f-158">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="fce8f-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

