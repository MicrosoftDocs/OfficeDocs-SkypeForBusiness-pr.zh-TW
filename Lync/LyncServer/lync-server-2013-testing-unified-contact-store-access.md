---
title: Lync Server 2013： 測試整合連絡人存放區的存取
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
ms.openlocfilehash: 6022d7651a99c2165961ed8cb8852048c10779ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="692cb-102">在 Lync Server 2013 中進行測試整合連絡人存放區的存取</span><span class="sxs-lookup"><span data-stu-id="692cb-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="692cb-103">_**主題上次修改日期：** 2015年-05-15_</span><span class="sxs-lookup"><span data-stu-id="692cb-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="692cb-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="692cb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="692cb-105">每日</span><span class="sxs-lookup"><span data-stu-id="692cb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="692cb-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="692cb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="692cb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="692cb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="692cb-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="692cb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="692cb-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="692cb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="692cb-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csunifiedcontactstore</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="692cb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="692cb-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="692cb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="692cb-112">描述</span><span class="sxs-lookup"><span data-stu-id="692cb-112">Description</span></span>

<span data-ttu-id="692cb-113">在 Lync Server 2013 中引進整合連絡人存放區提供系統管理員將使用者的連絡人儲存在 Microsoft Exchange Server 2013 而不是在 Lync Server 中的選項。</span><span class="sxs-lookup"><span data-stu-id="692cb-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="692cb-114">這可讓使用者存取相同的 Outlook Web Access，除了 Lync 2013 中的連絡人集合。</span><span class="sxs-lookup"><span data-stu-id="692cb-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="692cb-115">（或者，您可以繼續將連絡人儲存在 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="692cb-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="692cb-116">In that case，使用者仍必須維護兩組不同的連絡人： 一個用於 Outlook 和 Outlook Web Access，一個用於與 Lync 2013 搭配使用。)</span><span class="sxs-lookup"><span data-stu-id="692cb-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="692cb-117">您可以判斷使用者的連絡人已執行**Test-csunifiedcontactstore** cmdlet 來移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="692cb-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="692cb-118">**Test-csunifiedcontactstore** cmdlet 將會採取指定的使用者帳戶，連線至整合連絡人存放區，並嘗試擷取使用者的連絡人。</span><span class="sxs-lookup"><span data-stu-id="692cb-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="692cb-119">如果可以不擷取任何連絡人然後命令將會失敗搭配 「 沒有連絡人已收到郵件的使用者。</span><span class="sxs-lookup"><span data-stu-id="692cb-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="692cb-120">確認連絡人存在的使用者。 」</span><span class="sxs-lookup"><span data-stu-id="692cb-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="692cb-121">請注意，如果使用者已成功地移轉至整合連絡人存放區，但不有他/她的連絡人清單上的任何連絡人**Test-csunifiedcontactstore** cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="692cb-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="692cb-122">指定的使用者必須至少一個連絡人**Test-csunifiedcontactstore** cmdlet 才能順利完成。</span><span class="sxs-lookup"><span data-stu-id="692cb-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="692cb-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="692cb-123">Running the test</span></span>

<span data-ttu-id="692cb-124">下列範例所示的命令判斷是否連絡人使用者 litwareinc\\kenmyer 可以在整合連絡人存放區中找到。</span><span class="sxs-lookup"><span data-stu-id="692cb-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="692cb-125">若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立使用者 litwareinc 所需的 Windows PowerShell 命令列介面認證物件\\kenmyer。</span><span class="sxs-lookup"><span data-stu-id="692cb-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="692cb-126">請注意，您必須提供建立有效的認證物件，並確定**Test-csunifiedcontactstore** cmdlet 可以執行其檢查此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="692cb-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="692cb-127">此範例中的第二個命令使用提供的認證物件 ($x) 和的 SIP 位址的使用者 litwareinc\\kenmyer 來判斷是否可以在整合連絡人存放區中找到他的連絡人。</span><span class="sxs-lookup"><span data-stu-id="692cb-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="692cb-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="692cb-128">Determining success or failure</span></span>

<span data-ttu-id="692cb-129">如果已正確設定的存取權的連絡人存放區，您會收到類似，具有標示為 Result 屬性的輸出**成功：**</span><span class="sxs-lookup"><span data-stu-id="692cb-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="692cb-130">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="692cb-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="692cb-131">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="692cb-131">Result : Success</span></span>

<span data-ttu-id="692cb-132">延遲： 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="692cb-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="692cb-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="692cb-133">Error Message :</span></span>

<span data-ttu-id="692cb-134">診斷：</span><span class="sxs-lookup"><span data-stu-id="692cb-134">Diagnosis :</span></span>

<span data-ttu-id="692cb-135">如果未正確設定的存取權的連絡人存放區，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="692cb-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="692cb-136">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="692cb-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="692cb-137">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="692cb-137">domain name (FQDN).</span></span> <span data-ttu-id="692cb-138">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="692cb-138">Using default Registrar port number.</span></span> <span data-ttu-id="692cb-139">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="692cb-139">Exception:</span></span>

<span data-ttu-id="692cb-140">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="692cb-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="692cb-141">在</span><span class="sxs-lookup"><span data-stu-id="692cb-141">at</span></span>

<span data-ttu-id="692cb-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="692cb-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="692cb-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="692cb-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="692cb-144">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="692cb-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="692cb-145">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="692cb-145">Result : Failure</span></span>

<span data-ttu-id="692cb-146">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="692cb-146">Latency : 00:00:00</span></span>

<span data-ttu-id="692cb-147">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="692cb-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="692cb-148">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="692cb-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="692cb-149">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="692cb-149">established connection failed because connected host has</span></span>

<span data-ttu-id="692cb-150">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="692cb-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="692cb-151">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="692cb-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="692cb-152">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="692cb-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="692cb-153">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="692cb-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="692cb-154">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="692cb-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="692cb-155">診斷：</span><span class="sxs-lookup"><span data-stu-id="692cb-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="692cb-156">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="692cb-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="692cb-157">以下是一些常見的原因為何**Test-csunifiedcontactstore**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="692cb-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="692cb-158">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="692cb-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="692cb-159">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="692cb-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="692cb-160">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="692cb-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="692cb-161">連接至整合連絡人存放區失敗，並嘗試擷取使用者的連絡人是不可行。</span><span class="sxs-lookup"><span data-stu-id="692cb-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="692cb-162">可能有網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="692cb-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="692cb-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="692cb-163">See Also</span></span>


[<span data-ttu-id="692cb-164">New-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="692cb-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="692cb-165">Set-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="692cb-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

