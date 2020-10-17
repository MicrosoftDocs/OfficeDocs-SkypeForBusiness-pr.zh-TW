---
title: Lync Server 2013：測試整合連絡人存放區存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5552c03ac18ddd373385674da03d872ce89eb585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503900"
---
# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="eb6e0-102">在 Lync Server 2013 中測試整合連絡人存放區存取權</span><span class="sxs-lookup"><span data-stu-id="eb6e0-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb6e0-103">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="eb6e0-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb6e0-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="eb6e0-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="eb6e0-105">每日</span><span class="sxs-lookup"><span data-stu-id="eb6e0-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb6e0-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="eb6e0-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="eb6e0-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb6e0-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb6e0-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="eb6e0-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="eb6e0-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="eb6e0-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsUnifiedContactStore</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="eb6e0-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="eb6e0-112">描述</span><span class="sxs-lookup"><span data-stu-id="eb6e0-112">Description</span></span>

<span data-ttu-id="eb6e0-113">Lync Server 2013 中引入的整合連絡人存放區可讓管理員選擇將使用者的連絡人儲存在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="eb6e0-114">這樣一來，除了 Lync 2013 之外，使用者還是可以存取 Outlook Web Access 中的同一組連絡人。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="eb6e0-115"> (或者，您可以繼續在 Lync Server 中儲存連絡人。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="eb6e0-116">在此情況下，使用者必須維護兩組不同的連絡人：一個用於 Outlook 和 Outlook Web Access，另一個則用於 Lync 2013。 ) </span><span class="sxs-lookup"><span data-stu-id="eb6e0-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="eb6e0-117">您可以執行 **Test-CsUnifiedContactStore** Cmdlet，判斷使用者的連絡人是否已移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="eb6e0-118">**Test-CsUnifiedContactStore** Cmdlet 會使用指定的使用者帳戶，並聯機至整合連絡人存放區，並嘗試為使用者取回連絡人。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="eb6e0-119">若未取得任何連絡人，命令會一起失敗，並顯示 [使用者未收到任何連絡人] 的訊息。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="eb6e0-120">確認使用者已存在連絡人。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="eb6e0-121">請注意，如果使用者已成功遷移至整合連絡人存放區，但其連絡人清單中沒有連絡人，則 **Test-CsUnifiedContactStore** Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="eb6e0-122">指定的使用者至少必須有一個連絡人， **Test-CsUnifiedContactStore** Cmdlet 才能成功完成。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="eb6e0-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="eb6e0-123">Running the test</span></span>

<span data-ttu-id="eb6e0-124">下列範例所示的命令會決定使用者 litwareinc kenmyer 的連絡人是否 \\ 可以在整合連絡人存放區中找到。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="eb6e0-125">為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 為使用者 litwareinc Kenmyer 建立 Windows PowerShell 命令列介面認證物件 \\ 。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="eb6e0-126">請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確定 **Test-CsUnifiedContactStore** 指令程式可以執行其檢查。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="eb6e0-127">範例中的第二個命令會使用提供的認證物件 ($x) 和使用者 litwareinc kenmyer 的 SIP 位址， \\ 以判斷是否可以在整合連絡人存放區中找到其連絡人。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="eb6e0-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="eb6e0-128">Determining success or failure</span></span>

<span data-ttu-id="eb6e0-129">如果已正確設定連絡人存放區的存取權，您會收到類似下列的輸出，並將 Result 屬性標示為「 **成功」：**</span><span class="sxs-lookup"><span data-stu-id="eb6e0-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="eb6e0-130">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb6e0-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eb6e0-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="eb6e0-131">Result : Success</span></span>

<span data-ttu-id="eb6e0-132">延遲：00：00：14.9862716</span><span class="sxs-lookup"><span data-stu-id="eb6e0-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="eb6e0-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-133">Error Message :</span></span>

<span data-ttu-id="eb6e0-134">診斷：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-134">Diagnosis :</span></span>

<span data-ttu-id="eb6e0-135">如果未正確設定連絡人存放區的存取權，結果將會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 內容中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="eb6e0-136">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="eb6e0-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="eb6e0-137">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-137">domain name (FQDN).</span></span> <span data-ttu-id="eb6e0-138">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-138">Using default Registrar port number.</span></span> <span data-ttu-id="eb6e0-139">例外：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-139">Exception:</span></span>

<span data-ttu-id="eb6e0-140">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="eb6e0-141">在</span><span class="sxs-lookup"><span data-stu-id="eb6e0-141">at</span></span>

<span data-ttu-id="eb6e0-142">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="eb6e0-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="eb6e0-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="eb6e0-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="eb6e0-144">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="eb6e0-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="eb6e0-145">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="eb6e0-145">Result : Failure</span></span>

<span data-ttu-id="eb6e0-146">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="eb6e0-146">Latency : 00:00:00</span></span>

<span data-ttu-id="eb6e0-147">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="eb6e0-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="eb6e0-148">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="eb6e0-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="eb6e0-149">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="eb6e0-149">established connection failed because connected host has</span></span>

<span data-ttu-id="eb6e0-150">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="eb6e0-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="eb6e0-151">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="eb6e0-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="eb6e0-152">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="eb6e0-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="eb6e0-153">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="eb6e0-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="eb6e0-154">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="eb6e0-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="eb6e0-155">診斷：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="eb6e0-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="eb6e0-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="eb6e0-157">以下是一些 **Test-CsUnifiedContactStore** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="eb6e0-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="eb6e0-158">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="eb6e0-159">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="eb6e0-160">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="eb6e0-161">連線至整合連絡人存放區失敗，但嘗試為使用者取回連絡人失敗。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="eb6e0-162">可能是網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="eb6e0-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb6e0-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eb6e0-163">See Also</span></span>


[<span data-ttu-id="eb6e0-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="eb6e0-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="eb6e0-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="eb6e0-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

