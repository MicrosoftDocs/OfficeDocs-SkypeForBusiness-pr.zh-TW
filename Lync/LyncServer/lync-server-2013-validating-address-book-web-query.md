---
title: Lync Server 2013：驗證通訊錄 web 查詢
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae10fa68703393459a72eaab7236f214502a614
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508550"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="543a2-102">在 Lync Server 2013 中驗證通訊錄 web 查詢</span><span class="sxs-lookup"><span data-stu-id="543a2-102">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="543a2-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="543a2-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="543a2-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="543a2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="543a2-105">每日</span><span class="sxs-lookup"><span data-stu-id="543a2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="543a2-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="543a2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="543a2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="543a2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="543a2-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="543a2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="543a2-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="543a2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="543a2-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAddressBookWebQuery Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="543a2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="543a2-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="543a2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="543a2-112">描述</span><span class="sxs-lookup"><span data-stu-id="543a2-112">Description</span></span>

<span data-ttu-id="543a2-113">Test-CsAddressBookWebQuery Cmdlet 可讓系統管理員驗證使用者是否可以使用通訊錄 Web 查詢服務來搜尋特定的連絡人。</span><span class="sxs-lookup"><span data-stu-id="543a2-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="543a2-114">當您執行 Cmdlet 時，Test-CsAddressBookWebQuery 會先連線至 Web 票證服務，以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="543a2-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="543a2-115">如果驗證成功，則 Cmdlet 會連接到通訊錄 Web 查詢服務，並搜尋指定的連絡人。</span><span class="sxs-lookup"><span data-stu-id="543a2-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="543a2-116">如果找到該連絡人，Cmdlet 會嘗試將該資訊傳回本機電腦。</span><span class="sxs-lookup"><span data-stu-id="543a2-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="543a2-117">只有在所有這些步驟都可以完成時，才會將測試標記為成功。</span><span class="sxs-lookup"><span data-stu-id="543a2-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="543a2-118">如需詳細資訊，請參閱 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="543a2-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="543a2-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="543a2-119">Running the test</span></span>

<span data-ttu-id="543a2-120">您可以使用預先設定的測試帳戶執行 Test-CsAddressBookWebQuery Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="543a2-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="543a2-121">若要使用測試帳戶執行這項檢查，您只需要指定 Lync Server 集區的 FQDN，以及充當搜尋目標之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="543a2-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="543a2-122">例如：</span><span class="sxs-lookup"><span data-stu-id="543a2-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="543a2-123">若要使用實際使用者帳戶執行這種檢查，您必須建立 Windows PowerShell 身分憑證物件，該物件包含有效的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="543a2-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="543a2-124">然後，您必須在程式碼呼叫 Test-CsAddressBookWebQuery 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="543a2-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="543a2-125">如需詳細資訊，請參閱 [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="543a2-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="543a2-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="543a2-126">Determining success or failure</span></span>

<span data-ttu-id="543a2-127">如果指定的使用者可以連線到通訊錄服務並取得目標使用者位址，則會以標記為 [成功] 的 Result 屬性傳回類似下列輸出：</span><span class="sxs-lookup"><span data-stu-id="543a2-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="543a2-128">TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="543a2-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="543a2-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="543a2-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="543a2-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="543a2-130">Result : Success</span></span>

<span data-ttu-id="543a2-131">延遲：00：00：06.2611356</span><span class="sxs-lookup"><span data-stu-id="543a2-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="543a2-132">錯誤：</span><span class="sxs-lookup"><span data-stu-id="543a2-132">Error :</span></span>

<span data-ttu-id="543a2-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="543a2-133">Diagnosis :</span></span>

<span data-ttu-id="543a2-134">如果指定的使用者無法連線，或無法檢索目標使用者位址，則結果會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="543a2-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="543a2-135">TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="543a2-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="543a2-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="543a2-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="543a2-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="543a2-137">Result : Failure</span></span>

<span data-ttu-id="543a2-138">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="543a2-138">Latency : 00:00:00</span></span>

<span data-ttu-id="543a2-139">錯誤：通訊錄 Web 服務要求失敗，回應碼</span><span class="sxs-lookup"><span data-stu-id="543a2-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="543a2-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="543a2-140">NoEntryFound.</span></span>

<span data-ttu-id="543a2-141">診斷：</span><span class="sxs-lookup"><span data-stu-id="543a2-141">Diagnosis :</span></span>

<span data-ttu-id="543a2-142">因為找不到目標使用者，所以先前的輸出會指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="543a2-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="543a2-143">您可以執行類似下列的命令，判斷是否已將有效的 SIP 位址傳遞給 Test-CsAddressBookWebQuery：</span><span class="sxs-lookup"><span data-stu-id="543a2-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="543a2-144">如果 Test-CsAddressBookWebQuery 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="543a2-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="543a2-145">包含 Verbose 參數時，Test-CsAddressBookWebQuery 會傳回所嘗試之每個動作的逐步帳戶，檢查指定之使用者登入 Lync 伺服器的功能。</span><span class="sxs-lookup"><span data-stu-id="543a2-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="543a2-146">例如，此輸出指出 Test-CsAddressBookWebQuery 能夠連線至通訊錄服務，但無法找到目標 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="543a2-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="543a2-147">' QueryAddressBookWebService ' 活動已開始。</span><span class="sxs-lookup"><span data-stu-id="543a2-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="543a2-148">呼叫通訊錄 Web 查詢服務。</span><span class="sxs-lookup"><span data-stu-id="543a2-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="543a2-149">ABWS URL=</span><span class="sxs-lookup"><span data-stu-id="543a2-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="543a2-150">通訊錄查詢例外狀況：由於回應碼 NoEntryFound，Address Book Web 服務要求失敗。</span><span class="sxs-lookup"><span data-stu-id="543a2-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="543a2-151">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="543a2-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="543a2-152">以下是一些 Test-CsAddressBookWebQuery 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="543a2-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="543a2-153">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="543a2-153">You specified an invalid user account.</span></span> <span data-ttu-id="543a2-154">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="543a2-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="543a2-155">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="543a2-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="543a2-156">若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="543a2-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="543a2-157">如果 Enabled 屬性設定為 False，表示使用者目前未啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="543a2-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="543a2-158">目標使用者可能不在通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="543a2-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="543a2-159">通訊錄可能尚未完全更新及複製。</span><span class="sxs-lookup"><span data-stu-id="543a2-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="543a2-160">您可以執行下列命令，強制更新組織中的所有通訊錄服務器：</span><span class="sxs-lookup"><span data-stu-id="543a2-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

