---
title: Lync Server 2013：測試電話撥入式會議會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcc6d9277f7333989c59b812ed76087b9b6ca9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a><span data-ttu-id="7aa20-102">在 Lync Server 2013 中測試電話撥入式會議會話</span><span class="sxs-lookup"><span data-stu-id="7aa20-102">Testing dial-in conferencing session in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa20-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7aa20-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7aa20-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="7aa20-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7aa20-105">日常</span><span class="sxs-lookup"><span data-stu-id="7aa20-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7aa20-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="7aa20-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7aa20-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7aa20-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7aa20-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="7aa20-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7aa20-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7aa20-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7aa20-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsDialInConferencing Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7aa20-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialInConferencing cmdlet.</span></span> <span data-ttu-id="7aa20-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7aa20-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7aa20-112">描述</span><span class="sxs-lookup"><span data-stu-id="7aa20-112">Description</span></span>

<span data-ttu-id="7aa20-113">CsDialInConferencing Cmdlet 會驗證使用者是否可以參與電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="7aa20-113">The Test-CsDialInConferencing cmdlet verifies whether a user can participate in a dial-in conference.</span></span> <span data-ttu-id="7aa20-114">測試 CsDialInConferencing 的運作方式是嘗試將測試使用者記錄在系統上。</span><span class="sxs-lookup"><span data-stu-id="7aa20-114">Test-CsDialInConferencing works by trying to log a test user onto the system.</span></span> <span data-ttu-id="7aa20-115">如果登入成功，則 Cmdlet 會使用使用者的認證和許可權來嘗試所有可用的電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="7aa20-115">If the logon succeeds, the cmdlet will then use the user’s credentials and permissions to try all of the available dial-in conferencing access numbers.</span></span> <span data-ttu-id="7aa20-116">每次撥入嘗試的成功或失敗都會說出，然後從 Lync Server 登出測試使用者。測試 CsDialInConferencing 只會驗證是否可以建立適當的連線。</span><span class="sxs-lookup"><span data-stu-id="7aa20-116">The success or failure of each dial-in try will be noted, then the test user will be logged off from Lync Server.Test-CsDialInConferencing only verifies that the appropriate connections can be made.</span></span> <span data-ttu-id="7aa20-117">Cmdlet 不會實際撥打任何電話或建立任何其他使用者可以加入的撥入會議。</span><span class="sxs-lookup"><span data-stu-id="7aa20-117">The cmdlet does not actually make any phone calls or create any dial-in conferences that other users can join.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7aa20-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="7aa20-118">Running the test</span></span>

<span data-ttu-id="7aa20-119">CsDialInConferencing Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="7aa20-119">The Test-CsDialInConferencing cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="7aa20-120">若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="7aa20-120">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="7aa20-121">例如：</span><span class="sxs-lookup"><span data-stu-id="7aa20-121">For example:</span></span>

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="7aa20-122">若要使用實際的使用者帳戶執行此檢查，您必須建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="7aa20-122">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="7aa20-123">接著，您必須將該認證物件與帳戶 SIP 位址納入呼叫測試-CsDialInConferencing：</span><span class="sxs-lookup"><span data-stu-id="7aa20-123">You must then include that credentials object and the account SIP address the calling Test-CsDialInConferencing:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="7aa20-124">如需詳細資訊，請參閱[Test CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="7aa20-124">For more information, see the Help documentation for the [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7aa20-125">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="7aa20-125">Determining success or failure</span></span>

<span data-ttu-id="7aa20-126">如果指定的使用者可以登入 Lync Server，然後使用其中一個可用的電話撥入式會議存取號碼進行連線，則會收到與此類似的輸出，且 Result 屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="7aa20-126">If the specified user can log on to Lync Server and then make a connection using one of the available dial-in conferencing access numbers, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7aa20-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7aa20-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7aa20-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="7aa20-128">Result : Success</span></span>

<span data-ttu-id="7aa20-129">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="7aa20-129">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="7aa20-130">出錯</span><span class="sxs-lookup"><span data-stu-id="7aa20-130">Error :</span></span>

<span data-ttu-id="7aa20-131">自檢</span><span class="sxs-lookup"><span data-stu-id="7aa20-131">Diagnosis :</span></span>

<span data-ttu-id="7aa20-132">如果指定的使用者無法進行這個連線，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="7aa20-132">If the specified user can't make this connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7aa20-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7aa20-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7aa20-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="7aa20-134">Result : Failure</span></span>

<span data-ttu-id="7aa20-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="7aa20-135">Latency : 00:00:00</span></span>

<span data-ttu-id="7aa20-136">錯誤：登入遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="7aa20-136">Error : The log on was denied.</span></span> <span data-ttu-id="7aa20-137">檢查是否有適當的認證</span><span class="sxs-lookup"><span data-stu-id="7aa20-137">Check that the proper credentials are</span></span>

<span data-ttu-id="7aa20-138">正在使用中，且帳戶處於作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="7aa20-138">being used and the account is active.</span></span>

<span data-ttu-id="7aa20-139">內部例外狀況： NegotiateSecurityAssociation 失敗，錯誤：-</span><span class="sxs-lookup"><span data-stu-id="7aa20-139">Inner Exception:NegotiateSecurityAssociation failed, error: -</span></span>

<span data-ttu-id="7aa20-140">2146893044</span><span class="sxs-lookup"><span data-stu-id="7aa20-140">2146893044</span></span>

<span data-ttu-id="7aa20-141">自檢</span><span class="sxs-lookup"><span data-stu-id="7aa20-141">Diagnosis :</span></span>

<span data-ttu-id="7aa20-142">前一個輸出表示已拒絕測試使用者存取 Lync Server 本身。</span><span class="sxs-lookup"><span data-stu-id="7aa20-142">The previous output indicates that the test user was denied access to Lync Server itself.</span></span> <span data-ttu-id="7aa20-143">這通常表示傳遞給 Test CsDialInConferencing 的使用者認證無效。</span><span class="sxs-lookup"><span data-stu-id="7aa20-143">This typically means that the user credentials passed to Test-CsDialInConferencing were not valid.</span></span> <span data-ttu-id="7aa20-144">接著，您應該重新建立 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="7aa20-144">In turn, you should re-create the Windows PowerShell credentials object.</span></span> <span data-ttu-id="7aa20-145">雖然您可以取得使用者帳戶的密碼，但是您可以使用類似以下的命令來驗證 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="7aa20-145">Although you can retrieve the password for the user account, you can verify the SIP address by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7aa20-146">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="7aa20-146">Reasons why the test might have failed</span></span>

<span data-ttu-id="7aa20-147">以下是測試 CsDialInConferencing 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="7aa20-147">Here are some common reasons why Test-CsDialInConferencing might fail:</span></span>

  - <span data-ttu-id="7aa20-148">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="7aa20-148">You specified a user account that is not valid.</span></span> <span data-ttu-id="7aa20-149">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="7aa20-149">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="7aa20-150">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7aa20-150">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="7aa20-151">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="7aa20-151">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="7aa20-152">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="7aa20-152">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="7aa20-153">您的電話撥入式會議存取號碼可能不正確。</span><span class="sxs-lookup"><span data-stu-id="7aa20-153">You might have an incorrect dial-in conferencing access number.</span></span> <span data-ttu-id="7aa20-154">您可以使用此命令，返回目前設定的電話撥入式會議存取號碼清單：</span><span class="sxs-lookup"><span data-stu-id="7aa20-154">You can return your currently-configured list of dial-in conferencing access numbers by using this command:</span></span>
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

