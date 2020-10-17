---
title: Lync Server 2013：測試行動使用者存取
description: Lync Server 2013：測試行動使用者存取。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541869"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="7cedf-103">在 Lync Server 2013 中測試行動使用者存取</span><span class="sxs-lookup"><span data-stu-id="7cedf-103">Test mobile user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cedf-104">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="7cedf-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cedf-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="7cedf-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7cedf-106">每月</span><span class="sxs-lookup"><span data-stu-id="7cedf-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cedf-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="7cedf-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7cedf-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cedf-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cedf-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="7cedf-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7cedf-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7cedf-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7cedf-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsMcxConference Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7cedf-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="7cedf-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7cedf-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7cedf-113">描述</span><span class="sxs-lookup"><span data-stu-id="7cedf-113">Description</span></span>

<span data-ttu-id="7cedf-114">行動服務可讓行動裝置使用者執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="7cedf-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="7cedf-115">Exchange 立即訊息和目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="7cedf-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="7cedf-116">內部儲存及取回語音信箱，而不是與其無線提供者。</span><span class="sxs-lookup"><span data-stu-id="7cedf-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="7cedf-117">利用 Lync Server 功能（例如透過工作和撥出會議進行通話）。</span><span class="sxs-lookup"><span data-stu-id="7cedf-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="7cedf-118">Test-CsMcxConference Cmdlet 提供一種快速快捷的方式，可驗證使用者是否可以使用行動裝置加入和參加 Lync Server 會議。</span><span class="sxs-lookup"><span data-stu-id="7cedf-118">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7cedf-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="7cedf-119">Running the test</span></span>

<span data-ttu-id="7cedf-120">若要執行這項檢查，您必須建立三個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="7cedf-120">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7cedf-121">接下來，您必須在呼叫 Test-CsMcxConference 時，包含這兩個帳戶的認證物件和 SIP 位址，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="7cedf-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="7cedf-122">如需詳細資訊，請參閱 [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="7cedf-122">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7cedf-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="7cedf-123">Determining success or failure</span></span>

<span data-ttu-id="7cedf-124">如果檢查成功，Test-CsMcxConference 將會報告成功的測試結果：</span><span class="sxs-lookup"><span data-stu-id="7cedf-124">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="7cedf-125">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7cedf-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7cedf-126">目標 Uri： http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="7cedf-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="7cedf-127">結果：成功</span><span class="sxs-lookup"><span data-stu-id="7cedf-127">Result : Success</span></span>

<span data-ttu-id="7cedf-128">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="7cedf-128">Latency : 00:00:00</span></span>

<span data-ttu-id="7cedf-129">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="7cedf-129">Error Message :</span></span>

<span data-ttu-id="7cedf-130">診斷：</span><span class="sxs-lookup"><span data-stu-id="7cedf-130">Diagnosis :</span></span>

<span data-ttu-id="7cedf-131">如果檢查失敗 Test-CsMcxConference 會報告失敗的測試結果。</span><span class="sxs-lookup"><span data-stu-id="7cedf-131">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="7cedf-132">此測試結果通常會附帶詳細的錯誤訊息和診斷。</span><span class="sxs-lookup"><span data-stu-id="7cedf-132">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="7cedf-133">例如：</span><span class="sxs-lookup"><span data-stu-id="7cedf-133">For example:</span></span>

<span data-ttu-id="7cedf-134">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7cedf-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7cedf-135">目標 Uri： https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="7cedf-135">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="7cedf-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="7cedf-136">Result : Failure</span></span>

<span data-ttu-id="7cedf-137">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="7cedf-137">Latency : 00:00:00</span></span>

<span data-ttu-id="7cedf-138">錯誤訊息：沒有為 Web-Ticket 服務接收任何回應。</span><span class="sxs-lookup"><span data-stu-id="7cedf-138">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="7cedf-139">內部例外狀況： HHTP 要求未經用戶端授權</span><span class="sxs-lookup"><span data-stu-id="7cedf-139">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="7cedf-140">協商架構「Ntlm」。</span><span class="sxs-lookup"><span data-stu-id="7cedf-140">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="7cedf-141">收到的驗證標頭</span><span class="sxs-lookup"><span data-stu-id="7cedf-141">The authentication header received</span></span>

<span data-ttu-id="7cedf-142">從伺服器「協商」。</span><span class="sxs-lookup"><span data-stu-id="7cedf-142">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="7cedf-143">內部例外狀況：遠端伺服器傳回錯誤： (401) </span><span class="sxs-lookup"><span data-stu-id="7cedf-143">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="7cedf-144">未經 授權。</span><span class="sxs-lookup"><span data-stu-id="7cedf-144">Unauthorized.</span></span>

<span data-ttu-id="7cedf-145">診斷：</span><span class="sxs-lookup"><span data-stu-id="7cedf-145">Diagnosis :</span></span>

<span data-ttu-id="7cedf-146">內部診斷： X-毫秒-伺服器-Fqdb： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7cedf-146">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7cedf-147">Cache-Control： private</span><span class="sxs-lookup"><span data-stu-id="7cedf-147">Cache-Control : private</span></span>

<span data-ttu-id="7cedf-148">Content-Type：文字/html;字元集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="7cedf-148">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="7cedf-149">伺服器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="7cedf-149">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="7cedf-150">WWW-Authenticate：協商、NTLM</span><span class="sxs-lookup"><span data-stu-id="7cedf-150">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="7cedf-151">X-供電方式： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7cedf-151">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="7cedf-152">X-Content-Type-選項： nosniff</span><span class="sxs-lookup"><span data-stu-id="7cedf-152">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="7cedf-153">日期：星期三，28月 2014 19:22:19 （格林威治）</span><span class="sxs-lookup"><span data-stu-id="7cedf-153">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="7cedf-154">內容長度：6305</span><span class="sxs-lookup"><span data-stu-id="7cedf-154">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7cedf-155">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="7cedf-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="7cedf-156">如果 Test-CsMcxConference 失敗，您應該先驗證行動性服務是否正在執行且可以存取。</span><span class="sxs-lookup"><span data-stu-id="7cedf-156">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="7cedf-157">可以使用網頁瀏覽器來驗證 Lync Server 集區的行動服務 URL 是否可以存取。</span><span class="sxs-lookup"><span data-stu-id="7cedf-157">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="7cedf-158">例如，下列命令會驗證集區 atl-cs-001.litwareinc.com 的 URL：</span><span class="sxs-lookup"><span data-stu-id="7cedf-158">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="7cedf-159">若可以存取行動服務，您應該確認測試使用者具備有效的 Lync 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="7cedf-159">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="7cedf-160">您可以使用類似下列的命令來取得帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="7cedf-160">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="7cedf-161">如果 Enabled 屬性不等於 True 或如果命令失敗，則表示使用者沒有有效的 Lync 伺服器帳戶。您也應該確認每個使用者帳戶都已啟用行動性。</span><span class="sxs-lookup"><span data-stu-id="7cedf-161">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="7cedf-162">若要這麼做，請先決定指派給該帳戶的行動原則：</span><span class="sxs-lookup"><span data-stu-id="7cedf-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="7cedf-163">在您知道原則名稱後，請使用 Get-CsMobilityPolicy 指令程式確認問題原則 (例如，RedmondMobilityPolicy) 具有 EnableMobility 屬性設定為 True：</span><span class="sxs-lookup"><span data-stu-id="7cedf-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="7cedf-164">如果您在執行 Test-CsMcxConference 通常表示您未指定有效的使用者帳戶，請確認使用者名稱和密碼，然後再試一次，您會收到「驗證標頭」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7cedf-164">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="7cedf-165">如果您確信使用者帳戶是有效的，請使用 Get-CsWebServiceConfiguration Cmdlet，並檢查 UseWindowsAuth 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="7cedf-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="7cedf-166">這會告訴您您的組織中已啟用哪種驗證方法。</span><span class="sxs-lookup"><span data-stu-id="7cedf-166">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="7cedf-167">如需如何疑難排解行動性服務的更多秘訣，請參閱博客文章 [疑難排解外部 Lync 行動連線問題逐步](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)執行。</span><span class="sxs-lookup"><span data-stu-id="7cedf-167">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

