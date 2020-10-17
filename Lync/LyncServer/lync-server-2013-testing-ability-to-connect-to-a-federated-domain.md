---
title: Lync Server 2013：測試連接至同盟網域的能力
description: Lync Server 2013：測試連接至同盟網域的能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560819"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="bf18a-103">從 Lync Server 2013 測試連線到同盟網域的能力</span><span class="sxs-lookup"><span data-stu-id="bf18a-103">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf18a-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bf18a-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf18a-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="bf18a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bf18a-106">每日</span><span class="sxs-lookup"><span data-stu-id="bf18a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf18a-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="bf18a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bf18a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf18a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf18a-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="bf18a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bf18a-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bf18a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bf18a-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsFederatedPartner Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="bf18a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="bf18a-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bf18a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bf18a-113">描述</span><span class="sxs-lookup"><span data-stu-id="bf18a-113">Description</span></span>

<span data-ttu-id="bf18a-114">Test-CsFederatedPartner 會驗證您是否能夠連線到同盟協力廠商的網域。</span><span class="sxs-lookup"><span data-stu-id="bf18a-114">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="bf18a-115">若要驗證網域的連線能力，該網域必須列在 (同盟) 網域的允許集合中。</span><span class="sxs-lookup"><span data-stu-id="bf18a-115">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="bf18a-116">您可以使用下列命令，在允許的網域清單上檢索網域清單：</span><span class="sxs-lookup"><span data-stu-id="bf18a-116">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="bf18a-117">如需詳細資訊，請參閱 [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="bf18a-117">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bf18a-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="bf18a-118">Running the test</span></span>

<span data-ttu-id="bf18a-119">Test-FederatedPartner Cmdlet 需要兩部分資訊： Edge Server 的 FQDN 和同盟協力廠商的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bf18a-119">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="bf18a-120">例如，此命令會測試連線至網域 contoso.com 的功能：</span><span class="sxs-lookup"><span data-stu-id="bf18a-120">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="bf18a-121">這個命令可讓您測試目前允許的網域清單上的所有網域的連線：</span><span class="sxs-lookup"><span data-stu-id="bf18a-121">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="bf18a-122">如需詳細資訊，請參閱 [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="bf18a-122">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bf18a-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="bf18a-123">Determining success or failure</span></span>

<span data-ttu-id="bf18a-124">如果可以聯繫指定的網域，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="bf18a-124">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="bf18a-125">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bf18a-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bf18a-126">結果：成功</span><span class="sxs-lookup"><span data-stu-id="bf18a-126">Result : Success</span></span>

<span data-ttu-id="bf18a-127">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="bf18a-127">Latency : 00:00:00</span></span>

<span data-ttu-id="bf18a-128">錯誤：</span><span class="sxs-lookup"><span data-stu-id="bf18a-128">Error :</span></span>

<span data-ttu-id="bf18a-129">診斷：</span><span class="sxs-lookup"><span data-stu-id="bf18a-129">Diagnosis :</span></span>

<span data-ttu-id="bf18a-130">若無法連絡指定的網域，則結果會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="bf18a-130">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="bf18a-131">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="bf18a-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="bf18a-132">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="bf18a-132">Result : Failure</span></span>

<span data-ttu-id="bf18a-133">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="bf18a-133">Latency : 00:00:00</span></span>

<span data-ttu-id="bf18a-134">錯誤：504，伺服器超時</span><span class="sxs-lookup"><span data-stu-id="bf18a-134">Error : 504, Server time-out</span></span>

<span data-ttu-id="bf18a-135">診斷： ErrorCode = 2，Source = atl-ws-01-cs，Reason = 請參閱</span><span class="sxs-lookup"><span data-stu-id="bf18a-135">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="bf18a-136">回應碼和 reason 片語。</span><span class="sxs-lookup"><span data-stu-id="bf18a-136">response code and reason phrase.</span></span>

<span data-ttu-id="bf18a-137">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="bf18a-137">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="bf18a-138">例如，上一個輸出規定因伺服器逾時錯誤，測試失敗。</span><span class="sxs-lookup"><span data-stu-id="bf18a-138">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="bf18a-139">這通常表示網路連線問題或聯繫 Edge Server 的問題。</span><span class="sxs-lookup"><span data-stu-id="bf18a-139">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="bf18a-140">如果 Test-CsFederatedPartner 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="bf18a-140">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bf18a-141">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="bf18a-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="bf18a-142">以下是一些 Test-CsFederatedPartner 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="bf18a-142">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="bf18a-143">Edge Server 可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="bf18a-143">The Edge Server might not be available.</span></span> <span data-ttu-id="bf18a-144">您可以使用下列命令來執行 Edge Server 的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="bf18a-144">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="bf18a-145">然後，您可以 ping 每一部 Edge Server，以確認可透過網路存取它。</span><span class="sxs-lookup"><span data-stu-id="bf18a-145">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="bf18a-146">例如：</span><span class="sxs-lookup"><span data-stu-id="bf18a-146">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="bf18a-147">指定的網域可能並未列在允許的網域清單上。</span><span class="sxs-lookup"><span data-stu-id="bf18a-147">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="bf18a-148">若要驗證新增至允許的網域清單中的網域，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bf18a-148">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="bf18a-149">如果您想要查看封鎖使用者通訊的網域清單，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="bf18a-149">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

