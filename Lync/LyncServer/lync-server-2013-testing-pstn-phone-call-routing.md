---
title: Lync Server 2013：測試 PSTN 通話路由
description: Lync Server 2013：測試 PSTN 通話路由。
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
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556269"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="d26c4-103">在 Lync Server 2013 中測試 PSTN 撥打電話路由</span><span class="sxs-lookup"><span data-stu-id="d26c4-103">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d26c4-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="d26c4-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d26c4-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="d26c4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d26c4-106">每日</span><span class="sxs-lookup"><span data-stu-id="d26c4-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d26c4-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="d26c4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d26c4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d26c4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d26c4-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d26c4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d26c4-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d26c4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d26c4-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsInterTrunkRouting</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d26c4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="d26c4-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d26c4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d26c4-113">描述</span><span class="sxs-lookup"><span data-stu-id="d26c4-113">Description</span></span>

<span data-ttu-id="d26c4-114">**Test-CsInterTrunkRouting** Cmdlet 會驗證通話是否可以從一個 SIP 路由傳送到另一個 SIP。</span><span class="sxs-lookup"><span data-stu-id="d26c4-114">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="d26c4-115">若要這麼做，指令指令會獲得一個電話號碼和主幹設定。</span><span class="sxs-lookup"><span data-stu-id="d26c4-115">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="d26c4-116">**Test-CsInterTrunkRouting** 會向後報告指定數目的對應路由和對應 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="d26c4-116">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="d26c4-117">請注意，只有當主幹具有符合指定電話號碼的號碼模式，且只有在主幹共用至少一個 PSTN 使用方式時，才可以在主幹之間路由傳送通話。</span><span class="sxs-lookup"><span data-stu-id="d26c4-117">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d26c4-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="d26c4-118">Running the test</span></span>

<span data-ttu-id="d26c4-119">下列所示的命令會傳回相符的路由和對應的電話使用方式，讓使用者能夠使用 Redmond 網站的主幹設定來呼叫電話號碼1-206-555-1219。</span><span class="sxs-lookup"><span data-stu-id="d26c4-119">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d26c4-120">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="d26c4-120">Determining success or failure</span></span>

<span data-ttu-id="d26c4-121">如果呼叫可以從一個 SIP 路由傳送到另一個 SIP，您會收到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="d26c4-121">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="d26c4-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="d26c4-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="d26c4-123">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="d26c4-123">\------------------ ------------- --------------</span></span>

<span data-ttu-id="d26c4-124">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="d26c4-124">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="d26c4-125">如果測試失敗，您會收到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="d26c4-125">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="d26c4-126">Test-CsInterTrunkRouting：無法在參數上處理引數轉換</span><span class="sxs-lookup"><span data-stu-id="d26c4-126">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="d26c4-127">' TrunkConfiguration '。</span><span class="sxs-lookup"><span data-stu-id="d26c4-127">'TrunkConfiguration'.</span></span> <span data-ttu-id="d26c4-128">TrunkConfigurationsetting (參數) 無效。</span><span class="sxs-lookup"><span data-stu-id="d26c4-128">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="d26c4-129">指定</span><span class="sxs-lookup"><span data-stu-id="d26c4-129">Specify a</span></span>

<span data-ttu-id="d26c4-130">有效的設定 (參數) 然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="d26c4-130">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="d26c4-131">位於：1個字元：79</span><span class="sxs-lookup"><span data-stu-id="d26c4-131">At line:1 char:79</span></span>

<span data-ttu-id="d26c4-132">\+ Test-CsInterTrunkRouting-TargetNumber "電話： + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="d26c4-132">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="d26c4-133">\-TrunkConfiguration $t</span><span class="sxs-lookup"><span data-stu-id="d26c4-133">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="d26c4-134">\+ CategoryInfo： InvalidData： (： ) \[ Test-CsInterTrunkRouting \] ，Par</span><span class="sxs-lookup"><span data-stu-id="d26c4-134">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="d26c4-135">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="d26c4-135">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="d26c4-136">\+ FullyQualifiedErrorId： ParameterArgumentTransformationError，Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d26c4-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="d26c4-137">Tc。TestOcsInterTrunkRoutingCmdlet 的管理</span><span class="sxs-lookup"><span data-stu-id="d26c4-137">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d26c4-138">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="d26c4-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="d26c4-139">以下是一些 **Test-CsInterTrunkRouting** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="d26c4-139">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="d26c4-140">您指定的參數無效。</span><span class="sxs-lookup"><span data-stu-id="d26c4-140">You specified invalid parameters.</span></span> <span data-ttu-id="d26c4-141">主幹可能尚未正確設定，且指定的目標號碼可能不正確或無效。</span><span class="sxs-lookup"><span data-stu-id="d26c4-141">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d26c4-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d26c4-142">See Also</span></span>


[<span data-ttu-id="d26c4-143">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="d26c4-143">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="d26c4-144">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="d26c4-144">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

