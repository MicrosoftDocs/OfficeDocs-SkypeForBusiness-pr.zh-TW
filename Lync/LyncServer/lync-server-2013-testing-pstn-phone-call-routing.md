---
title: Lync Server 2013： 測試 PSTN 電話路由
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
ms.openlocfilehash: abdb6796139ddc4be2b8ea24aa9bfeb19f745373
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="32636-102">測試 Lync Server 2013 中的 PSTN 電話路由</span><span class="sxs-lookup"><span data-stu-id="32636-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32636-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="32636-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32636-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="32636-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="32636-105">每日</span><span class="sxs-lookup"><span data-stu-id="32636-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32636-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="32636-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="32636-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="32636-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32636-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="32636-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="32636-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="32636-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="32636-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csintertrunkrouting</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="32636-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="32636-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="32636-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="32636-112">說明</span><span class="sxs-lookup"><span data-stu-id="32636-112">Description</span></span>

<span data-ttu-id="32636-113">**Test-csintertrunkrouting** cmdlet 會驗證通話可以路由從一個 SIP，到另一個。</span><span class="sxs-lookup"><span data-stu-id="32636-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="32636-114">若要這麼做，指令程式提供的電話號碼及主幹組態。</span><span class="sxs-lookup"><span data-stu-id="32636-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="32636-115">**Test-csintertrunkrouting**會然後回報相符的路由和相符的 PSTN 使用方式指定數目。</span><span class="sxs-lookup"><span data-stu-id="32636-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="32636-116">請注意，可以來路由傳送通話主幹間僅有主幹的數字模式符合指定的電話號碼，且只有在主幹共用至少一個 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="32636-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="32636-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="32636-117">Running the test</span></span>

<span data-ttu-id="32636-118">如下所示的命令會傳回相符的路由和相符的電話使用方式，讓使用者能夠呼叫的主幹組態設定用於 Redmond 網站的電話號碼 1-206-555-1219。</span><span class="sxs-lookup"><span data-stu-id="32636-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="32636-119">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="32636-119">Determining success or failure</span></span>

<span data-ttu-id="32636-120">如果呼叫可以從一個 SIP 路由傳送至另一個，您會收到類似如下的輸出：</span><span class="sxs-lookup"><span data-stu-id="32636-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="32636-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="32636-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="32636-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="32636-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="32636-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="32636-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="32636-124">如果測試失敗，您會收到類似如下的輸出：</span><span class="sxs-lookup"><span data-stu-id="32636-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="32636-125">Test-csintertrunkrouting： 無法處理上參數的引數轉換</span><span class="sxs-lookup"><span data-stu-id="32636-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="32636-126">' TrunkConfiguration'。</span><span class="sxs-lookup"><span data-stu-id="32636-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="32636-127">無效的 TrunkConfigurationsetting （參數）。</span><span class="sxs-lookup"><span data-stu-id="32636-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="32636-128">指定</span><span class="sxs-lookup"><span data-stu-id="32636-128">Specify a</span></span>

<span data-ttu-id="32636-129">有效的設定 （參數），然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="32636-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="32636-130">在線條： 1 char: 79</span><span class="sxs-lookup"><span data-stu-id="32636-130">At line:1 char:79</span></span>

<span data-ttu-id="32636-131">\+Test-csintertrunkrouting TargetNumber"tel: + 12065551219 」</span><span class="sxs-lookup"><span data-stu-id="32636-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="32636-132">\-TrunkConfiguration $t...]</span><span class="sxs-lookup"><span data-stu-id="32636-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="32636-133">\+CategoryInfo: InvalidData: （:）\[Test-csintertrunkrouting\]、 Par</span><span class="sxs-lookup"><span data-stu-id="32636-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="32636-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="32636-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="32636-135">\+FullyQualifiedErrorId: ParameterArgumentTransformationError,Microsoft.R</span><span class="sxs-lookup"><span data-stu-id="32636-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="32636-136">繁體中文。Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="32636-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="32636-137">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="32636-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="32636-138">以下是一些常見的原因為何**Test-csintertrunkrouting**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="32636-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="32636-139">您指定無效的參數。</span><span class="sxs-lookup"><span data-stu-id="32636-139">You specified invalid parameters.</span></span> <span data-ttu-id="32636-140">主幹可能尚未被設定不正確，指定的目標數字可能不正確或不正確。</span><span class="sxs-lookup"><span data-stu-id="32636-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32636-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32636-141">See Also</span></span>


[<span data-ttu-id="32636-142">Get-cstrunk</span><span class="sxs-lookup"><span data-stu-id="32636-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="32636-143">Get-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="32636-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

