---
title: Lync Server 2013： 測試 Web 應用程式的匿名存取
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
ms.openlocfilehash: 9df6a040e71b0dfe82a52cf519357d058b78a1d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="b47fe-102">測試 Lync Server 2013 中的 Web 應用程式的匿名存取</span><span class="sxs-lookup"><span data-stu-id="b47fe-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b47fe-103">_**上次修改主題：** 2014年-06-07_</span><span class="sxs-lookup"><span data-stu-id="b47fe-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b47fe-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="b47fe-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b47fe-105">每月</span><span class="sxs-lookup"><span data-stu-id="b47fe-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b47fe-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="b47fe-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b47fe-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b47fe-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b47fe-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="b47fe-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b47fe-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b47fe-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b47fe-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Test-cswebappanonymous cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b47fe-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="b47fe-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b47fe-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b47fe-112">描述</span><span class="sxs-lookup"><span data-stu-id="b47fe-112">Description</span></span>

<span data-ttu-id="b47fe-113">Test-cswebappanonymous cmdlet 會驗證匿名使用者可以加入 Lync Server 會議使用 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="b47fe-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="b47fe-114">當您執行 cmdlet 時，Test-cswebappanonymous 會連絡的 Web 票證服務，以取得匿名使用者的 web 票證。</span><span class="sxs-lookup"><span data-stu-id="b47fe-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="b47fe-115">如果此 cmdlet 成功中取得此票證，Test-cswebappanonymous 會再連絡 Lync Server，並嘗試建立獨立部署會議的立即訊息，應用程式共用，以及資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="b47fe-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="b47fe-116">請注意 Test-cswebappanonymous 只驗證 Api，用來建立這些會議的連線。</span><span class="sxs-lookup"><span data-stu-id="b47fe-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="b47fe-117">指令程式不會不會實際建立，並先進行任何會議。</span><span class="sxs-lookup"><span data-stu-id="b47fe-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b47fe-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="b47fe-118">Running the test</span></span>

<span data-ttu-id="b47fe-119">Test-cswebappanonymous 指令程式可以使用預先設定的測試帳戶的一組或已啟用 Lync Server 的任何兩個使用者的帳戶來執行。</span><span class="sxs-lookup"><span data-stu-id="b47fe-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="b47fe-120">若要執行這項檢查使用測試帳戶，您只需指定要測試的 Lync 伺服器集區的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="b47fe-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="b47fe-121">例如：</span><span class="sxs-lookup"><span data-stu-id="b47fe-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="b47fe-122">若要執行這項檢查使用實際使用者帳戶，您必須為每個帳戶建立兩個 Lync Server 管理命令介面的認證物件 （包含的帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="b47fe-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="b47fe-123">當您呼叫 Test-cswebappanonymous 時，您必須再包含這些認證物件與兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="b47fe-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="b47fe-124">如需詳細資訊，請參閱 < Test-cswebappanonymous cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b47fe-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="b47fe-125">請注意 Test-cswebappanonymous 已過時，以在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="b47fe-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b47fe-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="b47fe-126">Determining success or failure</span></span>

<span data-ttu-id="b47fe-127">如果 Test-cswebappanonymous 可以匿名使用者加入他/她的會議，此 cmdlet 會傳回成功的測試結果：</span><span class="sxs-lookup"><span data-stu-id="b47fe-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="b47fe-128">目標 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="b47fe-128">Target Fqdn :</span></span>

<span data-ttu-id="b47fe-129">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="b47fe-129">Result : Success</span></span>

<span data-ttu-id="b47fe-130">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b47fe-130">Latency : 00:00:00</span></span>

<span data-ttu-id="b47fe-131">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="b47fe-131">Error Message :</span></span>

<span data-ttu-id="b47fe-132">診斷：</span><span class="sxs-lookup"><span data-stu-id="b47fe-132">Diagnosis :</span></span>

<span data-ttu-id="b47fe-133">如果匿名使用者不能加入所需的會議的測試結果會被標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="b47fe-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="b47fe-134">通常 Test-cswebappanonymous 也會報告回詳細的錯誤訊息和診斷：</span><span class="sxs-lookup"><span data-stu-id="b47fe-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="b47fe-135">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b47fe-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b47fe-136">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="b47fe-136">Result : Failure</span></span>

<span data-ttu-id="b47fe-137">延遲： 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="b47fe-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="b47fe-138">錯誤訊息： 接收 Web 票證服務沒有回應</span><span class="sxs-lookup"><span data-stu-id="b47fe-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="b47fe-139">診斷： HTTP 要求是使用用戶端未經授權</span><span class="sxs-lookup"><span data-stu-id="b47fe-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="b47fe-140">驗證配置 'Ntlm'。</span><span class="sxs-lookup"><span data-stu-id="b47fe-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="b47fe-141">驗證</span><span class="sxs-lookup"><span data-stu-id="b47fe-141">The authentication</span></span>

<span data-ttu-id="b47fe-142">從伺服器收到的標頭已 '交涉，NTLM'。</span><span class="sxs-lookup"><span data-stu-id="b47fe-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b47fe-143">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="b47fe-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="b47fe-144">Test-cswebappanonymous 失敗通常為中心的使用者驗證錯誤： 您必須執行使用有效的使用者帳戶，即使指令程式會檢查匿名使用者能夠連線至 Lync Server 的測試。</span><span class="sxs-lookup"><span data-stu-id="b47fe-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="b47fe-145">如果 Test-cswebappanonymous 失敗，您應該確認所指定的使用者具有有效的 Lync Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b47fe-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="b47fe-146">您可以使用類似如下的命令擷取 Lync Server 的帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="b47fe-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="b47fe-147">如果 Enabled 屬性值不等於，則為 True，或如果命令就會失敗，這表示使用者沒有有效的 Lync Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b47fe-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="b47fe-148">您也應確認您執行 cmdlet 時，所提供的密碼是有效的密碼。</span><span class="sxs-lookup"><span data-stu-id="b47fe-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="b47fe-149">Office Web Apps Server 的組態問題也可能會導致 Test-cswebappanonymous 失敗;如果您收到下列診斷，，通常會是這種情況：</span><span class="sxs-lookup"><span data-stu-id="b47fe-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="b47fe-150">HTTP 要求的用戶端驗證配置 'Ntlm' 未經授權。</span><span class="sxs-lookup"><span data-stu-id="b47fe-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="b47fe-151">收到來自伺服器的驗證標頭已 '交涉，NTLM'。</span><span class="sxs-lookup"><span data-stu-id="b47fe-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="b47fe-152">如需有關診斷和解決 Office Web Apps Server 問題請參閱部落格文章[Office Web Apps Server 2013-機器一律回報為 Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)。</span><span class="sxs-lookup"><span data-stu-id="b47fe-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

