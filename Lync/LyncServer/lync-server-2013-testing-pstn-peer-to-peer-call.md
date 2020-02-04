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
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a><span data-ttu-id="267ef-102">在 Lync Server 2013 中測試 PSTN 對等通話</span><span class="sxs-lookup"><span data-stu-id="267ef-102">Testing PSTN peer to peer call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="267ef-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="267ef-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="267ef-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="267ef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="267ef-105">日常</span><span class="sxs-lookup"><span data-stu-id="267ef-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="267ef-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="267ef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="267ef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="267ef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="267ef-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="267ef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="267ef-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="267ef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="267ef-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsPstnPeerToPeerCall Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="267ef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPstnPeerToPeerCall cmdlet.</span></span> <span data-ttu-id="267ef-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="267ef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="267ef-112">說明</span><span class="sxs-lookup"><span data-stu-id="267ef-112">Description</span></span>

<span data-ttu-id="267ef-113">CsPstnPeerToPeerCall Cmdlet 會驗證一組使用者必須在公用交換電話網絡（PSTN）閘道上進行對等呼叫的能力。</span><span class="sxs-lookup"><span data-stu-id="267ef-113">The Test-CsPstnPeerToPeerCall cmdlet verifies the ability a pair of users has to conduct a peer-to-peer call over the public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="267ef-114">當您呼叫 Test CsPstnPeerToPeerCall 時，此 Cmdlet 會先嘗試將兩個測試使用者登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="267ef-114">When you call Test-CsPstnPeerToPeerCall, the cmdlet will first attempt to log on two test users to Lync Server.</span></span> <span data-ttu-id="267ef-115">假設記錄成功，則 Cmdlet 會讓使用者1嘗試使用 PSTN 閘道呼叫 user 2。</span><span class="sxs-lookup"><span data-stu-id="267ef-115">Assuming that the logons succeed, the cmdlet will then have user 1 attempt to call user 2 over the PSTN gateway.</span></span> <span data-ttu-id="267ef-116">CsPstnPeerToPeerCall 將會使用撥號計畫、語音原則以及指派給測試使用者的其他原則和設定設定來撥打此通話。</span><span class="sxs-lookup"><span data-stu-id="267ef-116">Test-CsPstnPeerToPeerCall will make this call using the dial plan, voice policy, and other policy and configuration settings assigned to the test user.</span></span> <span data-ttu-id="267ef-117">如果測試是以規劃方式進行，此 Cmdlet 會驗證使用者2是否能夠接聽通話，然後從系統登出測試帳戶。</span><span class="sxs-lookup"><span data-stu-id="267ef-117">If the test goes as planned, the cmdlet will verify that user 2 was able to answer the call, and then log off both test accounts from the system.</span></span>

<span data-ttu-id="267ef-118">CsPstnPeerToPeerCall 會撥打實際的電話，其中一個會驗證是否可以建立連線，也可透過網路傳送 DTMF 代碼來判斷媒體是否可透過連線傳送。</span><span class="sxs-lookup"><span data-stu-id="267ef-118">Test-CsPstnPeerToPeerCall makes an actual phone call, one that verifies that a connection can be made and that also transmits DTMF codes over the network to determine whether media can be sent over the connection.</span></span> <span data-ttu-id="267ef-119">呼叫是由 Cmdlet 本身所接聽，且不需要手動終止通話。</span><span class="sxs-lookup"><span data-stu-id="267ef-119">The call is answered by the cmdlet itself, and no manual termination of the call is necessary.</span></span> <span data-ttu-id="267ef-120">（也就是說，沒有人必須回答，然後掛斷來電的電話。）</span><span class="sxs-lookup"><span data-stu-id="267ef-120">(That is, no one must answer and then hang up the phone that was called.)</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="267ef-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="267ef-121">Running the test</span></span>

<span data-ttu-id="267ef-122">CsPstnPeerToPeerCall Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="267ef-122">The Test-CsPstnPeerToPeerCall cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="267ef-123">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="267ef-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="267ef-124">例如：</span><span class="sxs-lookup"><span data-stu-id="267ef-124">For example:</span></span>

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

<span data-ttu-id="267ef-125">若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="267ef-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="267ef-126">當您呼叫 Test CsPstnPeerToPeerCall 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="267ef-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPstnPeerToPeerCall:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="267ef-127">如需詳細資訊，請參閱[Test CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="267ef-127">For more information, see the Help documentation for the [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="267ef-128">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="267ef-128">Determining success or failure</span></span>

<span data-ttu-id="267ef-129">如果指定的使用者可以完成對等呼叫，您將會收到與此類似的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="267ef-129">If the specified users can complete a peer-to-peer call, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="267ef-130">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="267ef-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="267ef-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="267ef-131">Result : Success</span></span>

<span data-ttu-id="267ef-132">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="267ef-132">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="267ef-133">出錯</span><span class="sxs-lookup"><span data-stu-id="267ef-133">Error :</span></span>

<span data-ttu-id="267ef-134">自檢</span><span class="sxs-lookup"><span data-stu-id="267ef-134">Diagnosis :</span></span>

<span data-ttu-id="267ef-135">如果指定的使用者無法完成對等呼叫，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="267ef-135">If the specified users can't complete a peer-to-peer call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="267ef-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="267ef-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="267ef-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="267ef-137">Result : Failure</span></span>

<span data-ttu-id="267ef-138">延遲：00:00:0182361</span><span class="sxs-lookup"><span data-stu-id="267ef-138">Latency : 00:00:0182361</span></span>

<span data-ttu-id="267ef-139">錯誤：403，已禁止</span><span class="sxs-lookup"><span data-stu-id="267ef-139">Error : 403, Forbidden</span></span>

<span data-ttu-id="267ef-140">診斷： ErrorCode = 12001，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="267ef-140">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="267ef-141">原因 = 使用者原則不包含電話路線使用量</span><span class="sxs-lookup"><span data-stu-id="267ef-141">Reason=User Policy does not contain phone route usage</span></span>

<span data-ttu-id="267ef-142">由於指派給至少其中一個指定使用者的語音原則不包含電話使用方式，因此先前的輸出指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="267ef-142">The previous output states that the test failed because the voice policy assigned to at least one of the specified users does not include a phone usage.</span></span> <span data-ttu-id="267ef-143">（電話使用方式會將語音原則與語音路線聯繫在一起。</span><span class="sxs-lookup"><span data-stu-id="267ef-143">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="267ef-144">如果沒有語音原則及相對應的語音路線，您就無法透過 PSTN 撥打通話。</span><span class="sxs-lookup"><span data-stu-id="267ef-144">Without both a voice policy and a corresponding voice route, you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="267ef-145">如果測試 CsPstnPeerToPeerCall 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="267ef-145">If Test-CsPstnPeerToPeerCall fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="267ef-146">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPstnPeerToPeerCall 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="267ef-146">When the Verbose parameter is included, Test-CsPstnPeerToPeerCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="267ef-147">例如，此輸出表示網路問題妨礙與 PSTN 連線：</span><span class="sxs-lookup"><span data-stu-id="267ef-147">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="267ef-148">建立音訊視頻通話至「sip： + 12065551219@litwareinc .com; 使用者 = 電話」。</span><span class="sxs-lookup"><span data-stu-id="267ef-148">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="267ef-149">從網路接收到 [404 （找不到）回應] 的例外狀況，且操作失敗。</span><span class="sxs-lookup"><span data-stu-id="267ef-149">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="267ef-150">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="267ef-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="267ef-151">以下是測試 CsPstnPeerToPeerCall 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="267ef-151">Here are some common reasons why Test-CsPstnPeerToPeerCall might fail:</span></span>

  - <span data-ttu-id="267ef-152">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="267ef-152">You specified a user account that is not valid.</span></span> <span data-ttu-id="267ef-153">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="267ef-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="267ef-154">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="267ef-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="267ef-155">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="267ef-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="267ef-156">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="267ef-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="267ef-157">指派給指定使用者的語音原則沒有有效的 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="267ef-157">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="267ef-158">您可以使用類似以下的命令來判斷指派給使用者的語音原則：</span><span class="sxs-lookup"><span data-stu-id="267ef-158">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="267ef-159">然後，您可以使用類似下列的命令來判斷指派給該原則的 PSTN 使用方式（如果有的話），這會檢索每個使用者語音原則 RedmondVoicePolicy 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="267ef-159">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

