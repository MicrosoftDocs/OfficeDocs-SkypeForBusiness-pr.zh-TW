---
title: Lync Server 2013：測試 Lync Phone Edition 登入
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bfce8b1e034fd9772e10178366b0ed524fdbd55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="616c1-102">在 Lync Server 2013 中測試 Lync Phone Edition 登入</span><span class="sxs-lookup"><span data-stu-id="616c1-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="616c1-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="616c1-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="616c1-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="616c1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="616c1-105">日常</span><span class="sxs-lookup"><span data-stu-id="616c1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="616c1-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="616c1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="616c1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="616c1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="616c1-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="616c1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="616c1-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="616c1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="616c1-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsPhoneBootstrap Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="616c1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="616c1-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="616c1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="616c1-112">說明</span><span class="sxs-lookup"><span data-stu-id="616c1-112">Description</span></span>

<span data-ttu-id="616c1-113">CsPhoneBootstrap Cmdlet 可讓管理員驗證指定的使用者（使用電話號碼和指派給他/她的 PIN）可以從 Lync 2013 Phone 版本相容的裝置登入系統。</span><span class="sxs-lookup"><span data-stu-id="616c1-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="616c1-114">（實際不需要裝置就能執行測試。）</span><span class="sxs-lookup"><span data-stu-id="616c1-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="616c1-115">為了讓測試 CsPhoneBootstrap 進行檢查，託管已測試之使用者帳戶的註冊機構池必須使用 DHCP 來探索。</span><span class="sxs-lookup"><span data-stu-id="616c1-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="616c1-116">若要判斷註冊機構是否以這種方式被發現，請使用 Cmdlet CsRegistrarConfiguration 並檢查 EnableDHCPServer 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="616c1-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="616c1-117">如果此屬性設定為 False，您必須使用 CsRegistrarConfiguration 將屬性值設定為 True，並使用 DHCP 讓註冊機構可搜尋。</span><span class="sxs-lookup"><span data-stu-id="616c1-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="616c1-118">您也可以使用企業 DHCP 伺服器並設定 Lync 伺服器專用的選項，來完成此動作。</span><span class="sxs-lookup"><span data-stu-id="616c1-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="616c1-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="616c1-119">Running the test</span></span>

<span data-ttu-id="616c1-120">若要執行 CsPhoneBootstrap Cmdlet，您必須至少為有效的 Lync Server 使用者提供電話號碼和用戶端個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="616c1-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="616c1-121">例如，這個命令會測試具有電話號碼12065551219和 PIN 0712 的使用者的登入能力：</span><span class="sxs-lookup"><span data-stu-id="616c1-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="616c1-122">若要進行更完整的檢查，您也可以包含使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="616c1-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="616c1-123">在這種情況下，電話號碼、用戶端 PIN 及 SIP 位址都必須是有效的，測試才能成功：</span><span class="sxs-lookup"><span data-stu-id="616c1-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="616c1-124">如需詳細資訊，請參閱[Test CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="616c1-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="616c1-125">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="616c1-125">Determining success or failure</span></span>

<span data-ttu-id="616c1-126">如果指定的使用者能夠連線到 Lync Server，您將會收到與此類似的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="616c1-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="616c1-127">TargetUri :https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="616c1-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="616c1-128">CertProvisioningService （.svc）</span><span class="sxs-lookup"><span data-stu-id="616c1-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="616c1-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="616c1-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="616c1-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="616c1-130">Result : Success</span></span>

<span data-ttu-id="616c1-131">延隔時間：00：00：06.3981276</span><span class="sxs-lookup"><span data-stu-id="616c1-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="616c1-132">出錯</span><span class="sxs-lookup"><span data-stu-id="616c1-132">Error :</span></span>

<span data-ttu-id="616c1-133">自檢</span><span class="sxs-lookup"><span data-stu-id="616c1-133">Diagnosis :</span></span>

<span data-ttu-id="616c1-134">如果指定的使用者無法進行連線，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="616c1-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="616c1-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="616c1-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="616c1-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="616c1-136">Result : Failure</span></span>

<span data-ttu-id="616c1-137">延隔時間：00：00：04.1993845</span><span class="sxs-lookup"><span data-stu-id="616c1-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="616c1-138">錯誤：錯誤-沒有收到 Web 票證服務的回應。</span><span class="sxs-lookup"><span data-stu-id="616c1-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="616c1-139">自檢</span><span class="sxs-lookup"><span data-stu-id="616c1-139">Diagnosis :</span></span>

<span data-ttu-id="616c1-140">先前的輸出指出由於 Web 票證服務沒有回應，測試失敗。</span><span class="sxs-lookup"><span data-stu-id="616c1-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="616c1-141">這可能是因為服務本身有問題，或是由於 SIP 位址、電話號碼或用戶端 PIN 傳遞到測試 CsPhoneBootstrap。</span><span class="sxs-lookup"><span data-stu-id="616c1-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="616c1-142">您可以使用類似以下的命令來驗證使用者的 SIP 位址和電話號碼：</span><span class="sxs-lookup"><span data-stu-id="616c1-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="616c1-143">而且，您可以使用下列命令驗證使用者是否有有效的 PIN：</span><span class="sxs-lookup"><span data-stu-id="616c1-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="616c1-144">如果測試 CsPhoneBootstrap 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="616c1-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="616c1-145">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPhoneBootstrap 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="616c1-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="616c1-146">例如，以下是失敗登錄的一部分輸出，其中包含不正確 PIN 的會話：</span><span class="sxs-lookup"><span data-stu-id="616c1-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="616c1-147">將 PIN 驗證與手機\\Ext： 12065551219 PIN：0712結合使用</span><span class="sxs-lookup"><span data-stu-id="616c1-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="616c1-148">無法取得網頁入場券</span><span class="sxs-lookup"><span data-stu-id="616c1-148">Could not get web ticket</span></span>

<span data-ttu-id="616c1-149">確認</span><span class="sxs-lookup"><span data-stu-id="616c1-149">CHECK :</span></span>

<span data-ttu-id="616c1-150">\-Web 服務 url 有效且 web 服務正常運作</span><span class="sxs-lookup"><span data-stu-id="616c1-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="616c1-151">\-如果您使用\\PhoneNo PIN 來進行驗證，請確定它們與使用者 uri 相符</span><span class="sxs-lookup"><span data-stu-id="616c1-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="616c1-152">\-如果您使用\\的是 NTLM Kerberos 驗證，請確認您提供的是有效認證</span><span class="sxs-lookup"><span data-stu-id="616c1-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="616c1-153">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="616c1-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="616c1-154">以下是測試 CsPhoneBootstrap 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="616c1-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="616c1-155">您可能指定了不正確 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="616c1-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="616c1-156">您可以使用如下的命令來驗證 SIP 位址是否正確：</span><span class="sxs-lookup"><span data-stu-id="616c1-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="616c1-157">您可能指定了不正確 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="616c1-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="616c1-158">雖然您無法取得使用者的 PIN 碼，但您可以使用類似以下的命令，確認使用者至少擁有 PIN 碼：</span><span class="sxs-lookup"><span data-stu-id="616c1-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="616c1-159">您可能指定了不正確電話號碼。</span><span class="sxs-lookup"><span data-stu-id="616c1-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="616c1-160">您可以使用類似下列的命令來驗證使用者的電話：</span><span class="sxs-lookup"><span data-stu-id="616c1-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="616c1-161">註冊機構池不是 DHCP 啟用的。</span><span class="sxs-lookup"><span data-stu-id="616c1-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="616c1-162">若要判斷您的註冊機構池是否已啟用 DHCP，請執行 CsRegistrarConfiguration Cmdlet，然後檢查 EnableDHCPServer 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="616c1-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="616c1-163">例如：</span><span class="sxs-lookup"><span data-stu-id="616c1-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

