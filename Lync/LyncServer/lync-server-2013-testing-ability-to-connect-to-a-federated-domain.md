---
title: Lync Server 2013：測試連線到聯盟網域的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2176008e3e941068f61a2fb385fa6230df6b25dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="00b79-102">從 Lync Server 2013 到聯盟網域的測試能力</span><span class="sxs-lookup"><span data-stu-id="00b79-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00b79-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="00b79-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00b79-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="00b79-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="00b79-105">日常</span><span class="sxs-lookup"><span data-stu-id="00b79-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00b79-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="00b79-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="00b79-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00b79-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00b79-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="00b79-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="00b79-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="00b79-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="00b79-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsFederatedPartner Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="00b79-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="00b79-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="00b79-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="00b79-112">描述</span><span class="sxs-lookup"><span data-stu-id="00b79-112">Description</span></span>

<span data-ttu-id="00b79-113">CsFederatedPartner 會驗證您是否能夠連線到聯盟合作夥伴的網域。</span><span class="sxs-lookup"><span data-stu-id="00b79-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="00b79-114">若要驗證與網域的連線性，該網域必須列在允許（同盟）網域的集合中。</span><span class="sxs-lookup"><span data-stu-id="00b79-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="00b79-115">您可以使用此命令，在 [允許的網域] 清單中檢索網域清單：</span><span class="sxs-lookup"><span data-stu-id="00b79-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="00b79-116">如需詳細資訊，請參閱[Test CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="00b79-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="00b79-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="00b79-117">Running the test</span></span>

<span data-ttu-id="00b79-118">FederatedPartner Cmdlet 需要兩種資訊：邊緣伺服器的 FQDN 和聯盟夥伴的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="00b79-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="00b79-119">例如，這個命令會測試連接至網域 contoso.com 的能力：</span><span class="sxs-lookup"><span data-stu-id="00b79-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="00b79-120">這個命令可讓您測試目前 [允許的網域] 清單中所有網域的連線：</span><span class="sxs-lookup"><span data-stu-id="00b79-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="00b79-121">如需詳細資訊，請參閱[Test CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="00b79-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="00b79-122">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="00b79-122">Determining success or failure</span></span>

<span data-ttu-id="00b79-123">如果您可以與指定的網域取得聯繫，您會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="00b79-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="00b79-124">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="00b79-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="00b79-125">結果：成功</span><span class="sxs-lookup"><span data-stu-id="00b79-125">Result : Success</span></span>

<span data-ttu-id="00b79-126">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="00b79-126">Latency : 00:00:00</span></span>

<span data-ttu-id="00b79-127">出錯</span><span class="sxs-lookup"><span data-stu-id="00b79-127">Error :</span></span>

<span data-ttu-id="00b79-128">自檢</span><span class="sxs-lookup"><span data-stu-id="00b79-128">Diagnosis :</span></span>

<span data-ttu-id="00b79-129">如果無法連絡指定的網域，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="00b79-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="00b79-130">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="00b79-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="00b79-131">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="00b79-131">Result : Failure</span></span>

<span data-ttu-id="00b79-132">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="00b79-132">Latency : 00:00:00</span></span>

<span data-ttu-id="00b79-133">錯誤：504，伺服器超時</span><span class="sxs-lookup"><span data-stu-id="00b79-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="00b79-134">診斷： ErrorCode = 2，Source = litwareinc = atl-ws-01，原因 = 請參閱</span><span class="sxs-lookup"><span data-stu-id="00b79-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="00b79-135">回應程式碼與原因片語。</span><span class="sxs-lookup"><span data-stu-id="00b79-135">response code and reason phrase.</span></span>

<span data-ttu-id="00b79-136">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="00b79-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="00b79-137">例如，先前的輸出指出伺服器因逾時錯誤而失敗。</span><span class="sxs-lookup"><span data-stu-id="00b79-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="00b79-138">這通常表示網路連通性問題，或與邊緣伺服器聯絡時會發生問題。</span><span class="sxs-lookup"><span data-stu-id="00b79-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="00b79-139">如果測試 CsFederatedPartner 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="00b79-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="00b79-140">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="00b79-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="00b79-141">以下是測試 CsFederatedPartner 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="00b79-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="00b79-142">Edge 伺服器可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="00b79-142">The Edge Server might not be available.</span></span> <span data-ttu-id="00b79-143">您可以使用此命令，讓您的邊緣伺服器的 Fqdn 如下：</span><span class="sxs-lookup"><span data-stu-id="00b79-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="00b79-144">然後，您可以 ping 每個 Edge 伺服器，以確認可以在網路上存取它。</span><span class="sxs-lookup"><span data-stu-id="00b79-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="00b79-145">例如：</span><span class="sxs-lookup"><span data-stu-id="00b79-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="00b79-146">指定的網域可能不會列于 [允許的網域] 清單中。</span><span class="sxs-lookup"><span data-stu-id="00b79-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="00b79-147">若要驗證已新增至 [允許的網域] 清單中的網域，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="00b79-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="00b79-148">如果您想要查看已封鎖使用者與之通訊的網域清單，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="00b79-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

