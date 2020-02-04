---
title: Lync Server 2013：測試整合連絡人存放區存取權
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
ms.openlocfilehash: 47d5d216a1d7a389f20bf2c59f94baf54636d409
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="b380e-102">在 Lync Server 2013 中測試整合連絡人存放區存取權</span><span class="sxs-lookup"><span data-stu-id="b380e-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b380e-103">_**主題上次修改日期：** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="b380e-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b380e-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="b380e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b380e-105">日常</span><span class="sxs-lookup"><span data-stu-id="b380e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b380e-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="b380e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b380e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b380e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b380e-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="b380e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b380e-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b380e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b380e-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsUnifiedContactStore</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b380e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="b380e-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b380e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b380e-112">說明</span><span class="sxs-lookup"><span data-stu-id="b380e-112">Description</span></span>

<span data-ttu-id="b380e-113">在 Lync Server 2013 中引入的整合連絡人存放區，可讓系統管理員選擇將使用者的連絡人儲存在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="b380e-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="b380e-114">這可讓使用者除了 Lync 2013 之外，還能在 Outlook Web Access 中存取同一組連絡人。</span><span class="sxs-lookup"><span data-stu-id="b380e-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="b380e-115">（或者，您可以繼續在 Lync Server 中儲存連絡人。</span><span class="sxs-lookup"><span data-stu-id="b380e-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="b380e-116">在這種情況下，使用者將必須維護兩組不同的連絡人：一個用於 Outlook 與 Outlook Web Access，另一個用於 Lync 2013。）</span><span class="sxs-lookup"><span data-stu-id="b380e-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="b380e-117">您可以執行**CsUnifiedContactStore** Cmdlet，判斷是否已將使用者的連絡人移至 [整合連絡人存放區]。</span><span class="sxs-lookup"><span data-stu-id="b380e-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="b380e-118">**CsUnifiedContactStore** Cmdlet 會採用指定的使用者帳戶、連線到 [整合] 連絡人存放區，並嘗試為使用者檢索連絡人。</span><span class="sxs-lookup"><span data-stu-id="b380e-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="b380e-119">如果無法檢索任何連絡人，則命令會失敗，並出現「使用者沒有收到連絡人的訊息。</span><span class="sxs-lookup"><span data-stu-id="b380e-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="b380e-120">確認使用者有連絡人。」</span><span class="sxs-lookup"><span data-stu-id="b380e-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="b380e-121">請注意，如果使用者已成功遷移至 [整合連絡人] 存放區，但其連絡人清單中沒有連絡人，則**CsUnifiedContactStore** Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b380e-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="b380e-122">指定的使用者必須至少有一個連絡人， **CsUnifiedContactStore** Cmdlet 才能順利完成。</span><span class="sxs-lookup"><span data-stu-id="b380e-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b380e-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="b380e-123">Running the test</span></span>

<span data-ttu-id="b380e-124">下列範例所示的命令會判斷是否可在整合連絡人存放\\區中找到使用者 litwareinc kenmyer 的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b380e-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="b380e-125">若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來為使用者 litwareinc\\kenmyer 建立 Windows PowerShell 命令列介面認證物件。</span><span class="sxs-lookup"><span data-stu-id="b380e-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="b380e-126">請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確認**Test CsUnifiedContactStore** Cmdlet 可以執行其檢查。</span><span class="sxs-lookup"><span data-stu-id="b380e-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="b380e-127">這個範例中的第二個命令使用所提供的認證物件（$x）和使用者 litwareinc\\KENMYER 的 SIP 位址來判斷是否可在整合連絡人存放區中找到他的連絡人。</span><span class="sxs-lookup"><span data-stu-id="b380e-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b380e-128">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="b380e-128">Determining success or failure</span></span>

<span data-ttu-id="b380e-129">如果正確設定對連絡人存放區的存取權，您會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="b380e-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b380e-130">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b380e-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b380e-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="b380e-131">Result : Success</span></span>

<span data-ttu-id="b380e-132">延隔時間：00：00：14.9862716</span><span class="sxs-lookup"><span data-stu-id="b380e-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="b380e-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="b380e-133">Error Message :</span></span>

<span data-ttu-id="b380e-134">自檢</span><span class="sxs-lookup"><span data-stu-id="b380e-134">Diagnosis :</span></span>

<span data-ttu-id="b380e-135">如果未正確設定對連絡人存放區的存取權，結果將會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="b380e-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b380e-136">警告：無法讀取指定之完全限定的註冊機構埠號碼</span><span class="sxs-lookup"><span data-stu-id="b380e-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="b380e-137">網功能變數名稱稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="b380e-137">domain name (FQDN).</span></span> <span data-ttu-id="b380e-138">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="b380e-138">Using default Registrar port number.</span></span> <span data-ttu-id="b380e-139">引發</span><span class="sxs-lookup"><span data-stu-id="b380e-139">Exception:</span></span>

<span data-ttu-id="b380e-140">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="b380e-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="b380e-141">的</span><span class="sxs-lookup"><span data-stu-id="b380e-141">at</span></span>

<span data-ttu-id="b380e-142">TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction</span><span class="sxs-lookup"><span data-stu-id="b380e-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="b380e-143">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="b380e-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="b380e-144">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b380e-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b380e-145">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="b380e-145">Result : Failure</span></span>

<span data-ttu-id="b380e-146">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="b380e-146">Latency : 00:00:00</span></span>

<span data-ttu-id="b380e-147">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="b380e-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b380e-148">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="b380e-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b380e-149">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="b380e-149">established connection failed because connected host has</span></span>

<span data-ttu-id="b380e-150">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="b380e-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b380e-151">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="b380e-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b380e-152">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="b380e-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b380e-153">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="b380e-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b380e-154">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="b380e-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b380e-155">自檢</span><span class="sxs-lookup"><span data-stu-id="b380e-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b380e-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="b380e-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="b380e-157">以下是**測試 CsUnifiedContactStore**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="b380e-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="b380e-158">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="b380e-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b380e-159">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b380e-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b380e-160">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="b380e-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b380e-161">連線至 [整合連絡人存放區] 失敗，且無法為使用者檢索連絡人的嘗試。</span><span class="sxs-lookup"><span data-stu-id="b380e-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="b380e-162">可能有網路連通性問題。</span><span class="sxs-lookup"><span data-stu-id="b380e-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b380e-163">請參閱</span><span class="sxs-lookup"><span data-stu-id="b380e-163">See Also</span></span>


[<span data-ttu-id="b380e-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b380e-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="b380e-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="b380e-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

