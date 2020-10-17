---
title: Lync Server 2013：測試行動使用者對 exchange 立即訊息的能力
description: Lync Server 2013：測試行動使用者對 exchange 立即訊息的能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558289"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="72732-103">在 Lync Server 2013 中測試行動使用者的 exchange 立即訊息能力</span><span class="sxs-lookup"><span data-stu-id="72732-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72732-104">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="72732-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72732-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="72732-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="72732-106">每月</span><span class="sxs-lookup"><span data-stu-id="72732-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72732-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="72732-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="72732-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72732-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72732-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="72732-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="72732-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="72732-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="72732-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsMcxP2PIM Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="72732-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="72732-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="72732-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="72732-113">描述</span><span class="sxs-lookup"><span data-stu-id="72732-113">Description</span></span>

<span data-ttu-id="72732-114">行動服務可讓行動裝置使用者執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="72732-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="72732-115">Exchange 立即訊息和目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="72732-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="72732-116">內部儲存及取回語音信箱，而不是與其無線提供者。</span><span class="sxs-lookup"><span data-stu-id="72732-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="72732-117">利用 Lync Server 功能（例如透過工作和撥出會議進行通話）。</span><span class="sxs-lookup"><span data-stu-id="72732-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="72732-118">Test-CsMxcP2PIM Cmdlet 提供一種快速快捷的方式，可驗證使用者是否可以使用行動服務來交換立即訊息。</span><span class="sxs-lookup"><span data-stu-id="72732-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="72732-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="72732-119">Running the test</span></span>

<span data-ttu-id="72732-120">若要執行此測試，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="72732-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="72732-121">當您呼叫 Test-CsMcxP2PIM 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="72732-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="72732-122">如需詳細資訊，請參閱 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="72732-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="72732-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="72732-123">Determining success or failure</span></span>

<span data-ttu-id="72732-124">如果兩個測試使用者可以使用行動服務來交換立即訊息，Test-CsMcxP2PIM 會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="72732-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="72732-125">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72732-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72732-126">目標 Uri： http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="72732-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="72732-127">結果：成功</span><span class="sxs-lookup"><span data-stu-id="72732-127">Result : Success</span></span>

<span data-ttu-id="72732-128">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="72732-128">Latency : 00:00:00</span></span>

<span data-ttu-id="72732-129">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="72732-129">Error Message :</span></span>

<span data-ttu-id="72732-130">診斷：</span><span class="sxs-lookup"><span data-stu-id="72732-130">Diagnosis :</span></span>

<span data-ttu-id="72732-131">如果測試失敗，則結果會設定為 [失敗]，並且會顯示詳細的錯誤訊息和診斷：</span><span class="sxs-lookup"><span data-stu-id="72732-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="72732-132">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72732-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="72732-133">目標 Uri： https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="72732-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="72732-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="72732-134">Result : Failure</span></span>

<span data-ttu-id="72732-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="72732-135">Latency : 00:00:00</span></span>

<span data-ttu-id="72732-136">錯誤訊息：沒有為 Web-Ticket 服務接收任何回應。</span><span class="sxs-lookup"><span data-stu-id="72732-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="72732-137">內部例外狀況： HHTP 要求未經授權使用</span><span class="sxs-lookup"><span data-stu-id="72732-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="72732-138">用戶端協商架構「Ntlm」。</span><span class="sxs-lookup"><span data-stu-id="72732-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="72732-139">驗證</span><span class="sxs-lookup"><span data-stu-id="72732-139">The authentication</span></span>

<span data-ttu-id="72732-140">從伺服器收到的標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="72732-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="72732-141">內部例外狀況：遠端伺服器傳回錯誤：</span><span class="sxs-lookup"><span data-stu-id="72732-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="72732-142"> (401) 未經授權。</span><span class="sxs-lookup"><span data-stu-id="72732-142">(401) Unauthorized.</span></span>

<span data-ttu-id="72732-143">診斷：</span><span class="sxs-lookup"><span data-stu-id="72732-143">Diagnosis :</span></span>

<span data-ttu-id="72732-144">內部診斷： X-MS-Fqdb： atl-cs-</span><span class="sxs-lookup"><span data-stu-id="72732-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="72732-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="72732-145">001.litwareinc.com</span></span>

<span data-ttu-id="72732-146">Cache-Control： private</span><span class="sxs-lookup"><span data-stu-id="72732-146">Cache-Control : private</span></span>

<span data-ttu-id="72732-147">Content-Type：文字/html;字元集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="72732-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="72732-148">伺服器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="72732-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="72732-149">WWW-Authenticate：協商、NTLM</span><span class="sxs-lookup"><span data-stu-id="72732-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="72732-150">X-供電方式： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72732-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="72732-151">X-Content-Type-選項： nosniff</span><span class="sxs-lookup"><span data-stu-id="72732-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="72732-152">日期：星期三，28月 2014 19:16:05 （格林威治）</span><span class="sxs-lookup"><span data-stu-id="72732-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="72732-153">內容長度：6305</span><span class="sxs-lookup"><span data-stu-id="72732-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="72732-154">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="72732-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="72732-155">如果 Test-CsMcxP2PIM 失敗第一個步驟，應驗證行動性服務是否已啟動並在運作中。</span><span class="sxs-lookup"><span data-stu-id="72732-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="72732-156">可以使用網頁瀏覽器來驗證 Lync Server 集區的行動服務 URL 是否可以存取。</span><span class="sxs-lookup"><span data-stu-id="72732-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="72732-157">例如，下列命令會驗證集區 atl-cs-001.litwareinc.com 的 URL：</span><span class="sxs-lookup"><span data-stu-id="72732-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="72732-158">若行動服務似乎已執行，請確認您的兩個測試使用者具有有效的 Lync 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="72732-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="72732-159">您可以使用類似下列的命令來取得帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="72732-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="72732-160">如果 Enabled 屬性不等於 True 或如果命令失敗，則表示使用者沒有有效的 Lync 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="72732-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="72732-161">您也應該確認使用者已啟用行動性。</span><span class="sxs-lookup"><span data-stu-id="72732-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="72732-162">若要這麼做，請先決定指派給該帳戶的行動原則：</span><span class="sxs-lookup"><span data-stu-id="72732-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="72732-163">在您知道原則名稱後，請使用 Get-CsMobilityPolicy 指令程式確認問題原則 (例如，RedmondMobilityPolicy) 具有 EnableMobility 屬性設定為 True：</span><span class="sxs-lookup"><span data-stu-id="72732-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="72732-164">如果您收到錯誤訊息及驗證標頭，這通常表示您未指定有效的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="72732-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="72732-165">請確認使用者名稱和密碼，然後再試一次測試。</span><span class="sxs-lookup"><span data-stu-id="72732-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="72732-166">如果您確信使用者帳戶是有效的，請使用 Get-CsWebServiceConfiguration Cmdlet，並檢查 UseWindowsAuth 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="72732-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="72732-167">這會告訴您您的組織中已啟用哪種驗證方法。如需如何疑難排解行動性服務的更多秘訣，請參閱博客文章 [疑難排解外部 Lync 行動連線問題逐步](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)執行。</span><span class="sxs-lookup"><span data-stu-id="72732-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

