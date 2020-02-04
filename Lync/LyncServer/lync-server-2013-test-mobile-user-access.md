---
title: Lync Server 2013：測試行動使用者存取權
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
ms.openlocfilehash: 628fd3aae4f66316627176c3af025eb63202bafb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="0f477-102">在 Lync Server 2013 中測試行動使用者存取權</span><span class="sxs-lookup"><span data-stu-id="0f477-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f477-103">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="0f477-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f477-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="0f477-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0f477-105">次</span><span class="sxs-lookup"><span data-stu-id="0f477-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f477-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="0f477-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0f477-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f477-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f477-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="0f477-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0f477-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0f477-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0f477-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsMcxConference Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="0f477-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="0f477-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0f477-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0f477-112">說明</span><span class="sxs-lookup"><span data-stu-id="0f477-112">Description</span></span>

<span data-ttu-id="0f477-113">行動裝置服務可讓行動裝置使用者執行如下動作：</span><span class="sxs-lookup"><span data-stu-id="0f477-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="0f477-114">Exchange 立即訊息和目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="0f477-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="0f477-115">在內部儲存及檢索語音信箱，而不是使用其無線提供者。</span><span class="sxs-lookup"><span data-stu-id="0f477-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="0f477-116">利用 Lync 伺服器的功能，例如透過工作和撥出式會議進行通話。</span><span class="sxs-lookup"><span data-stu-id="0f477-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="0f477-117">CsMcxConference Cmdlet 能快速且輕鬆地確認使用者可以使用行動裝置加入和參與 Lync Server 會議。</span><span class="sxs-lookup"><span data-stu-id="0f477-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0f477-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="0f477-118">Running the test</span></span>

<span data-ttu-id="0f477-119">若要執行這項檢查，您必須為每個帳戶建立三個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="0f477-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="0f477-120">您必須在呼叫 Test CsMcxConference 時包含這些認證物件和兩個帳戶的 SIP 位址，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="0f477-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="0f477-121">如需詳細資訊，請參閱[Test CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="0f477-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0f477-122">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="0f477-122">Determining success or failure</span></span>

<span data-ttu-id="0f477-123">如果檢查成功，測試 CsMcxConference 會報告成功的測試結果：</span><span class="sxs-lookup"><span data-stu-id="0f477-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="0f477-124">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0f477-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0f477-125">目標 Uri：http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="0f477-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="0f477-126">結果：成功</span><span class="sxs-lookup"><span data-stu-id="0f477-126">Result : Success</span></span>

<span data-ttu-id="0f477-127">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="0f477-127">Latency : 00:00:00</span></span>

<span data-ttu-id="0f477-128">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0f477-128">Error Message :</span></span>

<span data-ttu-id="0f477-129">自檢</span><span class="sxs-lookup"><span data-stu-id="0f477-129">Diagnosis :</span></span>

<span data-ttu-id="0f477-130">如果檢查失敗，CsMcxConference 將會報告失敗的測試結果。</span><span class="sxs-lookup"><span data-stu-id="0f477-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="0f477-131">此測試結果通常會伴隨詳細的錯誤訊息和診斷。</span><span class="sxs-lookup"><span data-stu-id="0f477-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="0f477-132">例如：</span><span class="sxs-lookup"><span data-stu-id="0f477-132">For example:</span></span>

<span data-ttu-id="0f477-133">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0f477-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0f477-134">目標 Uri：https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="0f477-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="0f477-135">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="0f477-135">Result : Failure</span></span>

<span data-ttu-id="0f477-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="0f477-136">Latency : 00:00:00</span></span>

<span data-ttu-id="0f477-137">錯誤訊息：網路票證服務沒有收到任何回應。</span><span class="sxs-lookup"><span data-stu-id="0f477-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="0f477-138">內部例外狀況： HHTP 要求未獲用戶端授權</span><span class="sxs-lookup"><span data-stu-id="0f477-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="0f477-139">協商配置 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="0f477-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="0f477-140">收到的驗證標頭</span><span class="sxs-lookup"><span data-stu-id="0f477-140">The authentication header received</span></span>

<span data-ttu-id="0f477-141">從伺服器為「協商」。</span><span class="sxs-lookup"><span data-stu-id="0f477-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="0f477-142">內部例外狀況：遠端伺服器傳回錯誤：（401）</span><span class="sxs-lookup"><span data-stu-id="0f477-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="0f477-143">取消.</span><span class="sxs-lookup"><span data-stu-id="0f477-143">Unauthorized.</span></span>

<span data-ttu-id="0f477-144">自檢</span><span class="sxs-lookup"><span data-stu-id="0f477-144">Diagnosis :</span></span>

<span data-ttu-id="0f477-145">內部診斷： X-MS-伺服器-Fqdb： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0f477-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0f477-146">緩存控制：私人</span><span class="sxs-lookup"><span data-stu-id="0f477-146">Cache-Control : private</span></span>

<span data-ttu-id="0f477-147">內容類型：文字/html;字元集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="0f477-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="0f477-148">伺服器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="0f477-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="0f477-149">WWW-驗證：協商，NTLM</span><span class="sxs-lookup"><span data-stu-id="0f477-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="0f477-150">X-電源： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0f477-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="0f477-151">X 內容-類型選項： nosniff</span><span class="sxs-lookup"><span data-stu-id="0f477-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="0f477-152">日期：週三，28年5月 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="0f477-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="0f477-153">內容-長度：6305</span><span class="sxs-lookup"><span data-stu-id="0f477-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0f477-154">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="0f477-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="0f477-155">如果測試 CsMcxConference 失敗，您應該先確認行動服務正在執行且可以存取。</span><span class="sxs-lookup"><span data-stu-id="0f477-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="0f477-156">您可以使用網頁瀏覽器來驗證您的 Lync 伺服器池行動服務 URL 是否可存取。</span><span class="sxs-lookup"><span data-stu-id="0f477-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="0f477-157">例如，這個命令會驗證 [pool atl-cs-001.litwareinc.com] 的 URL：</span><span class="sxs-lookup"><span data-stu-id="0f477-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="0f477-158">如果您可以存取行動服務，請確認您的測試使用者擁有有效的 Lync 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="0f477-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="0f477-159">您可以使用類似以下的命令來取得帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="0f477-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="0f477-160">如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。您也應該確認每個使用者帳戶都已啟用行動。</span><span class="sxs-lookup"><span data-stu-id="0f477-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="0f477-161">若要這樣做，請先決定指派給帳戶的行動原則：</span><span class="sxs-lookup"><span data-stu-id="0f477-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="0f477-162">在您知道原則名稱之後，請使用 CsMobilityPolicy Cmdlet，確認有問題的原則（例如，RedmondMobilityPolicy）已將 EnableMobility 屬性設為 True：</span><span class="sxs-lookup"><span data-stu-id="0f477-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="0f477-163">如果您在執行測試 CsMcxConference 時收到「驗證頭」錯誤訊息，這通常表示您尚未指定有效的使用者帳戶，請確認使用者名稱和密碼，然後再次嘗試測試。</span><span class="sxs-lookup"><span data-stu-id="0f477-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="0f477-164">如果您確信使用者帳戶有效，請使用 CsWebServiceConfiguration Cmdlet，然後檢查 UseWindowsAuth 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="0f477-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="0f477-165">這會告訴您組織中已啟用哪些驗證方法。</span><span class="sxs-lookup"><span data-stu-id="0f477-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="0f477-166">如需有關如何排查行動服務問題的其他秘訣，請參閱博客文章[疑難排解外部 Lync 行動連線問題](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0f477-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

