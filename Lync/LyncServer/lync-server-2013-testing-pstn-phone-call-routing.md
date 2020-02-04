---
title: Lync Server 2013：測試 PSTN 手機通話路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="49912-102">在 Lync Server 2013 中測試 PSTN 手機通話路由</span><span class="sxs-lookup"><span data-stu-id="49912-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49912-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="49912-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49912-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="49912-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="49912-105">日常</span><span class="sxs-lookup"><span data-stu-id="49912-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49912-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="49912-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="49912-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49912-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49912-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="49912-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="49912-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="49912-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="49912-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsInterTrunkRouting</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="49912-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="49912-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="49912-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="49912-112">說明</span><span class="sxs-lookup"><span data-stu-id="49912-112">Description</span></span>

<span data-ttu-id="49912-113">**CsInterTrunkRouting** Cmdlet 會確認呼叫可以從一個 SIP 路由到另一個 SIP。</span><span class="sxs-lookup"><span data-stu-id="49912-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="49912-114">若要這樣做，就會將 Cmdlet 提供給電話號碼和幹線設定。</span><span class="sxs-lookup"><span data-stu-id="49912-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="49912-115">然後，**測試 CsInterTrunkRouting**接著會針對指定的數位報告返回相符的路線及相符的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="49912-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="49912-116">請注意，只有當 trunks 的數位模式符合指定的電話號碼，且只有 trunks 共用至少一個 PSTN 使用量時，才可以在 trunks 之間路由通話。</span><span class="sxs-lookup"><span data-stu-id="49912-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="49912-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="49912-117">Running the test</span></span>

<span data-ttu-id="49912-118">下列所示的命令會傳回相符的路線及相符的電話用法，讓使用者使用雷德蒙者網站的幹線設定設定撥打電話號碼1-206-555-1219。</span><span class="sxs-lookup"><span data-stu-id="49912-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="49912-119">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="49912-119">Determining success or failure</span></span>

<span data-ttu-id="49912-120">如果可以將呼叫從一個 SIP 路由到另一個 SIP，您會收到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="49912-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="49912-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="49912-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="49912-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="49912-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="49912-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="49912-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="49912-124">如果測試沒有成功，您會收到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="49912-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="49912-125">測試-CsInterTrunkRouting：無法處理參數上的引數轉換</span><span class="sxs-lookup"><span data-stu-id="49912-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="49912-126">'TrunkConfiguration'.</span><span class="sxs-lookup"><span data-stu-id="49912-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="49912-127">不正確 TrunkConfigurationsetting （參數）。</span><span class="sxs-lookup"><span data-stu-id="49912-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="49912-128">指定</span><span class="sxs-lookup"><span data-stu-id="49912-128">Specify a</span></span>

<span data-ttu-id="49912-129">有效的設定（參數），然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="49912-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="49912-130">在第一行：1個字元：79</span><span class="sxs-lookup"><span data-stu-id="49912-130">At line:1 char:79</span></span>

<span data-ttu-id="49912-131">\+Test-CsInterTrunkRouting-TargetNumber "電話： + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="49912-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="49912-132">\-TrunkConfiguration $t .。。</span><span class="sxs-lookup"><span data-stu-id="49912-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="49912-133">\+CategoryInfo： InvalidData：（:)\[Test-CsInterTrunkRouting\]，Par</span><span class="sxs-lookup"><span data-stu-id="49912-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="49912-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="49912-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="49912-135">\+FullyQualifiedErrorId： ParameterArgumentTransformationError，Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="49912-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="49912-136">目錄.TestOcsInterTrunkRoutingCmdlet 的管理</span><span class="sxs-lookup"><span data-stu-id="49912-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="49912-137">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="49912-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="49912-138">以下是**測試 CsInterTrunkRouting**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="49912-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="49912-139">您指定的參數無效。</span><span class="sxs-lookup"><span data-stu-id="49912-139">You specified invalid parameters.</span></span> <span data-ttu-id="49912-140">主幹可能尚未正確設定，且指定的目標號碼可能不正確或無效。</span><span class="sxs-lookup"><span data-stu-id="49912-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49912-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="49912-141">See Also</span></span>


[<span data-ttu-id="49912-142">CsTrunk</span><span class="sxs-lookup"><span data-stu-id="49912-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="49912-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="49912-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

