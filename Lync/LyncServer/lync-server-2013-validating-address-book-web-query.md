---
title: Lync Server 2013：驗證通訊錄網頁查詢
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c43b4332be67bb164f21a2bb07459d61b23e85
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="6914e-102">在 Lync Server 2013 中驗證通訊錄網頁查詢</span><span class="sxs-lookup"><span data-stu-id="6914e-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6914e-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6914e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6914e-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="6914e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6914e-105">日常</span><span class="sxs-lookup"><span data-stu-id="6914e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6914e-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="6914e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6914e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6914e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6914e-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="6914e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6914e-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6914e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6914e-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsAddressBookWebQuery Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="6914e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="6914e-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6914e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6914e-112">描述</span><span class="sxs-lookup"><span data-stu-id="6914e-112">Description</span></span>

<span data-ttu-id="6914e-113">CsAddressBookWebQuery Cmdlet 可讓系統管理員確認使用者可以使用通訊錄網頁查詢服務來搜尋特定的連絡人。</span><span class="sxs-lookup"><span data-stu-id="6914e-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="6914e-114">當您執行 Cmdlet 時，測試 CsAddressBookWebQuery 會先連線到要驗證的 Web 票證服務。</span><span class="sxs-lookup"><span data-stu-id="6914e-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="6914e-115">如果驗證成功，則 Cmdlet 會連線至通訊錄網頁查詢服務，並搜尋指定的連絡人。</span><span class="sxs-lookup"><span data-stu-id="6914e-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="6914e-116">如果找到該連絡人，則 Cmdlet 會嘗試將該資訊傳回本機電腦。</span><span class="sxs-lookup"><span data-stu-id="6914e-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="6914e-117">只有在所有這些步驟都能完成時，才會將測試標示為成功。</span><span class="sxs-lookup"><span data-stu-id="6914e-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="6914e-118">如需詳細資訊，請參閱[Test CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="6914e-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6914e-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="6914e-119">Running the test</span></span>

<span data-ttu-id="6914e-120">CsAddressBookWebQuery Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="6914e-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="6914e-121">若要使用測試帳戶執行這項檢查，您只需指定 Lync Server pool 的 FQDN，以及充當搜尋目標之使用者的 SIP 位址即可。</span><span class="sxs-lookup"><span data-stu-id="6914e-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="6914e-122">例如：</span><span class="sxs-lookup"><span data-stu-id="6914e-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="6914e-123">若要使用實際的使用者帳戶執行此檢查，您必須建立包含有效使用者名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="6914e-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="6914e-124">接著，當程式碼呼叫 Test-CsAddressBookWebQuery 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="6914e-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6914e-125">如需詳細資訊，請參閱[Test CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="6914e-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6914e-126">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="6914e-126">Determining success or failure</span></span>

<span data-ttu-id="6914e-127">如果指定的使用者可以連線到通訊錄服務並檢索目標使用者位址，您將會傳回類似以下所示的輸出，並將 Result 屬性標示為成功：</span><span class="sxs-lookup"><span data-stu-id="6914e-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="6914e-128">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6914e-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="6914e-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6914e-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6914e-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="6914e-130">Result : Success</span></span>

<span data-ttu-id="6914e-131">延隔時間：00：00：06.2611356</span><span class="sxs-lookup"><span data-stu-id="6914e-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="6914e-132">出錯</span><span class="sxs-lookup"><span data-stu-id="6914e-132">Error :</span></span>

<span data-ttu-id="6914e-133">自檢</span><span class="sxs-lookup"><span data-stu-id="6914e-133">Diagnosis :</span></span>

<span data-ttu-id="6914e-134">如果指定的使用者無法連線，或者如果無法檢索目標使用者位址，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="6914e-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6914e-135">TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6914e-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="6914e-136">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6914e-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6914e-137">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="6914e-137">Result : Failure</span></span>

<span data-ttu-id="6914e-138">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="6914e-138">Latency : 00:00:00</span></span>

<span data-ttu-id="6914e-139">錯誤：通訊錄 Web 服務要求失敗，回應代碼為</span><span class="sxs-lookup"><span data-stu-id="6914e-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="6914e-140">NoEntryFound.</span><span class="sxs-lookup"><span data-stu-id="6914e-140">NoEntryFound.</span></span>

<span data-ttu-id="6914e-141">自檢</span><span class="sxs-lookup"><span data-stu-id="6914e-141">Diagnosis :</span></span>

<span data-ttu-id="6914e-142">先前的輸出指出由於找不到目標使用者，測試失敗。</span><span class="sxs-lookup"><span data-stu-id="6914e-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="6914e-143">您可以執行如下所示的命令，判斷是否已將有效的 SIP 位址傳遞到 Test CsAddressBookWebQuery：</span><span class="sxs-lookup"><span data-stu-id="6914e-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="6914e-144">如果測試 CsAddressBookWebQuery 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="6914e-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="6914e-145">在包含詳細參數時，測試 CsAddressBookWebQuery 會傳回其在檢查指定使用者登入 Lync Server 的功能時所嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="6914e-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="6914e-146">例如，此輸出表示測試 CsAddressBookWebQuery 能夠連線至通訊錄服務，但無法找出目標 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="6914e-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="6914e-147">「QueryAddressBookWebService」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="6914e-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="6914e-148">呼叫通訊錄網頁查詢服務。</span><span class="sxs-lookup"><span data-stu-id="6914e-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="6914e-149">ABWS URL =</span><span class="sxs-lookup"><span data-stu-id="6914e-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="6914e-150">通訊錄查詢例外狀況：通訊錄 Web 服務要求失敗，回應碼 NoEntryFound。</span><span class="sxs-lookup"><span data-stu-id="6914e-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6914e-151">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="6914e-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="6914e-152">以下是測試 CsAddressBookWebQuery 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="6914e-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="6914e-153">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="6914e-153">You specified an invalid user account.</span></span> <span data-ttu-id="6914e-154">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="6914e-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6914e-155">使用者帳戶有效，但目前沒有為 Lync Server 啟用該帳戶。</span><span class="sxs-lookup"><span data-stu-id="6914e-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="6914e-156">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="6914e-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6914e-157">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6914e-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="6914e-158">目標使用者可能不在通訊錄中。</span><span class="sxs-lookup"><span data-stu-id="6914e-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="6914e-159">通訊錄可能未完全更新及複製。</span><span class="sxs-lookup"><span data-stu-id="6914e-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="6914e-160">您可以執行下列命令，強制更新貴組織中的所有通訊錄服務器：</span><span class="sxs-lookup"><span data-stu-id="6914e-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

