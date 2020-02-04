---
title: Lync Server 2013：測試 Web App 存取權
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
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="c0345-102">在 Lync Server 2013 中測試 Web 應用程式存取權</span><span class="sxs-lookup"><span data-stu-id="c0345-102">Test Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0345-103">_**主題上次修改日期：** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="c0345-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0345-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="c0345-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c0345-105">次</span><span class="sxs-lookup"><span data-stu-id="c0345-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0345-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="c0345-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c0345-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0345-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0345-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="c0345-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c0345-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c0345-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c0345-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsWebApp Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c0345-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="c0345-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0345-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c0345-112">說明</span><span class="sxs-lookup"><span data-stu-id="c0345-112">Description</span></span>

<span data-ttu-id="c0345-113">CsWebApp Cmdlet 會驗證經過驗證的使用者可以使用 Lync Web App 加入 Lync Server 會議。</span><span class="sxs-lookup"><span data-stu-id="c0345-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="c0345-114">當您執行 Cmdlet 時，CsWebApp 會與 Web 票證服務聯絡，以取得指定使用者的網頁入場券。</span><span class="sxs-lookup"><span data-stu-id="c0345-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="c0345-115">這些入場券可有效地充當 Lync Server 會議的「許可票證」。</span><span class="sxs-lookup"><span data-stu-id="c0345-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="c0345-116">如果可以檢索票證，且如果使用者可以進行驗證，CsWebApp 將會與 Lync Server 取得聯繫，並嘗試建立獨立的會議以進行立即訊息、應用程式共用及資料共同作業。</span><span class="sxs-lookup"><span data-stu-id="c0345-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="c0345-117">請注意，測試 CsWebApp 只會驗證用來建立這些會議的 Api 和連線。</span><span class="sxs-lookup"><span data-stu-id="c0345-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="c0345-118">這個 Cmdlet 的設計目的是要確認 Lync Web App 可以用來建立及加入會議。</span><span class="sxs-lookup"><span data-stu-id="c0345-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="c0345-119">不過，它不會實際建立及執行會議。</span><span class="sxs-lookup"><span data-stu-id="c0345-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c0345-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="c0345-120">Running the test</span></span>

<span data-ttu-id="c0345-121">CsWebApp Cmdlet 可以使用一組預先配置的測試帳戶或任何兩個已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="c0345-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="c0345-122">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c0345-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="c0345-123">例如：</span><span class="sxs-lookup"><span data-stu-id="c0345-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c0345-124">若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="c0345-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="c0345-125">當您呼叫 Test CsWebApp 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="c0345-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="c0345-126">如需詳細資訊，請參閱[Test CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="c0345-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="c0345-127">請注意，CsWebApp 已過時，無法在 Lync Server 2013 上使用。</span><span class="sxs-lookup"><span data-stu-id="c0345-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c0345-128">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="c0345-128">Determining success or failure</span></span>

<span data-ttu-id="c0345-129">如果測試 CsWebApp 可以將使用者加入其會議，則 Cmdlet 會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="c0345-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="c0345-130">目標 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="c0345-130">Target Fqdn :</span></span>

<span data-ttu-id="c0345-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="c0345-131">Result : Success</span></span>

<span data-ttu-id="c0345-132">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="c0345-132">Latency : 00:00:00</span></span>

<span data-ttu-id="c0345-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="c0345-133">Error Message :</span></span>

<span data-ttu-id="c0345-134">自檢</span><span class="sxs-lookup"><span data-stu-id="c0345-134">Diagnosis :</span></span>

<span data-ttu-id="c0345-135">如果使用者無法加入必要的會議，則測試結果會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="c0345-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="c0345-136">通常測試 CsWebApp 也會傳回詳細的錯誤訊息及診斷資訊：</span><span class="sxs-lookup"><span data-stu-id="c0345-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="c0345-137">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c0345-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c0345-138">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="c0345-138">Result : Failure</span></span>

<span data-ttu-id="c0345-139">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="c0345-139">Latency : 00:00:00</span></span>

<span data-ttu-id="c0345-140">錯誤訊息：沒有收到 Web 票證服務的回應</span><span class="sxs-lookup"><span data-stu-id="c0345-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="c0345-141">診斷： HTTP 要求未經用戶端的授權</span><span class="sxs-lookup"><span data-stu-id="c0345-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="c0345-142">驗證配置 "Ntlm"。</span><span class="sxs-lookup"><span data-stu-id="c0345-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="c0345-143">驗證</span><span class="sxs-lookup"><span data-stu-id="c0345-143">The authentication</span></span>

<span data-ttu-id="c0345-144">從伺服器接收到的標頭是「協商，NTLM」。</span><span class="sxs-lookup"><span data-stu-id="c0345-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c0345-145">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="c0345-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="c0345-146">測試 CsWebApp 的失敗通常會涉及使用者驗證錯誤。</span><span class="sxs-lookup"><span data-stu-id="c0345-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="c0345-147">如果測試 CsWebApp 失敗，您應該先確認指定的使用者擁有有效的使用者帳戶，且已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="c0345-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="c0345-148">您可以使用類似以下的命令來取得帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="c0345-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="c0345-149">如果 Enabled 屬性不等於 True 或命令失敗，則表示使用者沒有有效的 Lync Server 帳戶。您也應該確認您提供給 Cmdlet 的密碼是有效的。</span><span class="sxs-lookup"><span data-stu-id="c0345-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

