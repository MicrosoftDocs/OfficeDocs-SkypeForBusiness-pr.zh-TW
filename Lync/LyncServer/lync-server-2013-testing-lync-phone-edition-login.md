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
ms.openlocfilehash: ce22e6c7f5fb48132f3f67c79c33daaa568d93ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="966b1-102">在 Lync Server 2013 中測試 Lync Phone Edition 登入</span><span class="sxs-lookup"><span data-stu-id="966b1-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="966b1-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="966b1-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="966b1-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="966b1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="966b1-105">每日</span><span class="sxs-lookup"><span data-stu-id="966b1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="966b1-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="966b1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="966b1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="966b1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="966b1-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="966b1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="966b1-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="966b1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="966b1-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsPhoneBootstrap Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="966b1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="966b1-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="966b1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="966b1-112">描述</span><span class="sxs-lookup"><span data-stu-id="966b1-112">Description</span></span>

<span data-ttu-id="966b1-113">Test-CsPhoneBootstrap Cmdlet 可讓系統管理員使用 Lync 2013 Phone Edition 相容裝置登入系統，以驗證指定的使用者（使用指派的電話號碼和 PIN 碼）。</span><span class="sxs-lookup"><span data-stu-id="966b1-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="966b1-114"> (實際執行測試時，不需要裝置。 ) </span><span class="sxs-lookup"><span data-stu-id="966b1-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="966b1-115">為了讓 Test-CsPhoneBootstrap 進行檢查，主控所測試之使用者帳戶的註冊集區集區必須可透過 DHCP 來探索。</span><span class="sxs-lookup"><span data-stu-id="966b1-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="966b1-116">若要判斷註冊機構是否以這種方式被探索，請使用 Cmdlet Get-CsRegistrarConfiguration，並檢查 EnableDHCPServer 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="966b1-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="966b1-117">如果此屬性設定為 False，您必須使用 Get-csregistrarconfiguration 將屬性值設定為 True，並讓註冊機構可使用 DHCP 加以探索。</span><span class="sxs-lookup"><span data-stu-id="966b1-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="966b1-118">您也可以使用企業 DHCP 伺服器及設定 Lync Server 特有的選項來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="966b1-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="966b1-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="966b1-119">Running the test</span></span>

<span data-ttu-id="966b1-120">若要執行 Test-CsPhoneBootstrap Cmdlet，您必須至少為有效的 Lync Server 使用者提供電話號碼及用戶端個人識別碼 (PIN) 。</span><span class="sxs-lookup"><span data-stu-id="966b1-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="966b1-121">例如，下列命令會測試具有電話號碼12065551219和 PIN 碼0712之使用者的登入能力：</span><span class="sxs-lookup"><span data-stu-id="966b1-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="966b1-122">若要進行更完整的檢查，您也可以包含使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="966b1-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="966b1-123">在此情況下，必須全部有效的電話號碼、用戶端 PIN 和 SIP 位址，才能成功測試：</span><span class="sxs-lookup"><span data-stu-id="966b1-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="966b1-124">如需詳細資訊，請參閱[Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="966b1-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="966b1-125">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="966b1-125">Determining success or failure</span></span>

<span data-ttu-id="966b1-126">如果指定的使用者能夠連線至 Lync 伺服器，則會收到類似下列的輸出，並將 Result 屬性標示為 [**成功]：**</span><span class="sxs-lookup"><span data-stu-id="966b1-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="966b1-127">TargetUri：https://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="966b1-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="966b1-128">CertProvisioningService</span><span class="sxs-lookup"><span data-stu-id="966b1-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="966b1-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="966b1-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="966b1-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="966b1-130">Result : Success</span></span>

<span data-ttu-id="966b1-131">延遲：00：00：06.3981276</span><span class="sxs-lookup"><span data-stu-id="966b1-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="966b1-132">錯誤：</span><span class="sxs-lookup"><span data-stu-id="966b1-132">Error :</span></span>

<span data-ttu-id="966b1-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="966b1-133">Diagnosis :</span></span>

<span data-ttu-id="966b1-134">如果指定的使用者無法進行連線，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="966b1-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="966b1-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="966b1-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="966b1-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="966b1-136">Result : Failure</span></span>

<span data-ttu-id="966b1-137">延遲：00：00：04.1993845</span><span class="sxs-lookup"><span data-stu-id="966b1-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="966b1-138">錯誤：錯誤-沒有為 Web 票證服務接收任何回應。</span><span class="sxs-lookup"><span data-stu-id="966b1-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="966b1-139">診斷：</span><span class="sxs-lookup"><span data-stu-id="966b1-139">Diagnosis :</span></span>

<span data-ttu-id="966b1-140">先前的輸出說明測試失敗，因為 Web 票證服務沒有回應。</span><span class="sxs-lookup"><span data-stu-id="966b1-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="966b1-141">這可能是因為服務本身發生問題，或是因為 SIP 位址、電話號碼或用戶端 PIN 碼已傳遞至 Test-CsPhoneBootstrap。</span><span class="sxs-lookup"><span data-stu-id="966b1-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="966b1-142">您可以使用類似下列的命令來驗證使用者的 SIP 位址和電話號碼：</span><span class="sxs-lookup"><span data-stu-id="966b1-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="966b1-143">您可以使用下列命令來確認使用者是否有有效的 PIN 碼：</span><span class="sxs-lookup"><span data-stu-id="966b1-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="966b1-144">如果 Test-CsPhoneBootstrap 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="966b1-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="966b1-145">包含 Verbose 參數時，Test-CsPhoneBootstrap 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="966b1-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="966b1-146">例如，以下是失敗登入的部分輸出，其中包含不正確 PIN 碼的會話：</span><span class="sxs-lookup"><span data-stu-id="966b1-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="966b1-147">使用 PIN 驗證搭配電話 \\ 分機： 12065551219 PIN：0712</span><span class="sxs-lookup"><span data-stu-id="966b1-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="966b1-148">無法取得 web 票證</span><span class="sxs-lookup"><span data-stu-id="966b1-148">Could not get web ticket</span></span>

<span data-ttu-id="966b1-149">檢查：</span><span class="sxs-lookup"><span data-stu-id="966b1-149">CHECK :</span></span>

<span data-ttu-id="966b1-150">\-Web 服務 url 有效且 web 服務可運作</span><span class="sxs-lookup"><span data-stu-id="966b1-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="966b1-151">\-若要使用 PhoneNo \\ PIN 來驗證，請確定它們符合使用者 uri</span><span class="sxs-lookup"><span data-stu-id="966b1-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="966b1-152">\-若要使用 NTLM \\ Kerberos 驗證，請確定您提供有效的認證</span><span class="sxs-lookup"><span data-stu-id="966b1-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="966b1-153">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="966b1-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="966b1-154">以下是一些 Test-CsPhoneBootstrap 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="966b1-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="966b1-155">您可能指定了不正確 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="966b1-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="966b1-156">您可以使用類似下列的命令來驗證 SIP 位址是否正確：</span><span class="sxs-lookup"><span data-stu-id="966b1-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="966b1-157">您可能指定了不正確 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="966b1-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="966b1-158">雖然您無法取回使用者的 PIN 碼號碼，但您可以使用類似下列的命令，確認使用者至少具有 PIN 碼號碼：</span><span class="sxs-lookup"><span data-stu-id="966b1-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="966b1-159">您可能指定了不正確電話號碼。</span><span class="sxs-lookup"><span data-stu-id="966b1-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="966b1-160">您可以使用類似下列的命令來驗證使用者的電話：</span><span class="sxs-lookup"><span data-stu-id="966b1-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="966b1-161">註冊機構集區未啟用 DHCP。</span><span class="sxs-lookup"><span data-stu-id="966b1-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="966b1-162">若要判斷您的註冊區集區是否已啟用 DHCP，請執行 Get-CsRegistrarConfiguration Cmdlet，並檢查 EnableDHCPServer 屬性的值。</span><span class="sxs-lookup"><span data-stu-id="966b1-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="966b1-163">例如：</span><span class="sxs-lookup"><span data-stu-id="966b1-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

