---
title: Lync Server 2013：測試 Exchange 至 Lync 通知
description: Lync Server 2013：測試 Exchange 至 Lync 通知。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf453bfdaab7e7b6bdaae8b67ac7759c0d55af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560619"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="9dbfb-103">在 Lync Server 2013 中測試 Exchange 至 Lync 通知</span><span class="sxs-lookup"><span data-stu-id="9dbfb-103">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dbfb-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="9dbfb-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dbfb-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="9dbfb-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9dbfb-106">每日</span><span class="sxs-lookup"><span data-stu-id="9dbfb-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dbfb-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="9dbfb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9dbfb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dbfb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dbfb-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="9dbfb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9dbfb-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9dbfb-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsExStorageNotification</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="9dbfb-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9dbfb-113">描述</span><span class="sxs-lookup"><span data-stu-id="9dbfb-113">Description</span></span>

<span data-ttu-id="9dbfb-114">**Test-CsExStorageNotification**指令程式可用來驗證 Microsoft Exchange Server 2013 notification 服務是否可在任何時候對使用者的連絡人清單進行更新時通知 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-114">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="9dbfb-115">此 Cmdlet 只有在您使用整合連絡人存放區時才有效。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-115">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9dbfb-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="9dbfb-116">Running the test</span></span>

<span data-ttu-id="9dbfb-117">範例1所示的命令會測試，以查看 Lync Server Storage Service 是否可以連線至使用者 sip:kenmyer@litwareinc.com 的 Microsoft Exchange Server 信箱通知服務。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-117">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="9dbfb-118">在此範例中，NetNamedPipe 是用來做為 WCF 系結。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-118">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9dbfb-119">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="9dbfb-119">Determining success or failure</span></span>

<span data-ttu-id="9dbfb-120">如果 Exchange 整合設定正確，您會收到類似以下的輸出，並將 Result 屬性標示為 [ **成功**]：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-120">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="9dbfb-121">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9dbfb-121">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9dbfb-122">結果：成功</span><span class="sxs-lookup"><span data-stu-id="9dbfb-122">Result : Success</span></span>

<span data-ttu-id="9dbfb-123">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="9dbfb-123">Latency : 00:00:00</span></span>

<span data-ttu-id="9dbfb-124">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-124">Error Message :</span></span>

<span data-ttu-id="9dbfb-125">診斷：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-125">Diagnosis :</span></span>

<span data-ttu-id="9dbfb-126">如果指定的使用者無法接收通知，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-126">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="9dbfb-127">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9dbfb-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9dbfb-128">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="9dbfb-128">Result : Failure</span></span>

<span data-ttu-id="9dbfb-129">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="9dbfb-129">Latency : 00:00:00</span></span>

<span data-ttu-id="9dbfb-130">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="9dbfb-130">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="9dbfb-131">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="9dbfb-131">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="9dbfb-132">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="9dbfb-132">established connection failed because connected host has</span></span>

<span data-ttu-id="9dbfb-133">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="9dbfb-133">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9dbfb-134">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="9dbfb-134">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="9dbfb-135">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="9dbfb-135">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="9dbfb-136">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="9dbfb-136">time, or established connection failed because connected host</span></span>

<span data-ttu-id="9dbfb-137">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="9dbfb-137">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="9dbfb-138">診斷：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-138">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9dbfb-139">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="9dbfb-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="9dbfb-140">以下是一些 **Test-CsExStorageNotification** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="9dbfb-140">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="9dbfb-141">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-141">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="9dbfb-142">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-142">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="9dbfb-143">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-143">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="9dbfb-144">如果 Microsoft Exchange 伺服器設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="9dbfb-144">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9dbfb-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9dbfb-145">See Also</span></span>


[<span data-ttu-id="9dbfb-146">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="9dbfb-146">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

