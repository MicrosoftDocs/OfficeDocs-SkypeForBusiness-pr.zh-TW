---
title: Lync Server 2013：測試 Lync 用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308bb50e5365cd45c993875ea503b33b32617397
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519030"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="88266-102">在 Lync Server 2013 中測試 Lync 用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="88266-102">Testing Lync Client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88266-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="88266-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88266-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="88266-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="88266-105">每日</span><span class="sxs-lookup"><span data-stu-id="88266-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88266-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="88266-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="88266-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="88266-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88266-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="88266-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="88266-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="88266-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="88266-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsClientAuth Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="88266-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="88266-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="88266-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="88266-112">描述</span><span class="sxs-lookup"><span data-stu-id="88266-112">Description</span></span>

<span data-ttu-id="88266-113">Test-CsClientAuth Cmdlet 可讓您判斷使用者是否可以使用用戶端憑證登入 Lync Server，您可以執行 Test-CsClientAuth Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88266-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="88266-114">呼叫 Test-CsClientAuth 後，Cmdlet 會聯繫憑證布建服務，並為指定的使用者下載任何用戶端憑證的複本。</span><span class="sxs-lookup"><span data-stu-id="88266-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="88266-115">如果可以找到並下載用戶端憑證，Test-CsClientAuth 會嘗試使用該憑證登入。</span><span class="sxs-lookup"><span data-stu-id="88266-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="88266-116">登入成功時，Test-CsClientAuth 會登出並報告測試已成功。</span><span class="sxs-lookup"><span data-stu-id="88266-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="88266-117">如果找不到憑證或無法下載憑證，或者 Cmdlet 無法使用該憑證登入，則 Test-CsClientAuth 將會報告測試失敗。</span><span class="sxs-lookup"><span data-stu-id="88266-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="88266-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="88266-118">Running the test</span></span>

<span data-ttu-id="88266-119">使用啟用 Lync Server 之任何使用者的帳戶來執行 Test-CsClientAuth Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="88266-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="88266-120">若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="88266-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="88266-121">然後，您必須在系統呼叫 Test-CsClientAuth 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="88266-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="88266-122">如需詳細資訊，請參閱 [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="88266-122">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="88266-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="88266-123">Determining success or failure</span></span>

<span data-ttu-id="88266-124">如果指定的使用者可以使用用戶端憑證登入 Lync Server，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="88266-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="88266-125">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="88266-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="88266-126">結果：成功</span><span class="sxs-lookup"><span data-stu-id="88266-126">Result : Success</span></span>

<span data-ttu-id="88266-127">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="88266-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="88266-128">錯誤：</span><span class="sxs-lookup"><span data-stu-id="88266-128">Error :</span></span>

<span data-ttu-id="88266-129">診斷：</span><span class="sxs-lookup"><span data-stu-id="88266-129">Diagnosis :</span></span>

<span data-ttu-id="88266-130">如果指定的使用者無法登入，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="88266-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="88266-131">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="88266-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="88266-132">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="88266-132">Result : Failure</span></span>

<span data-ttu-id="88266-133">延遲：00：00：03.3645259</span><span class="sxs-lookup"><span data-stu-id="88266-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="88266-134">錯誤：無法下載指定使用者的 CS 憑證。</span><span class="sxs-lookup"><span data-stu-id="88266-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="88266-135">檢查是否</span><span class="sxs-lookup"><span data-stu-id="88266-135">Check if</span></span>

<span data-ttu-id="88266-136">提供的 uri 和認證是正確的。</span><span class="sxs-lookup"><span data-stu-id="88266-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="88266-137">診斷：</span><span class="sxs-lookup"><span data-stu-id="88266-137">Diagnosis :</span></span>

<span data-ttu-id="88266-138">例如，由於找不到指定使用者的有效用戶端憑證，所以先前的輸出會指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="88266-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="88266-139">您可以執行下列命令，傳回向使用者發出之用戶端憑證的清單，如下所示：</span><span class="sxs-lookup"><span data-stu-id="88266-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="88266-140">如果 Test-CsClientAuth 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="88266-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="88266-141">包含 Verbose 參數時，Test-CsClientAuth 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="88266-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="88266-142">例如：</span><span class="sxs-lookup"><span data-stu-id="88266-142">For example:</span></span>

<span data-ttu-id="88266-143">嘗試為使用者下載 CS 憑證： kenmyer@litwareinc.com 端點： STEpid</span><span class="sxs-lookup"><span data-stu-id="88266-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="88266-144">Web 服務 url： https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="88266-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="88266-145">無法從 web 服務下載 CS 憑證。</span><span class="sxs-lookup"><span data-stu-id="88266-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="88266-146">檢查：</span><span class="sxs-lookup"><span data-stu-id="88266-146">CHECK:</span></span>

<span data-ttu-id="88266-147">\- Web 服務 url 有效且 web 服務可運作</span><span class="sxs-lookup"><span data-stu-id="88266-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="88266-148">\-若要使用 PhoneNo \\ \\ Pin 來驗證，請確定它們符合使用者 uri</span><span class="sxs-lookup"><span data-stu-id="88266-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="88266-149">\- 若要使用 NTLM \\ Kerberos 驗證，請確定您提供有效的認證</span><span class="sxs-lookup"><span data-stu-id="88266-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="88266-150">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="88266-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="88266-151">以下是一些 Test-CsClientAuth 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="88266-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="88266-152">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="88266-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="88266-153">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="88266-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="88266-154">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="88266-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="88266-155">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="88266-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="88266-156">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="88266-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="88266-157">測試使用者可能沒有有效的用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="88266-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="88266-158">您可以使用類似下列的命令，傳回指派給使用者之用戶端憑證的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="88266-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

