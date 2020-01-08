---
title: Lync Server 2013：測試行動使用者的 exchange 立即訊息功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="db3a7-102">在 Lync Server 2013 中測試行動使用者的 exchange 立即訊息功能</span><span class="sxs-lookup"><span data-stu-id="db3a7-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db3a7-103">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="db3a7-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db3a7-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="db3a7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="db3a7-105">次</span><span class="sxs-lookup"><span data-stu-id="db3a7-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db3a7-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="db3a7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="db3a7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db3a7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db3a7-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="db3a7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="db3a7-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="db3a7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="db3a7-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsMcxP2PIM Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="db3a7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="db3a7-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="db3a7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="db3a7-112">描述</span><span class="sxs-lookup"><span data-stu-id="db3a7-112">Description</span></span>

<span data-ttu-id="db3a7-113">行動裝置服務可讓行動裝置使用者執行如下動作：</span><span class="sxs-lookup"><span data-stu-id="db3a7-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="db3a7-114">Exchange 立即訊息和目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="db3a7-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="db3a7-115">在內部儲存及檢索語音信箱，而不是使用其無線提供者。</span><span class="sxs-lookup"><span data-stu-id="db3a7-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="db3a7-116">利用 Lync 伺服器的功能，例如透過工作和撥出式會議進行通話。</span><span class="sxs-lookup"><span data-stu-id="db3a7-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="db3a7-117">CsMxcP2PIM Cmdlet 能快速且輕鬆地確認使用者可以使用行動服務來交換立即訊息。</span><span class="sxs-lookup"><span data-stu-id="db3a7-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="db3a7-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="db3a7-118">Running the test</span></span>

<span data-ttu-id="db3a7-119">若要執行此測試，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="db3a7-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="db3a7-120">當您呼叫 Test CsMcxP2PIM 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="db3a7-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="db3a7-121">如需詳細資訊，請參閱[Test CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="db3a7-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="db3a7-122">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="db3a7-122">Determining success or failure</span></span>

<span data-ttu-id="db3a7-123">如果兩個測試使用者可以使用行動服務來交換立即訊息，則 CsMcxP2PIM 會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="db3a7-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="db3a7-124">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db3a7-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db3a7-125">目標 Uri：http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="db3a7-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="db3a7-126">結果：成功</span><span class="sxs-lookup"><span data-stu-id="db3a7-126">Result : Success</span></span>

<span data-ttu-id="db3a7-127">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="db3a7-127">Latency : 00:00:00</span></span>

<span data-ttu-id="db3a7-128">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="db3a7-128">Error Message :</span></span>

<span data-ttu-id="db3a7-129">自檢</span><span class="sxs-lookup"><span data-stu-id="db3a7-129">Diagnosis :</span></span>

<span data-ttu-id="db3a7-130">如果測試失敗，則會將結果設定為 [失敗]，並會顯示詳細的錯誤訊息和診斷：</span><span class="sxs-lookup"><span data-stu-id="db3a7-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="db3a7-131">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db3a7-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="db3a7-132">目標 Uri：https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="db3a7-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="db3a7-133">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="db3a7-133">Result : Failure</span></span>

<span data-ttu-id="db3a7-134">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="db3a7-134">Latency : 00:00:00</span></span>

<span data-ttu-id="db3a7-135">錯誤訊息：網路票證服務沒有收到任何回應。</span><span class="sxs-lookup"><span data-stu-id="db3a7-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="db3a7-136">內部例外狀況：未授權的 HHTP 要求</span><span class="sxs-lookup"><span data-stu-id="db3a7-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="db3a7-137">用戶端協商配置 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="db3a7-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="db3a7-138">驗證</span><span class="sxs-lookup"><span data-stu-id="db3a7-138">The authentication</span></span>

<span data-ttu-id="db3a7-139">從伺服器接收到的標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="db3a7-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="db3a7-140">內部例外狀況：遠端伺服器傳回錯誤：</span><span class="sxs-lookup"><span data-stu-id="db3a7-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="db3a7-141">（401）未授權。</span><span class="sxs-lookup"><span data-stu-id="db3a7-141">(401) Unauthorized.</span></span>

<span data-ttu-id="db3a7-142">自檢</span><span class="sxs-lookup"><span data-stu-id="db3a7-142">Diagnosis :</span></span>

<span data-ttu-id="db3a7-143">內部診斷： X MS-伺服器-Fqdb： atl-cs-</span><span class="sxs-lookup"><span data-stu-id="db3a7-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="db3a7-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="db3a7-144">001.litwareinc.com</span></span>

<span data-ttu-id="db3a7-145">緩存控制：私人</span><span class="sxs-lookup"><span data-stu-id="db3a7-145">Cache-Control : private</span></span>

<span data-ttu-id="db3a7-146">內容類型：文字/html;字元集 = utf-8。</span><span class="sxs-lookup"><span data-stu-id="db3a7-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="db3a7-147">伺服器： Microsoft-IIS/8。5</span><span class="sxs-lookup"><span data-stu-id="db3a7-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="db3a7-148">WWW-驗證：協商，NTLM</span><span class="sxs-lookup"><span data-stu-id="db3a7-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="db3a7-149">X-電源： ASP.NET</span><span class="sxs-lookup"><span data-stu-id="db3a7-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="db3a7-150">X 內容-類型選項： nosniff</span><span class="sxs-lookup"><span data-stu-id="db3a7-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="db3a7-151">日期：週三，28年5月 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="db3a7-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="db3a7-152">內容-長度：6305</span><span class="sxs-lookup"><span data-stu-id="db3a7-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="db3a7-153">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="db3a7-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="db3a7-154">如果 CsMcxP2PIM 測試失敗，您的第一個步驟應該是確認行動服務已啟動且正在執行。</span><span class="sxs-lookup"><span data-stu-id="db3a7-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="db3a7-155">您可以使用網頁瀏覽器來驗證您的 Lync 伺服器池行動服務 URL 是否可存取。</span><span class="sxs-lookup"><span data-stu-id="db3a7-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="db3a7-156">例如，這個命令會驗證 [pool atl-cs-001.litwareinc.com] 的 URL：</span><span class="sxs-lookup"><span data-stu-id="db3a7-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="db3a7-157">如果行動服務似乎正在執行，請確認您的兩個測試使用者擁有有效的 Lync 伺服器帳戶。</span><span class="sxs-lookup"><span data-stu-id="db3a7-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="db3a7-158">您可以使用類似以下的命令來取得帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="db3a7-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="db3a7-159">如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="db3a7-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="db3a7-160">您也應該確認使用者已啟用行動性。</span><span class="sxs-lookup"><span data-stu-id="db3a7-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="db3a7-161">若要這樣做，請先決定指派給帳戶的行動原則：</span><span class="sxs-lookup"><span data-stu-id="db3a7-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="db3a7-162">在您知道原則名稱之後，請使用 CsMobilityPolicy Cmdlet，確認有問題的原則（例如，RedmondMobilityPolicy）已將 EnableMobility 屬性設為 True：</span><span class="sxs-lookup"><span data-stu-id="db3a7-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="db3a7-163">如果您收到含驗證標頭的錯誤訊息，這通常表示您尚未指定有效的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="db3a7-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="db3a7-164">確認使用者名稱和密碼，然後再次嘗試測試。</span><span class="sxs-lookup"><span data-stu-id="db3a7-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="db3a7-165">如果您確信使用者帳戶有效，請使用 CsWebServiceConfiguration Cmdlet，然後檢查 UseWindowsAuth 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="db3a7-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="db3a7-166">這會告訴您組織中已啟用哪些驗證方法。如需有關如何排查行動服務問題的其他秘訣，請參閱博客文章[疑難排解外部 Lync 行動連線問題](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)。</span><span class="sxs-lookup"><span data-stu-id="db3a7-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

