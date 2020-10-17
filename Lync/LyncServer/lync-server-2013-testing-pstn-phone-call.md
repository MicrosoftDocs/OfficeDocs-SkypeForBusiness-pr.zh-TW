---
title: Lync Server 2013：測試 PSTN 通話
description: Lync Server 2013：測試 PSTN 通話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b42ea6dd46145961a34386d704f8f44e9b7909ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547399"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="b9375-103">在 Lync Server 2013 中測試 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="b9375-103">Testing PSTN phone call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9375-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="b9375-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9375-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="b9375-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b9375-106">每日</span><span class="sxs-lookup"><span data-stu-id="b9375-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9375-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="b9375-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b9375-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9375-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9375-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="b9375-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b9375-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b9375-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b9375-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsRegistration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b9375-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="b9375-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b9375-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b9375-113">描述</span><span class="sxs-lookup"><span data-stu-id="b9375-113">Description</span></span>

<span data-ttu-id="b9375-114">Test-CsPstnOutboundCall Cmdlet 會測試使用者撥打位於 PSTN 之電話號碼的能力。</span><span class="sxs-lookup"><span data-stu-id="b9375-114">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="b9375-115">當您執行 Test-CsPstnOutboundCall 時，指令 Cmdlet 會先嘗試將測試使用者記錄到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="b9375-115">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="b9375-116">如果登入成功，則 Cmdlet 會嘗試撥打跨越 PSTN 閘道的電話。</span><span class="sxs-lookup"><span data-stu-id="b9375-116">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="b9375-117">這會使用撥號對應表、語音原則，以及指派給測試帳戶的其他原則和設定進行通話。</span><span class="sxs-lookup"><span data-stu-id="b9375-117">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="b9375-118">當接聽來電時，Cmdlet 會透過網路傳送雙音多重頻率 (DTMF) 碼，以驗證媒體的連線能力。</span><span class="sxs-lookup"><span data-stu-id="b9375-118">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="b9375-119">進行測試時，Test-CsPstnOutboundCall 會撥打實際的電話：目標電話會振鈴，必須回答才能成功測試。</span><span class="sxs-lookup"><span data-stu-id="b9375-119">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="b9375-120">此通話也必須由系統管理員手動結束。</span><span class="sxs-lookup"><span data-stu-id="b9375-120">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b9375-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="b9375-121">Running the test</span></span>

<span data-ttu-id="b9375-122">您可以使用預先設定的測試帳戶執行 Test-CsPstnOutboundCall Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9375-122">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="b9375-123">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN，以及呼叫 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b9375-123">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="b9375-124">例如：</span><span class="sxs-lookup"><span data-stu-id="b9375-124">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="b9375-125">若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="b9375-125">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="b9375-126">接著，當您呼叫 Test-CsPstnOutboundCall 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="b9375-126">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="b9375-127">如需詳細資訊，請參閱 [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="b9375-127">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b9375-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="b9375-128">Determining success or failure</span></span>

<span data-ttu-id="b9375-129">如果指定的使用者可以撥打電話，且接聽來電，您會收到類似以下的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="b9375-129">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b9375-130">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9375-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b9375-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="b9375-131">Result : Success</span></span>

<span data-ttu-id="b9375-132">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="b9375-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="b9375-133">錯誤：</span><span class="sxs-lookup"><span data-stu-id="b9375-133">Error :</span></span>

<span data-ttu-id="b9375-134">診斷：</span><span class="sxs-lookup"><span data-stu-id="b9375-134">Diagnosis :</span></span>

<span data-ttu-id="b9375-135">如果指定的使用者無法撥打來電或來電未接聽，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="b9375-135">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b9375-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b9375-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b9375-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="b9375-137">Result : Failure</span></span>

<span data-ttu-id="b9375-138">延遲：00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="b9375-138">Latency : 00:00:0987365</span></span>

<span data-ttu-id="b9375-139">錯誤：403，已禁止</span><span class="sxs-lookup"><span data-stu-id="b9375-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="b9375-140">診斷： ErrorCode = 12001，Source = atl-ws-01 = cs，Reason = User</span><span class="sxs-lookup"><span data-stu-id="b9375-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="b9375-141">原則不含電話路由使用方式</span><span class="sxs-lookup"><span data-stu-id="b9375-141">Policy does not contain phone route usage</span></span>

<span data-ttu-id="b9375-142">先前的輸出規定測試失敗，因為指派給指定使用者的語音原則並未包含電話使用狀況。</span><span class="sxs-lookup"><span data-stu-id="b9375-142">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="b9375-143"> (電話使用方式會將語音原則與語音路由進行結合。</span><span class="sxs-lookup"><span data-stu-id="b9375-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="b9375-144">若未使用語音原則和對應的語音路由，則無法透過 PSTN 撥打通話。 ) </span><span class="sxs-lookup"><span data-stu-id="b9375-144">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="b9375-145">如果 Test-CsPstnOutboundCall 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="b9375-145">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="b9375-146">包含 Verbose 參數時，Test-CsPstnOutboundCall 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="b9375-146">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="b9375-147">例如，此輸出表示網路問題阻礙使用 PSTN 進行連線：</span><span class="sxs-lookup"><span data-stu-id="b9375-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="b9375-148">建立音訊影片通話至 ' sip： + 12065551219@litwareinc .com; user = phone '。</span><span class="sxs-lookup"><span data-stu-id="b9375-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="b9375-149">無法找到例外狀況 ' A 404 () 回應是從網路接收，而且操作失敗。</span><span class="sxs-lookup"><span data-stu-id="b9375-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b9375-150">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="b9375-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="b9375-151">以下是一些 Test-CsPstnOutboundCall 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="b9375-151">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="b9375-152">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="b9375-152">You specified an invalid user account.</span></span> <span data-ttu-id="b9375-153">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="b9375-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="b9375-154">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b9375-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="b9375-155">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="b9375-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="b9375-156">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="b9375-156">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="b9375-157">指派給指定使用者的語音原則沒有有效的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="b9375-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="b9375-158">您可以使用類似下列的命令，判斷指派給使用者的語音原則：</span><span class="sxs-lookup"><span data-stu-id="b9375-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="b9375-159">然後，您可以使用類似下列的命令，在指派給該原則的任何) 中判斷 PSTN 使用方式 (，該命令會檢索每一使用者語音原則 RedmondVoicePolicy 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="b9375-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

