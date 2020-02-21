---
title: Lync Server 2013： 測試應用程式共用
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
ms.openlocfilehash: c82ecab8883a6ccb5e6573d1d164e41648f14bfe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-application-sharing-in-lync-server-2013"></a><span data-ttu-id="9c2f6-102">Lync Server 2013 中共用的測試應用程式</span><span class="sxs-lookup"><span data-stu-id="9c2f6-102">Testing application sharing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c2f6-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="9c2f6-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c2f6-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="9c2f6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9c2f6-105">每日</span><span class="sxs-lookup"><span data-stu-id="9c2f6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c2f6-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="9c2f6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9c2f6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c2f6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c2f6-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="9c2f6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9c2f6-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9c2f6-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Test-csasconference cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsASConference cmdlet.</span></span> <span data-ttu-id="9c2f6-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9c2f6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9c2f6-112">說明</span><span class="sxs-lookup"><span data-stu-id="9c2f6-112">Description</span></span>

<span data-ttu-id="9c2f6-113">**Test-csasconference** cmdlet 會驗證測試使用者的一組可參與線上會議，其中包含應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-113">The **Test-CsASConference** cmdlet verifies that a pair of test users can participate in an online conference that includes application sharing.</span></span> <span data-ttu-id="9c2f6-114">若要這麼做，cmdlet 會登錄兩位使用者與 Lync Server 2013 中，並再使用其中一個使用者帳戶建立新的會議，其中包含應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-114">To do this, the cmdlet registers the two users with Lync Server 2013, and then it uses one of the user accounts to create a new conference that includes applications sharing.</span></span> <span data-ttu-id="9c2f6-115">然後指令程式會驗證第二個使用者就可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-115">The cmdlet then verifies that the second user is able to join that conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9c2f6-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="9c2f6-116">Running the test</span></span>

<span data-ttu-id="9c2f6-117">範例 1 所示的命令會驗證應用程式共用會議，可以在集區 atl-cs-001.litwareinc.com 上進行。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-117">The command shown in Example 1 verifies that an Application Sharing conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9c2f6-118">這個命令會假設您已設定的測試使用者指定的集區配對。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-118">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="9c2f6-119">如果沒有這類測試使用者存在，命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-119">If no such test users exist, the command will fail.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="9c2f6-120">範例 2 會測試參與在集區 atl-cs-001.litwareinc.com 上應用程式共用會議 Join Launcher 服務的能力。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-120">Example 2 tests the ability of the Join Launcher service to participate in an Application Sharing conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="9c2f6-121">請注意，此命令會測試本身; 的服務您不需要任何行動裝置才能執行此命令。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-121">Note that this command tests only the service itself; you do not need any mobile devices in order to run the command.</span></span>

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

<span data-ttu-id="9c2f6-122">範例 2 所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 來登入 Lync Server 2013 和再進行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-122">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct an Application Sharing conference.</span></span> <span data-ttu-id="9c2f6-123">若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立包含其名稱和密碼的使用者為 Pilar Ackerman 的 Windows PowerShell 命令列介面認證物件。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-123">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="9c2f6-124">(因為登入名稱中，litwareinc\\pilar，已包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-124">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="9c2f6-125">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-125">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="9c2f6-126">在手中的認證物件，第三個命令會決定這些兩個使用者可以登入 Lync Server 2013，並先進行應用程式共用會議。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-126">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct an Application Sharing conference.</span></span> <span data-ttu-id="9c2f6-127">若要執行這項工作， **Test-csasconference** cmdlet 呼叫時，以及下列參數： TargetFqdn (之登錄器集區 FQDN);SenderSipAddress （第一個測試使用者的 SIP 位址）;與 SenderCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;並與 ReceiverCredential （Windows PowerShell 物件包含其他測試使用者的認證）。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-127">To carry out this task, the **Test-CsASConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9c2f6-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="9c2f6-128">Determining success or failure</span></span>

<span data-ttu-id="9c2f6-129">如果正確設定應用程式共用，您會收到類似，具有標示為 Result 屬性的輸出**成功：**</span><span class="sxs-lookup"><span data-stu-id="9c2f6-129">If application sharing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9c2f6-130">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9c2f6-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9c2f6-131">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="9c2f6-131">Result : Success</span></span>

<span data-ttu-id="9c2f6-132">延遲： 00:00:01</span><span class="sxs-lookup"><span data-stu-id="9c2f6-132">Latency : 00:00:01</span></span>

<span data-ttu-id="9c2f6-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9c2f6-133">Error Message :</span></span>

<span data-ttu-id="9c2f6-134">診斷：</span><span class="sxs-lookup"><span data-stu-id="9c2f6-134">Diagnosis :</span></span>

<span data-ttu-id="9c2f6-135">如果指定的使用者無法共用應用程式，結果會顯示為失敗，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="9c2f6-135">If the specified users can't share applications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9c2f6-136">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9c2f6-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9c2f6-137">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="9c2f6-137">Result : Failure</span></span>

<span data-ttu-id="9c2f6-138">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9c2f6-138">Latency : 00:00:00</span></span>

<span data-ttu-id="9c2f6-139">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="9c2f6-139">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="9c2f6-140">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="9c2f6-140">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="9c2f6-141">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="9c2f6-141">established connection failed because connected host has</span></span>

<span data-ttu-id="9c2f6-142">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="9c2f6-142">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9c2f6-143">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="9c2f6-143">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="9c2f6-144">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="9c2f6-144">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="9c2f6-145">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="9c2f6-145">time, or established connection failed because connected host</span></span>

<span data-ttu-id="9c2f6-146">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="9c2f6-146">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9c2f6-147">診斷：</span><span class="sxs-lookup"><span data-stu-id="9c2f6-147">Diagnosis :</span></span>

<span data-ttu-id="9c2f6-148">例如，先前的輸出包含 「 連線的對象並未正確回應 「 附註這通常表示 Edge Server 的問題。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-148">For example, the previous output includes the note “the connected party did not properly respond” That typically indicates a problem with the Edge Server.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9c2f6-149">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="9c2f6-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="9c2f6-150">以下是一些常見的原因為何**Test-csasconference**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="9c2f6-150">Here are some common reasons why **Test-CsASConference** might fail:</span></span>

  - <span data-ttu-id="9c2f6-151">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-151">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9c2f6-152">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-152">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9c2f6-153">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-153">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9c2f6-154">如果測試使用者已指派防止使用應用程式共用會議原則，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-154">This command will fail if the test users were assigned a conferencing policy that prevents them from using application sharing.</span></span>

  - <span data-ttu-id="9c2f6-155">如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9c2f6-155">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c2f6-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9c2f6-156">See Also</span></span>


[<span data-ttu-id="9c2f6-157">Get-csconferencingpolicy</span><span class="sxs-lookup"><span data-stu-id="9c2f6-157">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[<span data-ttu-id="9c2f6-158">Test-csdataconference</span><span class="sxs-lookup"><span data-stu-id="9c2f6-158">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

