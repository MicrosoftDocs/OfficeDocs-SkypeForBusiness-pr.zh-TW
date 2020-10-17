---
title: Lync Server 2013：測試匿名 Web 應用程式存取
description: Lync Server 2013：測試匿名 Web 應用程式存取。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547469"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="da442-103">在 Lync Server 2013 中測試匿名 Web 應用程式存取權</span><span class="sxs-lookup"><span data-stu-id="da442-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da442-104">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="da442-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da442-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="da442-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="da442-106">每月</span><span class="sxs-lookup"><span data-stu-id="da442-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da442-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="da442-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="da442-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da442-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da442-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="da442-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="da442-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="da442-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="da442-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsWebAppAnonymous Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="da442-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="da442-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="da442-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="da442-113">描述</span><span class="sxs-lookup"><span data-stu-id="da442-113">Description</span></span>

<span data-ttu-id="da442-114">Test-CsWebAppAnonymous Cmdlet 會驗證匿名使用者是否可以使用 Lync Web App 加入 Lync Server 會議。</span><span class="sxs-lookup"><span data-stu-id="da442-114">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="da442-115">當您執行 Cmdlet 時，Test-CsWebAppAnonymous 會聯繫 Web Ticket 服務，以取得匿名使用者的 web 票證。</span><span class="sxs-lookup"><span data-stu-id="da442-115">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="da442-116">如果此 Cmdlet 成功取得此票證，Test-CsWebAppAnonymous 將會聯繫 Lync Server，並嘗試建立個別會議以進行立即訊息、應用程式共用及資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="da442-116">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="da442-117">請注意，Test-CsWebAppAnonymous 只會驗證用來建立這些會議的 APIs 和連線。</span><span class="sxs-lookup"><span data-stu-id="da442-117">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="da442-118">此 Cmdlet 不會實際建立及執行任何會議。</span><span class="sxs-lookup"><span data-stu-id="da442-118">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="da442-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="da442-119">Running the test</span></span>

<span data-ttu-id="da442-120">您可以使用一組預先設定的測試帳戶或任何兩個啟用 Lync Server 之使用者的帳戶執行 Test-CsWebAppAnonymous Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="da442-120">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="da442-121">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="da442-121">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="da442-122">例如：</span><span class="sxs-lookup"><span data-stu-id="da442-122">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="da442-123">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Lync Server 管理命令介面認證物件 (包含每個帳戶的帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="da442-123">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="da442-124">當您呼叫 Test-CsWebAppAnonymous 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="da442-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="da442-125">如需詳細資訊，請參閱 Test-CsWebAppAnonymous Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="da442-125">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="da442-126">請注意，Test-CsWebAppAnonymous 已過時，無法在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="da442-126">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="da442-127">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="da442-127">Determining success or failure</span></span>

<span data-ttu-id="da442-128">如果 Test-CsWebAppAnonymous 可以將匿名使用者加入其會議，此 Cmdlet 將會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="da442-128">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="da442-129">目標 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="da442-129">Target Fqdn :</span></span>

<span data-ttu-id="da442-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="da442-130">Result : Success</span></span>

<span data-ttu-id="da442-131">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="da442-131">Latency : 00:00:00</span></span>

<span data-ttu-id="da442-132">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="da442-132">Error Message :</span></span>

<span data-ttu-id="da442-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="da442-133">Diagnosis :</span></span>

<span data-ttu-id="da442-134">如果匿名使用者無法加入必要的會議，則測試結果會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="da442-134">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="da442-135">通常 Test-CsWebAppAnonymous 也會報告詳細的錯誤訊息和診斷：</span><span class="sxs-lookup"><span data-stu-id="da442-135">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="da442-136">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="da442-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="da442-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="da442-137">Result : Failure</span></span>

<span data-ttu-id="da442-138">延遲：00：00：05.9746266</span><span class="sxs-lookup"><span data-stu-id="da442-138">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="da442-139">錯誤訊息：沒有為 Web-Ticket 服務接收任何回應</span><span class="sxs-lookup"><span data-stu-id="da442-139">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="da442-140">診斷：未授權用戶端的 HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="da442-140">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="da442-141">驗證架構「Ntlm」。</span><span class="sxs-lookup"><span data-stu-id="da442-141">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="da442-142">驗證</span><span class="sxs-lookup"><span data-stu-id="da442-142">The authentication</span></span>

<span data-ttu-id="da442-143">從伺服器收到的標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="da442-143">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="da442-144">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="da442-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="da442-145">Test-CsWebAppAnonymous 失敗通常會圍繞使用者驗證錯誤進行旋轉：您必須使用有效的使用者帳戶執行測試，即使此 Cmdlet 檢查匿名使用者連線到 Lync Server 的能力也是一樣。</span><span class="sxs-lookup"><span data-stu-id="da442-145">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="da442-146">如果 Test-CsWebAppAnonymous 失敗，您應該確認指定的使用者是否有有效的 Lync Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="da442-146">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="da442-147">您可以使用類似下列的命令，來取得 Lync Server 帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="da442-147">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="da442-148">如果 Enabled 屬性不等於 True 或如果命令失敗，則表示使用者沒有有效的 Lync 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="da442-148">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="da442-149">您也應該確認執行 Cmdlet 時所提供的密碼是有效的密碼。</span><span class="sxs-lookup"><span data-stu-id="da442-149">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="da442-150">Office Web Apps Server 的設定問題也會導致 Test-CsWebAppAnonymous 失敗。當您收到下列診斷時，通常會發生這種情況：</span><span class="sxs-lookup"><span data-stu-id="da442-150">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="da442-151">以用戶端驗證架構 ' Ntlm ' 未授權的 HTTP 要求。</span><span class="sxs-lookup"><span data-stu-id="da442-151">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="da442-152">從伺服器接收的驗證標頭為「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="da442-152">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="da442-153">如需診斷及解決 Office Web Apps Server 問題的詳細資訊，請參閱博客文章中的 [Office Web Apps server 2013-電腦永不報告為狀況不良](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)。</span><span class="sxs-lookup"><span data-stu-id="da442-153">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

