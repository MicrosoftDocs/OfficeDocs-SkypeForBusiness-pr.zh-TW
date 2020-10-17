---
title: Lync Server 2013：測試 PSTN 對等通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33aa0447c90ea9c76a1956cb817f0e61ce0d626e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504040"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="7f4c8-102">在 Lync Server 2013 中測試 PSTN 對等通話</span><span class="sxs-lookup"><span data-stu-id="7f4c8-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f4c8-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7f4c8-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f4c8-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="7f4c8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7f4c8-105">每日</span><span class="sxs-lookup"><span data-stu-id="7f4c8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f4c8-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="7f4c8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7f4c8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f4c8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f4c8-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="7f4c8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7f4c8-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7f4c8-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsPstnPeerToPeerCall Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="7f4c8-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7f4c8-112">描述</span><span class="sxs-lookup"><span data-stu-id="7f4c8-112">Description</span></span>

<span data-ttu-id="7f4c8-113">Test-CsPstnPeerToPeerCall Cmdlet 會驗證一組使用者必須透過公用交換電話網路 (PSTN) 閘道進行對等呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="7f4c8-114">當您呼叫 Test-CsPstnPeerToPeerCall 時，Cmdlet 會先嘗試將兩個測試使用者登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="7f4c8-115">假設登入成功，則 Cmdlet 會讓使用者1嘗試透過 PSTN 閘道呼叫使用者2。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="7f4c8-116">Test-CsPstnPeerToPeerCall 會使用撥號對應表、語音原則，以及指派給測試使用者的其他原則和設定設定進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="7f4c8-117">如果測試為已計畫，指令程式會驗證使用者2是否可以接聽通話，然後從系統中登出這兩個測試帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="7f4c8-118">Test-CsPstnPeerToPeerCall 會撥打實際電話，一部驗證可以進行連線，也可透過網路傳輸 DTMF 碼，以判斷媒體是否可以透過連線傳送。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="7f4c8-119">此呼叫是由 Cmdlet 本身所接聽，且不需要手動結束通話。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="7f4c8-120"> (也就是說，任何人都必須回答，然後掛斷呼叫的電話。 ) </span><span class="sxs-lookup"><span data-stu-id="7f4c8-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7f4c8-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="7f4c8-121">Running the test</span></span>

<span data-ttu-id="7f4c8-122">您可以使用一對預先設定的測試帳戶來執行 Test-CsPstnPeerToPeerCall Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="7f4c8-123">若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="7f4c8-124">例如：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="7f4c8-125">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7f4c8-126">當您呼叫 Test-CsPstnPeerToPeerCall 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="7f4c8-127">如需詳細資訊，請參閱 [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7f4c8-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="7f4c8-128">Determining success or failure</span></span>

<span data-ttu-id="7f4c8-129">如果指定的使用者可以完成對等通話，您會收到類似以下的輸出，其 Result 屬性標示為「 **成功」：**</span><span class="sxs-lookup"><span data-stu-id="7f4c8-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7f4c8-130">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7f4c8-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7f4c8-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="7f4c8-131">Result : Success</span></span>

<span data-ttu-id="7f4c8-132">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="7f4c8-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="7f4c8-133">錯誤：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-133">Error :</span></span>

<span data-ttu-id="7f4c8-134">診斷：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-134">Diagnosis :</span></span>

<span data-ttu-id="7f4c8-135">如果指定的使用者無法完成對等通話，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7f4c8-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7f4c8-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7f4c8-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="7f4c8-137">Result : Failure</span></span>

<span data-ttu-id="7f4c8-138">延遲：00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="7f4c8-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="7f4c8-139">錯誤：403，已禁止</span><span class="sxs-lookup"><span data-stu-id="7f4c8-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="7f4c8-140">診斷： ErrorCode = 12001、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="7f4c8-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="7f4c8-141">原因 = 使用者原則不含電話路由使用方式</span><span class="sxs-lookup"><span data-stu-id="7f4c8-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="7f4c8-142">先前的輸出表明測試失敗，因為指派給至少一個指定使用者的語音原則不包含電話使用狀況。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="7f4c8-143"> (電話使用方式會將語音原則與語音路由進行結合。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="7f4c8-144">若未使用語音原則和對應的語音路由，則無法透過 PSTN 進行通話。 ) </span><span class="sxs-lookup"><span data-stu-id="7f4c8-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="7f4c8-145">如果 Test-CsPstnPeerToPeerCall 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="7f4c8-146">包含 Verbose 參數時，Test-CsPstnPeerToPeerCall 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="7f4c8-147">例如，此輸出表示網路問題阻礙使用 PSTN 進行連線：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="7f4c8-148">建立音訊影片通話至 ' sip： + 12065551219@litwareinc .com; user = phone '。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="7f4c8-149">無法找到例外狀況 ' A 404 () 回應是從網路接收，而且操作失敗。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7f4c8-150">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="7f4c8-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="7f4c8-151">以下是一些 Test-CsPstnPeerToPeerCall 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="7f4c8-152">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="7f4c8-153">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="7f4c8-154">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="7f4c8-155">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="7f4c8-156">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="7f4c8-157">指派給指定使用者的語音原則沒有有效的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="7f4c8-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="7f4c8-158">您可以使用類似下列的命令，判斷指派給使用者的語音原則：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="7f4c8-159">然後，您可以使用類似下列的命令，在指派給該原則的任何) 中判斷 PSTN 使用方式 (，該命令會檢索每一使用者語音原則 RedmondVoicePolicy 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="7f4c8-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

