---
title: Lync Server 2013：測試電話撥入式會議會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a7c3251ef5ff907dbf9964daaca222584953e75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536080"
---
# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="d0370-102">在 Lync Server 2013 中測試電話撥入式會議會話</span><span class="sxs-lookup"><span data-stu-id="d0370-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0370-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d0370-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0370-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="d0370-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d0370-105">每日</span><span class="sxs-lookup"><span data-stu-id="d0370-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0370-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="d0370-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d0370-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0370-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0370-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d0370-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d0370-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d0370-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d0370-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsDialInConferencing Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d0370-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="d0370-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d0370-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d0370-112">描述</span><span class="sxs-lookup"><span data-stu-id="d0370-112">Description</span></span>

<span data-ttu-id="d0370-113">Test-CsDialInConferencing Cmdlet 會驗證使用者是否可以加入電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="d0370-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="d0370-114">Test-CsDialInConferencing 會嘗試將測試使用者登入系統來運作。</span><span class="sxs-lookup"><span data-stu-id="d0370-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="d0370-115">如果登入成功，則 Cmdlet 會使用使用者的認證和許可權，以嘗試所有可用的電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d0370-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="d0370-116">每次撥入嘗試的成功或失敗都會記下，然後會從 Lync Server 登出測試使用者。 Test-CsDialInConferencing 只會驗證是否可以進行適當的連線。</span><span class="sxs-lookup"><span data-stu-id="d0370-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="d0370-117">此 Cmdlet 不會實際撥打任何電話，也不會建立其他使用者可以加入的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="d0370-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d0370-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="d0370-118">Running the test</span></span>

<span data-ttu-id="d0370-119">您可以使用預先設定的測試帳戶執行 Test-CsDialInConferencing Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d0370-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="d0370-120">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d0370-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d0370-121">例如：</span><span class="sxs-lookup"><span data-stu-id="d0370-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="d0370-122">若要使用實際使用者帳戶執行這種檢查，您必須建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="d0370-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="d0370-123">然後，您必須包含該認證物件，以及呼叫 Test-CsDialInConferencing 的帳戶 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="d0370-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="d0370-124">如需詳細資訊，請參閱 [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="d0370-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d0370-125">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="d0370-125">Determining success or failure</span></span>

<span data-ttu-id="d0370-126">如果指定的使用者可以登入 Lync 伺服器，然後使用其中一個可用的電話撥入式會議存取號碼進行連線，則會收到類似下列的輸出，並將 Result 屬性標示為「 **成功」：**</span><span class="sxs-lookup"><span data-stu-id="d0370-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d0370-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d0370-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d0370-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="d0370-128">Result : Success</span></span>

<span data-ttu-id="d0370-129">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="d0370-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="d0370-130">錯誤：</span><span class="sxs-lookup"><span data-stu-id="d0370-130">Error :</span></span>

<span data-ttu-id="d0370-131">診斷：</span><span class="sxs-lookup"><span data-stu-id="d0370-131">Diagnosis :</span></span>

<span data-ttu-id="d0370-132">如果指定的使用者無法進行此連線，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="d0370-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d0370-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d0370-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d0370-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="d0370-134">Result : Failure</span></span>

<span data-ttu-id="d0370-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="d0370-135">Latency : 00:00:00</span></span>

<span data-ttu-id="d0370-136">錯誤：登入已遭拒絕。</span><span class="sxs-lookup"><span data-stu-id="d0370-136">Error : The log on was denied.</span></span> <span data-ttu-id="d0370-137">檢查適當的認證是否</span><span class="sxs-lookup"><span data-stu-id="d0370-137">Check that the proper credentials are</span></span>

<span data-ttu-id="d0370-138">正在使用中，且帳戶為作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="d0370-138">being used and the account is active.</span></span>

<span data-ttu-id="d0370-139">內部例外狀況： NegotiateSecurityAssociation 失敗，錯誤：-</span><span class="sxs-lookup"><span data-stu-id="d0370-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="d0370-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="d0370-140">2146893044</span></span>

<span data-ttu-id="d0370-141">診斷：</span><span class="sxs-lookup"><span data-stu-id="d0370-141">Diagnosis :</span></span>

<span data-ttu-id="d0370-142">先前的輸出表明已拒絕對 Lync Server 自身進行存取的測試使用者。</span><span class="sxs-lookup"><span data-stu-id="d0370-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="d0370-143">這通常表示傳遞給 Test-CsDialInConferencing 的使用者認證無效。</span><span class="sxs-lookup"><span data-stu-id="d0370-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="d0370-144">反過來，您應該重新建立 [Windows PowerShell 認證] 物件。</span><span class="sxs-lookup"><span data-stu-id="d0370-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="d0370-145">雖然您可以為使用者帳戶取得密碼，但是您可以使用類似下列的命令來驗證 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="d0370-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d0370-146">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="d0370-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="d0370-147">以下是一些 Test-CsDialInConferencing 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="d0370-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="d0370-148">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="d0370-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="d0370-149">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="d0370-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="d0370-150">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d0370-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d0370-151">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="d0370-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d0370-152">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="d0370-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="d0370-153">您可能會有不正確的電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="d0370-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="d0370-154">您可以使用下列命令，傳回目前設定的電話撥入式會議存取號碼清單：</span><span class="sxs-lookup"><span data-stu-id="d0370-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

