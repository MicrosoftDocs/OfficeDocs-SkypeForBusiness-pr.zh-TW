---
title: Lync Server 2013：測試使用群組延伸的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="9a2c2-102">測試在 Lync Server 2013 中使用群組延伸的能力</span><span class="sxs-lookup"><span data-stu-id="9a2c2-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a2c2-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="9a2c2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a2c2-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="9a2c2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9a2c2-105">日常</span><span class="sxs-lookup"><span data-stu-id="9a2c2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c2-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="9a2c2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9a2c2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a2c2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c2-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="9a2c2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9a2c2-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9a2c2-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsGroupExpansion Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="9a2c2-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9a2c2-112">描述</span><span class="sxs-lookup"><span data-stu-id="9a2c2-112">Description</span></span>

<span data-ttu-id="9a2c2-113">CsGroupExpansion Cmdlet 可讓您判斷群組延伸在貴組織內是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="9a2c2-114">啟用群組展開時，使用者會將通訊群組設定為連絡人。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="9a2c2-115">這表示這些使用者只要將訊息定至群組，而不是群組成員，就可以傳送相同的立即訊息給所有的群組成員。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="9a2c2-116">[群組延伸] 可讓您快速且輕鬆地查看所有群組成員及其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="9a2c2-117">使用 Test CsGroupExpansion Cmdlet，您可以使用群組的電子郵件地址來指定 Active Directory 通訊群組。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="9a2c2-118">CsGroupExpansion 然後使用群組延伸來取得群組成員資格，並將檢索到的清單與您所提供的群組電子郵件地址的成員資格進行比較。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="9a2c2-119">如果兩個清單相符，則群組延伸作業正常運作。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="9a2c2-120">請注意，您可以使用兩種方式來測試群組延伸：測試服務本身，或測試相關的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="9a2c2-121">如需詳細資訊，請參閱[Test CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9a2c2-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="9a2c2-122">Running the test</span></span>

<span data-ttu-id="9a2c2-123">CsGroupExpansion Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="9a2c2-124">若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池 FQDN，以及有效通訊群組的電子郵件地址即可。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="9a2c2-125">例如：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="9a2c2-126">若要使用實際的使用者帳戶執行此檢查，您必須先建立一個包含帳戶名稱和密碼的 Lync Server 認證物件。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="9a2c2-127">然後，您必須在系統呼叫 Test-CsGroupExpansion 時包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="9a2c2-128">如需詳細資訊，請參閱[Test CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9a2c2-129">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="9a2c2-129">Determining success or failure</span></span>

<span data-ttu-id="9a2c2-130">如果指定的使用者可以使用群組延伸，您會收到類似以下的輸出，並將 Result 屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="9a2c2-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="9a2c2-131">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="9a2c2-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="9a2c2-132">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9a2c2-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9a2c2-133">結果：成功</span><span class="sxs-lookup"><span data-stu-id="9a2c2-133">Result : Success</span></span>

<span data-ttu-id="9a2c2-134">延隔時間：00：00：01.1234976</span><span class="sxs-lookup"><span data-stu-id="9a2c2-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="9a2c2-135">出錯</span><span class="sxs-lookup"><span data-stu-id="9a2c2-135">Error :</span></span>

<span data-ttu-id="9a2c2-136">自檢</span><span class="sxs-lookup"><span data-stu-id="9a2c2-136">Diagnosis :</span></span>

<span data-ttu-id="9a2c2-137">如果指定的使用者無法使用群組延伸，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9a2c2-138">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="9a2c2-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="9a2c2-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9a2c2-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9a2c2-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="9a2c2-140">Result : Failure</span></span>

<span data-ttu-id="9a2c2-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="9a2c2-141">Latency : 00:00:00</span></span>

<span data-ttu-id="9a2c2-142">出錯</span><span class="sxs-lookup"><span data-stu-id="9a2c2-142">Error :</span></span>

<span data-ttu-id="9a2c2-143">自檢</span><span class="sxs-lookup"><span data-stu-id="9a2c2-143">Diagnosis :</span></span>

<span data-ttu-id="9a2c2-144">測試-CsGroupExpansion：端點無法註冊。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="9a2c2-145">請參閱 ErrorCode，瞭解特定原因。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="9a2c2-146">先前的輸出指出測試失敗，因為指定的使用者無法使用 Lync Server 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="9a2c2-147">如果測試帳戶不存在，或沒有為 Lync Server 啟用，則通常會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="9a2c2-148">您可以透過執行類似下列的命令，確認帳戶存在，並判斷是否已啟用 nm 版 ocs-14-3 的帳戶：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="9a2c2-149">如果測試 CsGroupExpansion 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="9a2c2-150">在包含詳細參數的情況下，CsGroupExpansion 會傳回其在檢查指定使用者登入 Lync Server 的能力時所嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="9a2c2-151">例如，此輸出表示找不到指定的通訊群組：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="9a2c2-152">正在嘗試取得 web 票證。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-152">Trying to get web ticket.</span></span>

<span data-ttu-id="9a2c2-153">Web 服務 url：https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="9a2c2-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="9a2c2-154">使用 NTLM/Kerb auth。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="9a2c2-155">GetWebTicketActivity 已完成。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="9a2c2-156">「VerifyDistributionList」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="9a2c2-157">DLX Web Services 回應狀態為： NotFound。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="9a2c2-158">"VerifyDistributionList" 活動在 "0.2597923" 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9a2c2-159">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="9a2c2-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="9a2c2-160">以下是測試 CsGroupExpansion 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="9a2c2-161">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-161">You specified an invalid user account.</span></span> <span data-ttu-id="9a2c2-162">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="9a2c2-163">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="9a2c2-164">若要確認使用者帳戶已啟用 Lync Server，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="9a2c2-165">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="9a2c2-166">[群組延伸] 可能已停用。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-166">Group expansion might be disabled.</span></span> <span data-ttu-id="9a2c2-167">您可以關閉群組延伸。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="9a2c2-168">如果群組延伸已停用，則 CsGroupExpansion Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9a2c2-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="9a2c2-169">若要判斷是否已啟用群組延伸，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="9a2c2-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

