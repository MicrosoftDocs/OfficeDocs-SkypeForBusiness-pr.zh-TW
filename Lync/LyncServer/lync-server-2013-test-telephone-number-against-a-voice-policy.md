---
title: Lync Server 2013：對照語音原則測試電話號碼
description: Lync Server 2013：對照語音原則測試電話號碼。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a6523e7657bd4c30c23909bb02e2569b6067298
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548029"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="ee121-103">在 Lync Server 2013 中對照語音原則測試電話號碼</span><span class="sxs-lookup"><span data-stu-id="ee121-103">Test telephone number against a voice policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee121-104">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="ee121-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee121-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ee121-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ee121-106">每月</span><span class="sxs-lookup"><span data-stu-id="ee121-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee121-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="ee121-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ee121-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee121-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee121-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="ee121-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ee121-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ee121-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ee121-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoicePolicy Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ee121-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="ee121-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ee121-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ee121-113">描述</span><span class="sxs-lookup"><span data-stu-id="ee121-113">Description</span></span>

<span data-ttu-id="ee121-114">企業語音使用者透過公用交換電話網路撥打撥出電話的能力 (PSTN) 樞，在很大的情況下，有三種情況：</span><span class="sxs-lookup"><span data-stu-id="ee121-114">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="ee121-115">指派給使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="ee121-115">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="ee121-116">用於將呼叫從 Lync Server 路由傳送至 PSTN 網路的語音路由。</span><span class="sxs-lookup"><span data-stu-id="ee121-116">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="ee121-117">PSTN 使用方式，即將語音原則連線至語音路由的 Lync Server 屬性。</span><span class="sxs-lookup"><span data-stu-id="ee121-117">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="ee121-118">PSTN 使用方式尤為重要：它是將語音原則連線到語音路由的屬性。</span><span class="sxs-lookup"><span data-stu-id="ee121-118">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="ee121-119"> (語音原則和語音路由稱為已連接，但其共有至少一個 PSTN 使用情形。 ) 語音原則可以設定，但不指定 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="ee121-119">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="ee121-120">在此情況下，已獲指派該原則的使用者將無法透過 PSTN 網路撥出電話。</span><span class="sxs-lookup"><span data-stu-id="ee121-120">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="ee121-121">同樣地，沒有至少一個指定 PSTN 使用方式的語音路由，也無法將通話路由傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="ee121-121">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="ee121-122">Test-CsVoicePolicy Cmdlet 會驗證指定的語音原則是否有 PSTN 使用狀況，以及其使用方式是否至少由一個語音路由所共用。</span><span class="sxs-lookup"><span data-stu-id="ee121-122">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="ee121-123">如果 Test-CsVoicePolicy 成功執行驗證，指令程式會傳回找到的第一個有效語音路由的名稱，也會傳回將原則連接至路由的 PSTN 使用名稱。</span><span class="sxs-lookup"><span data-stu-id="ee121-123">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ee121-124">執行測試</span><span class="sxs-lookup"><span data-stu-id="ee121-124">Running the test</span></span>

<span data-ttu-id="ee121-125">若要執行 Test-CsVoicePolicy 指令程式，您必須先使用 Get-CsVoicePolicy Cmdlet，以找回要測試之語音原則的實例;然後，必須將該實例管線傳送至 Test-Set-csvoicepolicy。</span><span class="sxs-lookup"><span data-stu-id="ee121-125">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="ee121-126">例如：</span><span class="sxs-lookup"><span data-stu-id="ee121-126">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="ee121-127">請注意，此命令不會使用 Get-CsVoicePolicy 來取得語音原則實例，否則會失敗：</span><span class="sxs-lookup"><span data-stu-id="ee121-127">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="ee121-128">如果您想要根據指定的電話號碼檢查所有語音原則，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="ee121-128">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="ee121-129">請注意，必須使用 e.164 格式來指定 TargetNumber。</span><span class="sxs-lookup"><span data-stu-id="ee121-129">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="ee121-130">Test-CsVoicePolicy 不會嘗試將電話號碼正常化或轉譯為 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="ee121-130">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="ee121-131">如需詳細資訊，請參閱 Test-CsVoicePolicy Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ee121-131">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ee121-132">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ee121-132">Determining success or failure</span></span>

<span data-ttu-id="ee121-133">若語音原則可以找到相符的語音路由和相符的 PSTN 使用，則會在螢幕上顯示路由和使用狀況：</span><span class="sxs-lookup"><span data-stu-id="ee121-133">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="ee121-134">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="ee121-134">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="ee121-135">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="ee121-135">\------------------ -------------</span></span>

<span data-ttu-id="ee121-136">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="ee121-136">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="ee121-137">如果找不到適當的語音路由或適當的 PSTN 使用方式，將會在螢幕上顯示空白的屬性值：</span><span class="sxs-lookup"><span data-stu-id="ee121-137">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="ee121-138">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="ee121-138">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="ee121-139">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="ee121-139">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ee121-140">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ee121-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="ee121-141">如果 Test-CsVoicePolicy 未傳回可能表示語音原則與語音路由不共用 PSTN 使用狀況的相符。</span><span class="sxs-lookup"><span data-stu-id="ee121-141">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="ee121-142">若要驗證，請使用類似下列的指令程式，以驗證指派給語音原則的 PSTN 使用方式：</span><span class="sxs-lookup"><span data-stu-id="ee121-142">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="ee121-143">接下來，執行此命令以判斷 PSTN 使用方式指派給每個語音路由：</span><span class="sxs-lookup"><span data-stu-id="ee121-143">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="ee121-144">如果您看到任何相符 (，也就是，如果您看到一或多個語音路由，其至少共用一個 PSTN 使用方式與您的語音原則) ，則應該執行 Test-CsVoiceRoute Cmdlet，以確認語音路由可以撥打所提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ee121-144">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee121-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee121-145">See Also</span></span>


[<span data-ttu-id="ee121-146">測試-Set-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="ee121-146">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

