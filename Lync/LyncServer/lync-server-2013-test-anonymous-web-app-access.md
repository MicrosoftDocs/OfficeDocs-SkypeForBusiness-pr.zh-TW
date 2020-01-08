---
title: Lync Server 2013：測試匿名 Web 應用程式存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 701954a872645e80d6aac82cab1fbf5745ad6984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="fd67a-102">在 Lync Server 2013 中測試匿名 Web 應用程式存取權</span><span class="sxs-lookup"><span data-stu-id="fd67a-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd67a-103">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="fd67a-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd67a-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="fd67a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fd67a-105">次</span><span class="sxs-lookup"><span data-stu-id="fd67a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd67a-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="fd67a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fd67a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd67a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd67a-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="fd67a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fd67a-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fd67a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fd67a-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsWebAppAnonymous Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="fd67a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="fd67a-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fd67a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fd67a-112">描述</span><span class="sxs-lookup"><span data-stu-id="fd67a-112">Description</span></span>

<span data-ttu-id="fd67a-113">Test CsWebAppAnonymous Cmdlet 會驗證匿名使用者是否可以使用 Lync Web App 加入 Lync Server 會議。</span><span class="sxs-lookup"><span data-stu-id="fd67a-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="fd67a-114">當您執行 Cmdlet 時，測試 CsWebAppAnonymous 會與 Web 票證服務聯絡，以取得匿名使用者的 Web 票證。</span><span class="sxs-lookup"><span data-stu-id="fd67a-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="fd67a-115">如果 Cmdlet 成功取得此票證，測試 CsWebAppAnonymous 就會與 Lync Server 取得聯繫，並嘗試建立獨立的會議以進行立即訊息、應用程式共用及資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="fd67a-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="fd67a-116">請注意，測試 CsWebAppAnonymous 只會驗證用來建立這些會議的 Api 和連線。</span><span class="sxs-lookup"><span data-stu-id="fd67a-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="fd67a-117">這個 Cmdlet 不會實際建立並執行任何會議。</span><span class="sxs-lookup"><span data-stu-id="fd67a-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fd67a-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="fd67a-118">Running the test</span></span>

<span data-ttu-id="fd67a-119">CsWebAppAnonymous Cmdlet 可以使用一組預先配置的測試帳戶或任何兩個已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="fd67a-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="fd67a-120">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="fd67a-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="fd67a-121">例如：</span><span class="sxs-lookup"><span data-stu-id="fd67a-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="fd67a-122">若要使用實際的使用者帳戶執行此檢查，您必須為每個帳戶建立兩個 Lync Server 管理命令介面身分憑證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="fd67a-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="fd67a-123">當您呼叫 Test CsWebAppAnonymous 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="fd67a-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="fd67a-124">如需詳細資訊，請參閱 Test CsWebAppAnonymous Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="fd67a-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="fd67a-125">請注意，CsWebAppAnonymous 已過時，無法在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="fd67a-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fd67a-126">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="fd67a-126">Determining success or failure</span></span>

<span data-ttu-id="fd67a-127">如果測試 CsWebAppAnonymous 可以將匿名使用者加入其會議，此 Cmdlet 會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="fd67a-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="fd67a-128">目標 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="fd67a-128">Target Fqdn :</span></span>

<span data-ttu-id="fd67a-129">結果：成功</span><span class="sxs-lookup"><span data-stu-id="fd67a-129">Result : Success</span></span>

<span data-ttu-id="fd67a-130">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="fd67a-130">Latency : 00:00:00</span></span>

<span data-ttu-id="fd67a-131">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="fd67a-131">Error Message :</span></span>

<span data-ttu-id="fd67a-132">自檢</span><span class="sxs-lookup"><span data-stu-id="fd67a-132">Diagnosis :</span></span>

<span data-ttu-id="fd67a-133">如果匿名使用者無法加入必要的會議，則測試結果會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="fd67a-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="fd67a-134">通常測試 CsWebAppAnonymous 也會傳回詳細的錯誤訊息及診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="fd67a-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="fd67a-135">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fd67a-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fd67a-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="fd67a-136">Result : Failure</span></span>

<span data-ttu-id="fd67a-137">延隔時間：00：00：05.9746266</span><span class="sxs-lookup"><span data-stu-id="fd67a-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="fd67a-138">錯誤訊息：沒有收到 Web 票證服務的回應</span><span class="sxs-lookup"><span data-stu-id="fd67a-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="fd67a-139">診斷： HTTP 要求未經用戶端的授權</span><span class="sxs-lookup"><span data-stu-id="fd67a-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="fd67a-140">驗證配置 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="fd67a-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="fd67a-141">驗證</span><span class="sxs-lookup"><span data-stu-id="fd67a-141">The authentication</span></span>

<span data-ttu-id="fd67a-142">從伺服器接收到的標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="fd67a-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fd67a-143">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="fd67a-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="fd67a-144">測試 CsWebAppAnonymous 的失敗通常會繞過使用者驗證錯誤：您必須使用有效的使用者帳戶來執行測試，即使 Cmdlet 要檢查匿名使用者連線至 Lync Server 的能力。</span><span class="sxs-lookup"><span data-stu-id="fd67a-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="fd67a-145">如果測試 CsWebAppAnonymous 失敗，您應該確認指定的使用者擁有有效的 Lync Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd67a-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="fd67a-146">您可以使用類似以下的命令來取得 Lync Server 帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="fd67a-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="fd67a-147">如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd67a-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="fd67a-148">您也應該確認執行 Cmdlet 時所提供的密碼是有效的密碼。</span><span class="sxs-lookup"><span data-stu-id="fd67a-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="fd67a-149">Office Web Apps Server 的設定問題也可能會導致測試 CsWebAppAnonymous 失敗;如果您收到下列診斷，通常會發生這種情況：</span><span class="sxs-lookup"><span data-stu-id="fd67a-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="fd67a-150">HTTP 要求未經用戶端驗證配置 "Ntlm" 的授權。</span><span class="sxs-lookup"><span data-stu-id="fd67a-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="fd67a-151">從伺服器接收到的驗證標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="fd67a-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="fd67a-152">如需診斷及解決 Office Web Apps 伺服器問題的詳細資訊，請參閱博客文章[Office Web Apps server 2013-電腦總是報告為不正常](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)。</span><span class="sxs-lookup"><span data-stu-id="fd67a-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

