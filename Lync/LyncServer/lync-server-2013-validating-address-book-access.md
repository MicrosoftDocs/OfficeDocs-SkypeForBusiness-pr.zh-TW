---
title: Lync Server 2013：驗證通訊錄存取權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665ee384afd85c4be5c82182691953e1c78c9659
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="4ead6-102">驗證 Lync Server 2013 中的通訊錄存取權</span><span class="sxs-lookup"><span data-stu-id="4ead6-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ead6-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4ead6-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ead6-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="4ead6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4ead6-105">每日</span><span class="sxs-lookup"><span data-stu-id="4ead6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ead6-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="4ead6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4ead6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ead6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ead6-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="4ead6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4ead6-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4ead6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4ead6-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAddressBookService Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="4ead6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="4ead6-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4ead6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4ead6-112">描述</span><span class="sxs-lookup"><span data-stu-id="4ead6-112">Description</span></span>

<span data-ttu-id="4ead6-113">Test-CsAddressBookService Cmdlet 為您提供一種方法，讓您確認使用者可以連線至通訊錄下載 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="4ead6-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="4ead6-114">當您執行 Cmdlet 時，Test-CsAddressBookService 會連線至指定集區上的通訊錄下載 Web 服務，並要求通訊錄檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="4ead6-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="4ead6-115">[！注意] 如果通訊錄下載 Web 服務提供該位置，測試會視為成功。</span><span class="sxs-lookup"><span data-stu-id="4ead6-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="4ead6-116">如果要求遭到拒絕，則會將測試視為失敗。</span><span class="sxs-lookup"><span data-stu-id="4ead6-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4ead6-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="4ead6-117">Running the test</span></span>

<span data-ttu-id="4ead6-118">您可以使用預先設定的測試帳戶執行 Test-CsAddressBookService Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或已啟用 Lync Server 之任何使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ead6-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="4ead6-119">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="4ead6-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="4ead6-120">例如：</span><span class="sxs-lookup"><span data-stu-id="4ead6-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="4ead6-121">若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="4ead6-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="4ead6-122">然後，您必須在呼叫 Test-CsAddressBookService 時，包含該認證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="4ead6-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="4ead6-123">如需詳細資訊，請參閱[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="4ead6-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4ead6-124">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="4ead6-124">Determining success or failure</span></span>

<span data-ttu-id="4ead6-125">如果指定的使用者可以連線到通訊錄服務，您會收到類似如下的輸出，並將 Result 屬性標示為 [**成功**]：</span><span class="sxs-lookup"><span data-stu-id="4ead6-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="4ead6-126">TargetUri：https://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="4ead6-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="4ead6-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4ead6-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4ead6-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="4ead6-128">Result : Success</span></span>

<span data-ttu-id="4ead6-129">延遲：00：00：06.2260399</span><span class="sxs-lookup"><span data-stu-id="4ead6-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="4ead6-130">錯誤：</span><span class="sxs-lookup"><span data-stu-id="4ead6-130">Error :</span></span>

<span data-ttu-id="4ead6-131">診斷：</span><span class="sxs-lookup"><span data-stu-id="4ead6-131">Diagnosis :</span></span>

<span data-ttu-id="4ead6-132">如果指定的使用者無法進行此連線，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="4ead6-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4ead6-133">TargetUri：</span><span class="sxs-lookup"><span data-stu-id="4ead6-133">TargetUri :</span></span>

<span data-ttu-id="4ead6-134">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4ead6-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4ead6-135">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="4ead6-135">Result : Failure</span></span>

<span data-ttu-id="4ead6-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="4ead6-136">Latency : 00:00:00</span></span>

<span data-ttu-id="4ead6-137">診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="4ead6-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="4ead6-138">原因 = 未啟用 SIP 的目的 URI 或不是</span><span class="sxs-lookup"><span data-stu-id="4ead6-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="4ead6-139">存在。</span><span class="sxs-lookup"><span data-stu-id="4ead6-139">exist.</span></span>

<span data-ttu-id="4ead6-140">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="4ead6-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="4ead6-141">例如，上述輸出會指出測試失敗的原因是指定的使用者 (也就是說，「目的地 URI」 ) 不存在，或是尚未為 Lync Server 啟用。</span><span class="sxs-lookup"><span data-stu-id="4ead6-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="4ead6-142">您可以透過執行類似下列的命令，確認使用者帳戶是否有效，並確認您提供正確的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="4ead6-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="4ead6-143">Get-CsUser-Identity "sip:kenmyer@litwareinc.com" |Select-Object SipAddress，啟用</span><span class="sxs-lookup"><span data-stu-id="4ead6-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="4ead6-144">如果 Test-CsAddressBookService 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="4ead6-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="4ead6-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="4ead6-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="4ead6-146">包含 Verbose 參數時 Test-CsAddressBookService 會傳回所嘗試之每個動作的逐步帳戶，檢查指定之使用者登入 Lync 伺服器的功能。</span><span class="sxs-lookup"><span data-stu-id="4ead6-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="4ead6-147">例如，此範例輸出會顯示 Test-CsAddressBookService （至少在此範例中）可以下載通訊錄檔案：</span><span class="sxs-lookup"><span data-stu-id="4ead6-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="4ead6-148">傳送 Http GET 要求。</span><span class="sxs-lookup"><span data-stu-id="4ead6-148">Sending Http GET Request.</span></span>

<span data-ttu-id="4ead6-149">檔路徑 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="4ead6-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="4ead6-150">嘗試次數 = 1</span><span class="sxs-lookup"><span data-stu-id="4ead6-150">Attempt Number = 1</span></span>

<span data-ttu-id="4ead6-151">TimeOut (毫秒) = 60000</span><span class="sxs-lookup"><span data-stu-id="4ead6-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="4ead6-152">成功下載 ABS 檔https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="4ead6-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4ead6-153">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="4ead6-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="4ead6-154">以下是一些 Test-CsAddressBookService 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="4ead6-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="4ead6-155">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="4ead6-155">You specified an invalid user account.</span></span> <span data-ttu-id="4ead6-156">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="4ead6-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="4ead6-157">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ead6-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="4ead6-158">若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="4ead6-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="4ead6-159">如果 Enabled 屬性設定為 False，表示使用者目前未啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="4ead6-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4ead6-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ead6-160">See Also</span></span>


[<span data-ttu-id="4ead6-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="4ead6-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

