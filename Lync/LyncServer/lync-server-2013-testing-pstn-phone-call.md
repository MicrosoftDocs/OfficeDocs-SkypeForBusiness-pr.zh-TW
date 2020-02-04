---
title: Lync Server 2013：測試 PSTN 通話
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
ms.openlocfilehash: 8095b4b0bb6aa4e6920d291c3fde3885ae6bfb03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a><span data-ttu-id="41b0f-102">在 Lync Server 2013 中測試 PSTN 電話通話</span><span class="sxs-lookup"><span data-stu-id="41b0f-102">Testing PSTN phone call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41b0f-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="41b0f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41b0f-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="41b0f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="41b0f-105">日常</span><span class="sxs-lookup"><span data-stu-id="41b0f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41b0f-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="41b0f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="41b0f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41b0f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41b0f-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="41b0f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="41b0f-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="41b0f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="41b0f-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsRegistration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="41b0f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="41b0f-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="41b0f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="41b0f-112">說明</span><span class="sxs-lookup"><span data-stu-id="41b0f-112">Description</span></span>

<span data-ttu-id="41b0f-113">CsPstnOutboundCall Cmdlet 會測試使用者撥打電話給 PSTN 上電話號碼的功能。</span><span class="sxs-lookup"><span data-stu-id="41b0f-113">The Test-CsPstnOutboundCall cmdlet tests the ability of a user to make a call to a phone number located on the PSTN.</span></span> <span data-ttu-id="41b0f-114">當您執行 Test CsPstnOutboundCall 時，此 Cmdlet 會先嘗試將測試使用者記錄到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="41b0f-114">When you run Test-CsPstnOutboundCall, the cmdlet first attempts to log the test user on to Lync Server.</span></span> <span data-ttu-id="41b0f-115">如果登入成功，則 Cmdlet 會嘗試撥打 PSTN 閘道的電話撥打電話。</span><span class="sxs-lookup"><span data-stu-id="41b0f-115">If the logon succeeds, the cmdlet will then try to make a phone call across the PSTN gateway.</span></span> <span data-ttu-id="41b0f-116">這個電話將會使用撥號計畫、語音原則，以及指派給測試帳戶的其他原則和設定來撥打。</span><span class="sxs-lookup"><span data-stu-id="41b0f-116">This phone call will be made using the dial plan, voice policy, and other policies and settings assigned to the test account.</span></span> <span data-ttu-id="41b0f-117">接聽來電時，Cmdlet 會在網路上傳送雙音調多頻率（DTMF）碼，以驗證媒體連線性。</span><span class="sxs-lookup"><span data-stu-id="41b0f-117">When the call is answered, the cmdlet sends dual-tone multi-frequency (DTMF) codes over the network to verify media connectivity.</span></span>

<span data-ttu-id="41b0f-118">進行測試時，測試 CsPstnOutboundCall 將撥打實際電話： [目標電話] 會響鈴，而且必須接聽才能成功測試。</span><span class="sxs-lookup"><span data-stu-id="41b0f-118">When conducting its test, Test-CsPstnOutboundCall will make an actual phone call: the target phone will ring and must be answered for the test to succeed.</span></span> <span data-ttu-id="41b0f-119">系統管理員也必須手動結束此通話。</span><span class="sxs-lookup"><span data-stu-id="41b0f-119">This call must also be manually ended by the administrator.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="41b0f-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="41b0f-120">Running the test</span></span>

<span data-ttu-id="41b0f-121">CsPstnOutboundCall Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="41b0f-121">The Test-CsPstnOutboundCall cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="41b0f-122">若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池 FQDN，並呼叫 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="41b0f-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the PSTN phone number being called.</span></span> <span data-ttu-id="41b0f-123">例如：</span><span class="sxs-lookup"><span data-stu-id="41b0f-123">For example:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

<span data-ttu-id="41b0f-124">若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="41b0f-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="41b0f-125">當您呼叫 Test CsPstnOutboundCall 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="41b0f-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsPstnOutboundCall:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="41b0f-126">如需詳細資訊，請參閱[Test CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="41b0f-126">For more information, see the Help documentation for the [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="41b0f-127">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="41b0f-127">Determining success or failure</span></span>

<span data-ttu-id="41b0f-128">如果指定的使用者可以進行通話，而且接聽通話，您會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="41b0f-128">If the specified user can make the call, and if the call is answered, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="41b0f-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="41b0f-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="41b0f-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="41b0f-130">Result : Success</span></span>

<span data-ttu-id="41b0f-131">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="41b0f-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="41b0f-132">出錯</span><span class="sxs-lookup"><span data-stu-id="41b0f-132">Error :</span></span>

<span data-ttu-id="41b0f-133">自檢</span><span class="sxs-lookup"><span data-stu-id="41b0f-133">Diagnosis :</span></span>

<span data-ttu-id="41b0f-134">如果指定的使用者無法撥打電話或通話沒有回應，則結果會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="41b0f-134">If the specified user can't make the call or if the call is not answered, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="41b0f-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="41b0f-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="41b0f-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="41b0f-136">Result : Failure</span></span>

<span data-ttu-id="41b0f-137">延遲：00:00:0987365</span><span class="sxs-lookup"><span data-stu-id="41b0f-137">Latency : 00:00:0987365</span></span>

<span data-ttu-id="41b0f-138">錯誤：403，已禁止</span><span class="sxs-lookup"><span data-stu-id="41b0f-138">Error : 403, Forbidden</span></span>

<span data-ttu-id="41b0f-139">診斷： ErrorCode = 12001，Source = atl-cs-001. litwareinc，原因 = User</span><span class="sxs-lookup"><span data-stu-id="41b0f-139">Diagnosis : ErrorCode=12001,Source=atl-cs-001.litwareinc.com,Reason=User</span></span>

<span data-ttu-id="41b0f-140">原則不包含電話路線使用量</span><span class="sxs-lookup"><span data-stu-id="41b0f-140">Policy does not contain phone route usage</span></span>

<span data-ttu-id="41b0f-141">由於指派給指定使用者的語音原則不包含電話使用方式，因此先前的輸出指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="41b0f-141">The previous output states that the test failed because the voice policy assigned to the specified user does not include a phone usage.</span></span> <span data-ttu-id="41b0f-142">（電話使用方式會將語音原則與語音路線聯繫在一起。</span><span class="sxs-lookup"><span data-stu-id="41b0f-142">(Phone usages tie voice policies to voice routes.</span></span> <span data-ttu-id="41b0f-143">若沒有語音原則和相對應的語音路線，就無法透過 PSTN 撥打通話。</span><span class="sxs-lookup"><span data-stu-id="41b0f-143">Without both a voice policy and a corresponding voice route you can't make calls over the PSTN.)</span></span>

<span data-ttu-id="41b0f-144">如果測試 CsPstnOutboundCall 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="41b0f-144">If Test-CsPstnOutboundCall fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

<span data-ttu-id="41b0f-145">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPstnOutboundCall 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="41b0f-145">When the Verbose parameter is included, Test-CsPstnOutboundCall will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="41b0f-146">例如，此輸出表示網路問題妨礙與 PSTN 連線：</span><span class="sxs-lookup"><span data-stu-id="41b0f-146">For example, this output indicates that network problems are preventing a connection with the PSTN:</span></span>

<span data-ttu-id="41b0f-147">建立音訊視頻通話至「sip： + 12065551219@litwareinc .com; 使用者 = 電話」。</span><span class="sxs-lookup"><span data-stu-id="41b0f-147">Establishing Audio Video call to 'sip:+12065551219@litwareinc.com;user=phone'.</span></span>

<span data-ttu-id="41b0f-148">從網路接收到 [404 （找不到）回應] 的例外狀況，且操作失敗。</span><span class="sxs-lookup"><span data-stu-id="41b0f-148">An exception 'A 404 (Not Found) response was received from the network and the operation failed.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="41b0f-149">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="41b0f-149">Reasons why the test might have failed</span></span>

<span data-ttu-id="41b0f-150">以下是測試 CsPstnOutboundCall 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="41b0f-150">Here are some common reasons why Test-CsPstnOutboundCall might fail:</span></span>

  - <span data-ttu-id="41b0f-151">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="41b0f-151">You specified an invalid user account.</span></span> <span data-ttu-id="41b0f-152">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="41b0f-152">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="41b0f-153">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="41b0f-153">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="41b0f-154">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="41b0f-154">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="41b0f-155">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="41b0f-155">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="41b0f-156">指派給指定使用者的語音原則沒有有效的 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="41b0f-156">The voice policy assigned to the specified user does not have a valid PSTN usage.</span></span> <span data-ttu-id="41b0f-157">您可以使用類似以下的命令來判斷指派給使用者的語音原則：</span><span class="sxs-lookup"><span data-stu-id="41b0f-157">You can determine the voice policy that is assigned to a user by using a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    <span data-ttu-id="41b0f-158">然後，您可以使用類似下列的命令來判斷指派給該原則的 PSTN 使用方式（如果有的話），這會檢索每個使用者語音原則 RedmondVoicePolicy 的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="41b0f-158">And then you can determine the PSTN usages (if any) that are assigned to that policy by using a command similar to the following, which retrieves information about the per-user voice policy RedmondVoicePolicy:</span></span>
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

