---
title: Lync Server 2013： 測試在會議中共用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a98312c04b943d485e1c6668b1c9347c9714e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a><span data-ttu-id="dd08f-102">測試 Lync Server 2013 中的會議中共用</span><span class="sxs-lookup"><span data-stu-id="dd08f-102">Testing sharing in conferences in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd08f-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="dd08f-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd08f-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="dd08f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dd08f-105">每日</span><span class="sxs-lookup"><span data-stu-id="dd08f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd08f-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="dd08f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dd08f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd08f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd08f-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="dd08f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dd08f-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="dd08f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dd08f-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csdataconference</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="dd08f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDataConference</strong> cmdlet.</span></span> <span data-ttu-id="dd08f-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dd08f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dd08f-112">描述</span><span class="sxs-lookup"><span data-stu-id="dd08f-112">Description</span></span>

<span data-ttu-id="dd08f-113">在 Lync Server 2013 中，資料會議是任何會議可用共同作業活動，例如白板或註解。</span><span class="sxs-lookup"><span data-stu-id="dd08f-113">In Lync Server 2013, a data conference is any conference where collaborative activities such as whiteboarding or annotations are used.</span></span> <span data-ttu-id="dd08f-114">**Test-csdataconference** cmdlet 可讓您確認一組的使用者都可以參與資料會議。</span><span class="sxs-lookup"><span data-stu-id="dd08f-114">The **Test-CsDataConference** cmdlet enables you to verify that a pair of users are able to take part in a data conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dd08f-115">執行測試</span><span class="sxs-lookup"><span data-stu-id="dd08f-115">Running the test</span></span>

<span data-ttu-id="dd08f-116">範例 1 所示的命令會驗證資料會議，可以在集區 atl-cs-001.litwareinc.com 上進行。</span><span class="sxs-lookup"><span data-stu-id="dd08f-116">The command shown in Example 1 verifies that a data conference can be conducted on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="dd08f-117">這個命令會假設您已設定的測試使用者指定的集區配對。</span><span class="sxs-lookup"><span data-stu-id="dd08f-117">This command assumes that you have configured a pair of test users for the specified pool.</span></span> <span data-ttu-id="dd08f-118">如果沒有這類測試使用者存在，命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dd08f-118">If no such test users exist, the command will fail.</span></span>

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="dd08f-119">範例 2 所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 來登入 Lync Server 2013 和再進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="dd08f-119">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then conduct a data conference.</span></span> <span data-ttu-id="dd08f-120">若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立包含其名稱和密碼的使用者為 Pilar Ackerman 的 Windows PowerShell 命令列介面認證物件。</span><span class="sxs-lookup"><span data-stu-id="dd08f-120">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object containing the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="dd08f-121">(因為登入名稱中，litwareinc\\pilar，已包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。</span><span class="sxs-lookup"><span data-stu-id="dd08f-121">(Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="dd08f-122">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="dd08f-122">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="dd08f-123">在手中的認證物件，第三個命令會決定這些兩個使用者可以登入 Lync Server 2013，並先進行資料會議。</span><span class="sxs-lookup"><span data-stu-id="dd08f-123">With the credential objects in hand, the third command determines whether or not these two users can log on to Lync Server 2013 and conduct a data conference.</span></span> <span data-ttu-id="dd08f-124">若要執行這項工作， **Test-csdataconference** cmdlet 呼叫時，以及下列參數： TargetFqdn (之登錄器集區 FQDN);SenderSipAddress （第一個測試使用者的 SIP 位址）;與 SenderCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;並與 ReceiverCredential （Windows PowerShell 物件包含其他測試使用者的認證）。</span><span class="sxs-lookup"><span data-stu-id="dd08f-124">To carry out this task, the **Test-CsDataConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object containing the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object containing the credentials for the other test user).</span></span>

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dd08f-125">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="dd08f-125">Determining success or failure</span></span>

<span data-ttu-id="dd08f-126">如果已正確設定資料會議，您會收到類似，具有標示為 Result 屬性的輸出**成功：**</span><span class="sxs-lookup"><span data-stu-id="dd08f-126">If data conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="dd08f-127">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd08f-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd08f-128">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="dd08f-128">Result : Success</span></span>

<span data-ttu-id="dd08f-129">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dd08f-129">Latency : 00:00:00</span></span>

<span data-ttu-id="dd08f-130">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="dd08f-130">Error Message :</span></span>

<span data-ttu-id="dd08f-131">診斷：</span><span class="sxs-lookup"><span data-stu-id="dd08f-131">Diagnosis :</span></span>

<span data-ttu-id="dd08f-132">如果指定的使用者無法使用 」 資料共用，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="dd08f-132">If the specified users can't use data sharing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="dd08f-133">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd08f-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd08f-134">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="dd08f-134">Result : Failure</span></span>

<span data-ttu-id="dd08f-135">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="dd08f-135">Latency : 00:00:00</span></span>

<span data-ttu-id="dd08f-136">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="dd08f-136">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="dd08f-137">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="dd08f-137">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="dd08f-138">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="dd08f-138">established connection failed because connected host has</span></span>

<span data-ttu-id="dd08f-139">失敗回應\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="dd08f-139">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="dd08f-140">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="dd08f-140">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="dd08f-141">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="dd08f-141">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="dd08f-142">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="dd08f-142">time, or established connection failed because connected host</span></span>

<span data-ttu-id="dd08f-143">失敗回應</span><span class="sxs-lookup"><span data-stu-id="dd08f-143">has failed to respond</span></span>

<span data-ttu-id="dd08f-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="dd08f-144">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="dd08f-145">診斷：</span><span class="sxs-lookup"><span data-stu-id="dd08f-145">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dd08f-146">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="dd08f-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="dd08f-147">以下是一些常見的原因為何**Test-csdataconference**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="dd08f-147">Here are some common reasons why **Test-CsDataConference** might fail:</span></span>

  - <span data-ttu-id="dd08f-148">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="dd08f-148">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="dd08f-149">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dd08f-149">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="dd08f-150">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="dd08f-150">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="dd08f-151">若要進行資料會議功能取決於已指派給召開會議 （若是**Test-csdataconference** cmdlet，為 「 寄件者 」) 之使用者的會議原則。</span><span class="sxs-lookup"><span data-stu-id="dd08f-151">The ability to conduct a data conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsDataConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="dd08f-152">如果召集人不允許包含共同作業活動他/她的會議中 （例如，如果他/她的會議原則有 EnableDataCollaboration 屬性設為 False） 然後**Test-csdataconference** cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="dd08f-152">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsDataConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="dd08f-153">如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dd08f-153">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

