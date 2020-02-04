---
title: Lync Server 2013：測試 Exchange 與 Lync 通知
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
ms.openlocfilehash: 37f163d5a43dce9672535ec3d78f360bcec8d926
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="39325-102">在 Lync Server 2013 中測試 Lync 通知的 Exchange</span><span class="sxs-lookup"><span data-stu-id="39325-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39325-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="39325-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39325-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="39325-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="39325-105">日常</span><span class="sxs-lookup"><span data-stu-id="39325-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39325-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="39325-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="39325-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39325-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39325-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="39325-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="39325-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="39325-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="39325-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsExStorageNotification</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="39325-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="39325-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="39325-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="39325-112">說明</span><span class="sxs-lookup"><span data-stu-id="39325-112">Description</span></span>

<span data-ttu-id="39325-113">**CsExStorageNotification** Cmdlet 可用來驗證 Microsoft Exchange Server 2013 通知服務是否可在任何時候對使用者的連絡人清單進行更新時通知 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="39325-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="39325-114">這個 Cmdlet 只會在您使用整合連絡人存放區時有效。</span><span class="sxs-lookup"><span data-stu-id="39325-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="39325-115">執行測試</span><span class="sxs-lookup"><span data-stu-id="39325-115">Running the test</span></span>

<span data-ttu-id="39325-116">範例1中顯示的命令會測試，以查看 Lync Server Storage Service 是否可連線到使用者 sip:kenmyer@litwareinc.com 的 Microsoft Exchange Server 信箱通知服務。</span><span class="sxs-lookup"><span data-stu-id="39325-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="39325-117">在這個範例中，NetNamedPipe 是用來做為 WCF 系結。</span><span class="sxs-lookup"><span data-stu-id="39325-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="39325-118">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="39325-118">Determining success or failure</span></span>

<span data-ttu-id="39325-119">如果 Exchange 整合設定正確，您會收到類似以下的輸出，結果屬性標示為**成功**：</span><span class="sxs-lookup"><span data-stu-id="39325-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="39325-120">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39325-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39325-121">結果：成功</span><span class="sxs-lookup"><span data-stu-id="39325-121">Result : Success</span></span>

<span data-ttu-id="39325-122">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="39325-122">Latency : 00:00:00</span></span>

<span data-ttu-id="39325-123">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="39325-123">Error Message :</span></span>

<span data-ttu-id="39325-124">自檢</span><span class="sxs-lookup"><span data-stu-id="39325-124">Diagnosis :</span></span>

<span data-ttu-id="39325-125">如果指定的使用者無法接收通知，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="39325-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="39325-126">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="39325-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="39325-127">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="39325-127">Result : Failure</span></span>

<span data-ttu-id="39325-128">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="39325-128">Latency : 00:00:00</span></span>

<span data-ttu-id="39325-129">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="39325-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="39325-130">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="39325-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="39325-131">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="39325-131">established connection failed because connected host has</span></span>

<span data-ttu-id="39325-132">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="39325-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="39325-133">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="39325-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="39325-134">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="39325-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="39325-135">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="39325-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="39325-136">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="39325-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="39325-137">自檢</span><span class="sxs-lookup"><span data-stu-id="39325-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="39325-138">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="39325-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="39325-139">以下是**測試 CsExStorageNotification**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="39325-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="39325-140">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="39325-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="39325-141">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="39325-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="39325-142">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="39325-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="39325-143">如果 Microsoft Exchange Server 未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="39325-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39325-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="39325-144">See Also</span></span>


[<span data-ttu-id="39325-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="39325-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

