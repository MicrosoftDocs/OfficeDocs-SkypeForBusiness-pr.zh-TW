---
title: Lync Server 2013：測試 Web 應用程式存取
description: Lync Server 2013：測試 Web 應用程式存取。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3bbc8008df4fe47fc5a39571356383fe5a6035
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560829"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="73ac9-103">在 Lync Server 2013 中測試 Web 應用程式存取權</span><span class="sxs-lookup"><span data-stu-id="73ac9-103">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73ac9-104">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="73ac9-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73ac9-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="73ac9-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="73ac9-106">每月</span><span class="sxs-lookup"><span data-stu-id="73ac9-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73ac9-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="73ac9-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="73ac9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73ac9-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73ac9-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="73ac9-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="73ac9-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="73ac9-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="73ac9-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsWebApp Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="73ac9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="73ac9-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="73ac9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="73ac9-113">描述</span><span class="sxs-lookup"><span data-stu-id="73ac9-113">Description</span></span>

<span data-ttu-id="73ac9-114">Test-CsWebApp Cmdlet 會驗證已驗證的使用者是否可以使用 Lync Web App 加入 Lync Server 會議。</span><span class="sxs-lookup"><span data-stu-id="73ac9-114">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="73ac9-115">當您執行 Cmdlet 時，Test-CsWebApp 會聯繫 Web Ticket 服務，以取得指定使用者的 Web 入場券。</span><span class="sxs-lookup"><span data-stu-id="73ac9-115">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="73ac9-116">這些入場券會有效地充當 Lync Server 會議的「許可票證」。</span><span class="sxs-lookup"><span data-stu-id="73ac9-116">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="73ac9-117">若可取得票證，而且如果使用者可驗證，則 Test-CsWebApp 會聯繫 Lync Server，並嘗試建立個別會議以進行立即訊息、應用程式共用及資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="73ac9-117">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="73ac9-118">請注意，Test-CsWebApp 只會驗證用來建立這些會議的 APIs 和連線。</span><span class="sxs-lookup"><span data-stu-id="73ac9-118">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="73ac9-119">此 Cmdlet 的設計目的是要驗證 Lync Web App 是否可用於建立及加入會議。</span><span class="sxs-lookup"><span data-stu-id="73ac9-119">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="73ac9-120">不過，它不會實際建立及召開會議。</span><span class="sxs-lookup"><span data-stu-id="73ac9-120">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="73ac9-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="73ac9-121">Running the test</span></span>

<span data-ttu-id="73ac9-122">您可以使用一組預先設定的測試帳戶或任何兩個啟用 Lync Server 之使用者的帳戶執行 Test-CsWebApp Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="73ac9-122">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="73ac9-123">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="73ac9-123">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="73ac9-124">例如：</span><span class="sxs-lookup"><span data-stu-id="73ac9-124">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="73ac9-125">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="73ac9-125">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="73ac9-126">當您呼叫 Test-CsWebApp 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="73ac9-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="73ac9-127">如需詳細資訊，請參閱 [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="73ac9-127">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="73ac9-128">請注意，Test-CsWebApp 已過時，無法在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="73ac9-128">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="73ac9-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="73ac9-129">Determining success or failure</span></span>

<span data-ttu-id="73ac9-130">如果 Test-CsWebApp 可以將使用者加入其會議，此 Cmdlet 將會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="73ac9-130">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="73ac9-131">目標 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="73ac9-131">Target Fqdn :</span></span>

<span data-ttu-id="73ac9-132">結果：成功</span><span class="sxs-lookup"><span data-stu-id="73ac9-132">Result : Success</span></span>

<span data-ttu-id="73ac9-133">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="73ac9-133">Latency : 00:00:00</span></span>

<span data-ttu-id="73ac9-134">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="73ac9-134">Error Message :</span></span>

<span data-ttu-id="73ac9-135">診斷：</span><span class="sxs-lookup"><span data-stu-id="73ac9-135">Diagnosis :</span></span>

<span data-ttu-id="73ac9-136">如果使用者無法加入必要的會議，則測試結果會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="73ac9-136">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="73ac9-137">通常 Test-CsWebApp 也會報告詳細的錯誤訊息和診斷：</span><span class="sxs-lookup"><span data-stu-id="73ac9-137">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="73ac9-138">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="73ac9-138">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="73ac9-139">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="73ac9-139">Result : Failure</span></span>

<span data-ttu-id="73ac9-140">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="73ac9-140">Latency : 00:00:00</span></span>

<span data-ttu-id="73ac9-141">錯誤訊息：沒有為 Web-Ticket 服務接收任何回應</span><span class="sxs-lookup"><span data-stu-id="73ac9-141">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="73ac9-142">診斷：未授權用戶端的 HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="73ac9-142">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="73ac9-143">驗證架構「Ntlm」。</span><span class="sxs-lookup"><span data-stu-id="73ac9-143">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="73ac9-144">驗證</span><span class="sxs-lookup"><span data-stu-id="73ac9-144">The authentication</span></span>

<span data-ttu-id="73ac9-145">從伺服器收到的標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="73ac9-145">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="73ac9-146">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="73ac9-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="73ac9-147">Test-CsWebApp 失敗通常會涉及使用者驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="73ac9-147">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="73ac9-148">如果 Test-CsWebApp 失敗，您應該先確認指定的使用者具有有效的使用者帳戶，且已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="73ac9-148">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="73ac9-149">您可以使用類似下列的命令來取得帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="73ac9-149">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="73ac9-150">如果 Enabled 屬性不等於 True 或如果命令失敗，則表示使用者沒有有效的 Lync 伺服器帳戶。您也應該確認您提供給 Cmdlet 的密碼是有效的。</span><span class="sxs-lookup"><span data-stu-id="73ac9-150">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

