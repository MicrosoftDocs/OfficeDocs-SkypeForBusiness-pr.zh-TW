---
title: Lync Server 2013： 測試 Exchange Lync 通知
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
ms.openlocfilehash: c5e6010d7884bca7ec82d4992b83e22cce315b1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="8d8f3-102">測試 Exchange，以在 Lync Server 2013 中的 Lync 通知</span><span class="sxs-lookup"><span data-stu-id="8d8f3-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d8f3-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="8d8f3-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d8f3-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="8d8f3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8d8f3-105">每日</span><span class="sxs-lookup"><span data-stu-id="8d8f3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d8f3-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="8d8f3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8d8f3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d8f3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d8f3-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="8d8f3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8d8f3-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8d8f3-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csexstoragenotification</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="8d8f3-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8d8f3-112">描述</span><span class="sxs-lookup"><span data-stu-id="8d8f3-112">Description</span></span>

<span data-ttu-id="8d8f3-113">**Test-csexstoragenotification** cmdlet 用來驗證，Microsoft Exchange Server 2013 通知服務可以通知 Lync Server 2013 的任何時間更新會對使用者的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="8d8f3-114">此指令程式時才有效只有在您使用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8d8f3-115">執行測試</span><span class="sxs-lookup"><span data-stu-id="8d8f3-115">Running the test</span></span>

<span data-ttu-id="8d8f3-116">若要查看 Lync Server 儲存體服務是否可以連線至使用者 sip:kenmyer@litwareinc.com 的 Microsoft Exchange Server 信箱通知服務中的測試範例 1 所示的命令。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="8d8f3-117">在這個範例中，NetNamedPipe 會當做 WCF 繫結。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8d8f3-118">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="8d8f3-118">Determining success or failure</span></span>

<span data-ttu-id="8d8f3-119">如果已正確設定 Exchange 整合，您會收到類似，具有標示為 [**成功**結果屬性的輸出：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="8d8f3-120">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8d8f3-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8d8f3-121">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="8d8f3-121">Result : Success</span></span>

<span data-ttu-id="8d8f3-122">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8d8f3-122">Latency : 00:00:00</span></span>

<span data-ttu-id="8d8f3-123">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-123">Error Message :</span></span>

<span data-ttu-id="8d8f3-124">診斷：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-124">Diagnosis :</span></span>

<span data-ttu-id="8d8f3-125">如果指定的使用者無法收到通知，結果會顯示為失敗，及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8d8f3-126">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8d8f3-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8d8f3-127">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="8d8f3-127">Result : Failure</span></span>

<span data-ttu-id="8d8f3-128">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8d8f3-128">Latency : 00:00:00</span></span>

<span data-ttu-id="8d8f3-129">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="8d8f3-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="8d8f3-130">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="8d8f3-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="8d8f3-131">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="8d8f3-131">established connection failed because connected host has</span></span>

<span data-ttu-id="8d8f3-132">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="8d8f3-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="8d8f3-133">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="8d8f3-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="8d8f3-134">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="8d8f3-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="8d8f3-135">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="8d8f3-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="8d8f3-136">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="8d8f3-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="8d8f3-137">診斷：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8d8f3-138">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="8d8f3-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="8d8f3-139">以下是一些常見的原因為何**Test-csexstoragenotification**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="8d8f3-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="8d8f3-140">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="8d8f3-141">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="8d8f3-142">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="8d8f3-143">如果設定錯誤或尚未部署 Microsoft Exchange 伺服器，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8d8f3-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d8f3-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8d8f3-144">See Also</span></span>


[<span data-ttu-id="8d8f3-145">Test-csexstorageconnectivity</span><span class="sxs-lookup"><span data-stu-id="8d8f3-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

