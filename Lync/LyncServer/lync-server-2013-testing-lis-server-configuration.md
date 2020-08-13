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
ms.openlocfilehash: 50b2908b3f2403cc59f4cb7ce26f176d366ce2e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="e0a0f-102">在 Lync Server 2013 中測試 .LIS 伺服器設定</span><span class="sxs-lookup"><span data-stu-id="e0a0f-102">Testing LIS server configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0a0f-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e0a0f-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0a0f-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="e0a0f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e0a0f-105">每日</span><span class="sxs-lookup"><span data-stu-id="e0a0f-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0a0f-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="e0a0f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e0a0f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0a0f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0a0f-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e0a0f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e0a0f-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e0a0f-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsLisConfiguration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="e0a0f-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e0a0f-112">描述</span><span class="sxs-lookup"><span data-stu-id="e0a0f-112">Description</span></span>

<span data-ttu-id="e0a0f-113">Test-CsLisConfiguration Cmdlet 會驗證您是否可以聯繫 .LIS web 服務。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-113">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="e0a0f-114">如果可以聯繫 web 服務，則不論是否可以找到任何特定位置，都可以將測試視為成功。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-114">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e0a0f-115">執行測試</span><span class="sxs-lookup"><span data-stu-id="e0a0f-115">Running the test</span></span>

<span data-ttu-id="e0a0f-116">CsLisConfguration Cmdlet 可使用預先設定的測試帳戶執行 (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何已啟用 Lync Server 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-116">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="e0a0f-117">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-117">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e0a0f-118">例如：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-118">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e0a0f-119">若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-119">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="e0a0f-120">接著，當您呼叫 Test-CsLisConfiguration 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-120">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e0a0f-121">如需詳細資訊，請參閱[Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-121">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e0a0f-122">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="e0a0f-122">Determining success or failure</span></span>

<span data-ttu-id="e0a0f-123">如果已正確設定 .LIS，您會收到類似下列的輸出，並將 Result 屬性標示為 [**成功]：**</span><span class="sxs-lookup"><span data-stu-id="e0a0f-123">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e0a0f-124">TargetUri：https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="e0a0f-124">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="e0a0f-125">liservice</span><span class="sxs-lookup"><span data-stu-id="e0a0f-125">liservice.svc</span></span>

<span data-ttu-id="e0a0f-126">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e0a0f-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e0a0f-127">結果：成功</span><span class="sxs-lookup"><span data-stu-id="e0a0f-127">Result : Success</span></span>

<span data-ttu-id="e0a0f-128">延遲：00：00：06.1616913</span><span class="sxs-lookup"><span data-stu-id="e0a0f-128">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="e0a0f-129">錯誤：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-129">Error :</span></span>

<span data-ttu-id="e0a0f-130">診斷：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-130">Diagnosis :</span></span>

<span data-ttu-id="e0a0f-131">如果指定的使用者無法登入或登出，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-131">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e0a0f-132">TargetUri：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-132">TargetUri :</span></span>

<span data-ttu-id="e0a0f-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e0a0f-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e0a0f-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="e0a0f-134">Result : Failure</span></span>

<span data-ttu-id="e0a0f-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="e0a0f-135">Latency : 00:00:00</span></span>

<span data-ttu-id="e0a0f-136">錯誤：11004，要求的名稱是有效的，但沒有要求的資料</span><span class="sxs-lookup"><span data-stu-id="e0a0f-136">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="e0a0f-137">找到類型</span><span class="sxs-lookup"><span data-stu-id="e0a0f-137">type was found</span></span>

<span data-ttu-id="e0a0f-138">診斷：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-138">Diagnosis :</span></span>

<span data-ttu-id="e0a0f-139">Test-CsLisConfiguration：在拓撲中找不到相符的集群。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-139">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="e0a0f-140">例如，上一個輸出包含「沒有搭配拓撲中找到的對應叢集」的附注。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-140">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="e0a0f-141">這通常表示 Edge Server 發生問題： .LIS 使用 Edge Server 來連線至服務提供者及驗證位址。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-141">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="e0a0f-142">如果 Test-CsLisConfiguration 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-142">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="e0a0f-143">包含 Verbose 參數時，Test-CsLisConfiguration 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-143">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e0a0f-144">例如：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-144">For example:</span></span>

<span data-ttu-id="e0a0f-145">呼叫位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-145">Calling Location Information Service.</span></span>

<span data-ttu-id="e0a0f-146">服務路徑 =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="e0a0f-146">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="e0a0f-147">Subnet =</span><span class="sxs-lookup"><span data-stu-id="e0a0f-147">Subnet =</span></span>

<span data-ttu-id="e0a0f-148">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="e0a0f-148">BssId = 5</span></span>

<span data-ttu-id="e0a0f-149">ChassisId =</span><span class="sxs-lookup"><span data-stu-id="e0a0f-149">ChassisId =</span></span>

<span data-ttu-id="e0a0f-150">PortId =</span><span class="sxs-lookup"><span data-stu-id="e0a0f-150">PortId =</span></span>

<span data-ttu-id="e0a0f-151">PortIdSubType = 未定義的類型</span><span class="sxs-lookup"><span data-stu-id="e0a0f-151">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="e0a0f-152">Mac</span><span class="sxs-lookup"><span data-stu-id="e0a0f-152">Mac</span></span>

<span data-ttu-id="e0a0f-153">例外 ' 位置資訊 Web 服務要求失敗，回應碼 Item400。 '</span><span class="sxs-lookup"><span data-stu-id="e0a0f-153">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="e0a0f-154">在工作流程 SyntheticTrsnactions 中發生 STLisConfigurationWorkflow 執行。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-154">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="e0a0f-155">如果您仔細檢查先前的輸出，您會發現 Cmdlet 在嘗試呼叫位置資訊服務後失敗。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-155">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="e0a0f-156">該呼叫中使用的其中一個參數是：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-156">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="e0a0f-157">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="e0a0f-157">BssId = 5</span></span>

<span data-ttu-id="e0a0f-158">這不是基本服務組識別碼的有效值 (BssID) 。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-158">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="e0a0f-159">相反地，BssID 應如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-159">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="e0a0f-160">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="e0a0f-160">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e0a0f-161">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="e0a0f-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="e0a0f-162">以下是一些 Test-CsLisConfiguration 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="e0a0f-162">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="e0a0f-163">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-163">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e0a0f-164">如先前的範例所示，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-164">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e0a0f-165">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="e0a0f-165">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

