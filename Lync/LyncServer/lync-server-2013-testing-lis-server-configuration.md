---
title: Lync Server 2013：測試 .LIS 伺服器設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3c99e9f10f98d93af73869d166c33a27e9ce18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="837ad-102">在 Lync Server 2013 中測試 IIS 伺服器設定</span><span class="sxs-lookup"><span data-stu-id="837ad-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="837ad-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="837ad-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="837ad-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="837ad-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="837ad-105">日常</span><span class="sxs-lookup"><span data-stu-id="837ad-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="837ad-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="837ad-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="837ad-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="837ad-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="837ad-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="837ad-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="837ad-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="837ad-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="837ad-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsLisConfiguration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="837ad-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="837ad-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="837ad-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="837ad-112">說明</span><span class="sxs-lookup"><span data-stu-id="837ad-112">Description</span></span>

<span data-ttu-id="837ad-113">CsLisConfiguration Cmdlet 會驗證您是否可以與 IIS 網站服務取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="837ad-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="837ad-114">如果可以取得 web 服務，則無論是否找到任何特定位置，都會認為測試是成功的。</span><span class="sxs-lookup"><span data-stu-id="837ad-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="837ad-115">執行測試</span><span class="sxs-lookup"><span data-stu-id="837ad-115">Running the test</span></span>

<span data-ttu-id="837ad-116">CsLisConfguration Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="837ad-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="837ad-117">若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="837ad-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="837ad-118">例如：</span><span class="sxs-lookup"><span data-stu-id="837ad-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="837ad-119">若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="837ad-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="837ad-120">當您呼叫 Test CsLisConfiguration 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="837ad-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="837ad-121">如需詳細資訊，請參閱[Test CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="837ad-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="837ad-122">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="837ad-122">Determining success or failure</span></span>

<span data-ttu-id="837ad-123">如果 .LIS 的設定正確，您將會收到與此類似的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="837ad-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="837ad-124">TargetUri :https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="837ad-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="837ad-125">liservice （.svc）</span><span class="sxs-lookup"><span data-stu-id="837ad-125">liservice.svc</span></span>

<span data-ttu-id="837ad-126">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="837ad-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="837ad-127">結果：成功</span><span class="sxs-lookup"><span data-stu-id="837ad-127">Result : Success</span></span>

<span data-ttu-id="837ad-128">延隔時間：00：00：06.1616913</span><span class="sxs-lookup"><span data-stu-id="837ad-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="837ad-129">出錯</span><span class="sxs-lookup"><span data-stu-id="837ad-129">Error :</span></span>

<span data-ttu-id="837ad-130">自檢</span><span class="sxs-lookup"><span data-stu-id="837ad-130">Diagnosis :</span></span>

<span data-ttu-id="837ad-131">如果指定的使用者無法登入或登出，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="837ad-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="837ad-132">TargetUri :</span><span class="sxs-lookup"><span data-stu-id="837ad-132">TargetUri :</span></span>

<span data-ttu-id="837ad-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="837ad-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="837ad-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="837ad-134">Result : Failure</span></span>

<span data-ttu-id="837ad-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="837ad-135">Latency : 00:00:00</span></span>

<span data-ttu-id="837ad-136">錯誤：11004，要求的名稱有效，但沒有要求的資料</span><span class="sxs-lookup"><span data-stu-id="837ad-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="837ad-137">已找到類型</span><span class="sxs-lookup"><span data-stu-id="837ad-137">type was found</span></span>

<span data-ttu-id="837ad-138">自檢</span><span class="sxs-lookup"><span data-stu-id="837ad-138">Diagnosis :</span></span>

<span data-ttu-id="837ad-139">Test-CsLisConfiguration：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="837ad-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="837ad-140">例如，前一個輸出包含「在拓撲中找不到相符的群集」的筆記。</span><span class="sxs-lookup"><span data-stu-id="837ad-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="837ad-141">這通常表示邊緣伺服器的問題：使用 Edge 伺服器來連線至服務提供者並驗證位址的 IIS 類型。</span><span class="sxs-lookup"><span data-stu-id="837ad-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="837ad-142">如果測試 CsLisConfiguration 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="837ad-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="837ad-143">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsLisConfiguration 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="837ad-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="837ad-144">例如：</span><span class="sxs-lookup"><span data-stu-id="837ad-144">For example:</span></span>

<span data-ttu-id="837ad-145">呼叫位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="837ad-145">Calling Location Information Service.</span></span>

<span data-ttu-id="837ad-146">服務路徑 =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="837ad-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="837ad-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="837ad-147">Subnet =</span></span>

<span data-ttu-id="837ad-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="837ad-148">BssId = 5</span></span>

<span data-ttu-id="837ad-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="837ad-149">ChassisId =</span></span>

<span data-ttu-id="837ad-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="837ad-150">PortId =</span></span>

<span data-ttu-id="837ad-151">PortIdSubType = 未定義的類型</span><span class="sxs-lookup"><span data-stu-id="837ad-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="837ad-152">版</span><span class="sxs-lookup"><span data-stu-id="837ad-152">Mac</span></span>

<span data-ttu-id="837ad-153">例外 ' 位置資訊 Web 服務要求失敗，回應碼 Item400。」</span><span class="sxs-lookup"><span data-stu-id="837ad-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="837ad-154">在工作流程 SyntheticTrsnactions STLisConfigurationWorkflow 執行期間發生。</span><span class="sxs-lookup"><span data-stu-id="837ad-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="837ad-155">如果您仔細檢查先前的輸出，您會發現 Cmdlet 在嘗試呼叫位置資訊服務之後失敗。</span><span class="sxs-lookup"><span data-stu-id="837ad-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="837ad-156">該呼叫中使用的其中一個參數就是：</span><span class="sxs-lookup"><span data-stu-id="837ad-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="837ad-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="837ad-157">BssId = 5</span></span>

<span data-ttu-id="837ad-158">這個值不是基本服務組識別元（BssID）的有效值。</span><span class="sxs-lookup"><span data-stu-id="837ad-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="837ad-159">相反地，BssID 應如下所示：</span><span class="sxs-lookup"><span data-stu-id="837ad-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="837ad-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="837ad-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="837ad-161">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="837ad-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="837ad-162">以下是測試 CsLisConfiguration 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="837ad-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="837ad-163">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="837ad-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="837ad-164">如上一個範例所示，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="837ad-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="837ad-165">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="837ad-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

