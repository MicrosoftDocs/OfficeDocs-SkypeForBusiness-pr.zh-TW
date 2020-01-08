---
title: Lync Server 2013：測試 Lync 用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8ea26c39582a69062526c7b4ae00343bb19482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="efd49-102">在 Lync Server 2013 中測試 Lync 用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="efd49-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efd49-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="efd49-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efd49-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="efd49-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="efd49-105">日常</span><span class="sxs-lookup"><span data-stu-id="efd49-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efd49-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="efd49-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="efd49-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efd49-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efd49-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="efd49-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="efd49-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="efd49-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="efd49-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsClientAuth Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="efd49-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="efd49-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="efd49-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="efd49-112">描述</span><span class="sxs-lookup"><span data-stu-id="efd49-112">Description</span></span>

<span data-ttu-id="efd49-113">CsClientAuth Cmdlet 可讓您判斷使用者是否可以使用用戶端憑證登入 Lync Server，您可以執行 Test-CsClientAuth Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="efd49-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="efd49-114">在呼叫 Test CsClientAuth 之後，此 Cmdlet 會與憑證提供服務取得聯繫，並為指定的使用者下載任何用戶端憑證的複本。</span><span class="sxs-lookup"><span data-stu-id="efd49-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="efd49-115">如果可以找到並下載用戶端憑證，測試 CsClientAuth 就會嘗試使用該憑證登入。</span><span class="sxs-lookup"><span data-stu-id="efd49-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="efd49-116">如果登入成功，測試 CsClientAuth 就會登出並報告測試已成功完成。</span><span class="sxs-lookup"><span data-stu-id="efd49-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="efd49-117">如果找不到或無法下載證書，或者 Cmdlet 無法使用該憑證登入，則 CsClientAuth 會報告測試失敗。</span><span class="sxs-lookup"><span data-stu-id="efd49-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="efd49-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="efd49-118">Running the test</span></span>

<span data-ttu-id="efd49-119">CsClientAuth Cmdlet 是使用任何已啟用 Lync Server 的使用者帳戶來執行。</span><span class="sxs-lookup"><span data-stu-id="efd49-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="efd49-120">若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="efd49-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="efd49-121">然後，您必須在系統呼叫 Test-CsClientAuth 時包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="efd49-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="efd49-122">如需詳細資訊，請參閱[Test CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="efd49-122">For more information, see the Help documentation for the [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="efd49-123">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="efd49-123">Determining success or failure</span></span>

<span data-ttu-id="efd49-124">如果指定的使用者可以使用用戶端憑證登入 Lync Server，您會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="efd49-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="efd49-125">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="efd49-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="efd49-126">結果：成功</span><span class="sxs-lookup"><span data-stu-id="efd49-126">Result : Success</span></span>

<span data-ttu-id="efd49-127">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="efd49-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="efd49-128">出錯</span><span class="sxs-lookup"><span data-stu-id="efd49-128">Error :</span></span>

<span data-ttu-id="efd49-129">自檢</span><span class="sxs-lookup"><span data-stu-id="efd49-129">Diagnosis :</span></span>

<span data-ttu-id="efd49-130">如果指定的使用者無法登入，則會將結果顯示為失敗，並會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="efd49-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="efd49-131">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="efd49-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="efd49-132">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="efd49-132">Result : Failure</span></span>

<span data-ttu-id="efd49-133">延隔時間：00：00：03.3645259</span><span class="sxs-lookup"><span data-stu-id="efd49-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="efd49-134">錯誤：無法下載指定使用者的 CS 憑證。</span><span class="sxs-lookup"><span data-stu-id="efd49-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="efd49-135">檢查是否</span><span class="sxs-lookup"><span data-stu-id="efd49-135">Check if</span></span>

<span data-ttu-id="efd49-136">提供的 uri 與認證正確無誤。</span><span class="sxs-lookup"><span data-stu-id="efd49-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="efd49-137">自檢</span><span class="sxs-lookup"><span data-stu-id="efd49-137">Diagnosis :</span></span>

<span data-ttu-id="efd49-138">例如，由於找不到指定使用者的有效用戶端憑證，所以先前的輸出指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="efd49-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="efd49-139">您可以執行下列命令，以傳回頒發給使用者的用戶端憑證清單：</span><span class="sxs-lookup"><span data-stu-id="efd49-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="efd49-140">如果測試 CsClientAuth 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="efd49-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="efd49-141">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsClientAuth 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="efd49-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="efd49-142">例如：</span><span class="sxs-lookup"><span data-stu-id="efd49-142">For example:</span></span>

<span data-ttu-id="efd49-143">嘗試下載適用于使用者的 CS 憑證： kenmyer@litwareinc.com 端點： STEpid</span><span class="sxs-lookup"><span data-stu-id="efd49-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="efd49-144">Web 服務 url：https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="efd49-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="efd49-145">無法從 web 服務下載 CS 憑證。</span><span class="sxs-lookup"><span data-stu-id="efd49-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="efd49-146">確認</span><span class="sxs-lookup"><span data-stu-id="efd49-146">CHECK:</span></span>

<span data-ttu-id="efd49-147">\-Web 服務 url 有效且 web 服務正常運作</span><span class="sxs-lookup"><span data-stu-id="efd49-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="efd49-148">\-如果您使用\\\\PhoneNo Pin 來進行驗證，請確定它們與使用者 uri 相符</span><span class="sxs-lookup"><span data-stu-id="efd49-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="efd49-149">\-如果您使用\\的是 NTLM Kerberos 驗證，請確認您提供的是有效認證</span><span class="sxs-lookup"><span data-stu-id="efd49-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="efd49-150">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="efd49-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="efd49-151">以下是測試 CsClientAuth 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="efd49-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="efd49-152">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="efd49-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="efd49-153">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="efd49-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="efd49-154">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="efd49-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="efd49-155">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="efd49-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="efd49-156">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="efd49-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="efd49-157">測試使用者可能沒有有效的用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="efd49-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="efd49-158">您可以使用類似以下的命令，返回指派給使用者的用戶端憑證資訊：</span><span class="sxs-lookup"><span data-stu-id="efd49-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

