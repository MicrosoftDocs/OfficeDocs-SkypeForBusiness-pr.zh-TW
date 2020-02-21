---
title: Lync Server 2013： 測試的語音原則針對電話號碼
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
ms.openlocfilehash: d22c801c7d08c3df663f69df07a6c73a5f17f858
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="c21c3-102">針對 Lync Server 2013 中的語音原則測試電話號碼</span><span class="sxs-lookup"><span data-stu-id="c21c3-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c21c3-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="c21c3-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c21c3-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="c21c3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c21c3-105">每月</span><span class="sxs-lookup"><span data-stu-id="c21c3-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c21c3-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="c21c3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c21c3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c21c3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c21c3-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="c21c3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c21c3-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c21c3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c21c3-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 CsVoicePolicy cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c21c3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="c21c3-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c21c3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c21c3-112">說明</span><span class="sxs-lookup"><span data-stu-id="c21c3-112">Description</span></span>

<span data-ttu-id="c21c3-113">Enterprise Voice 使用者能夠透過公用交換電話網路 (PSTN) 撥出電話電話取決，在大型組件，下列三個動作：</span><span class="sxs-lookup"><span data-stu-id="c21c3-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="c21c3-114">指派給使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="c21c3-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="c21c3-115">從 Lync 伺服器用來將通話路由傳送至 PSTN 網路的語音路由。</span><span class="sxs-lookup"><span data-stu-id="c21c3-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="c21c3-116">PSTN 使用方式中，按一下 [連線到語音路由的語音原則的 Lync Server 屬性。</span><span class="sxs-lookup"><span data-stu-id="c21c3-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="c21c3-117">PSTN 使用方式，請務必特別是： 它是連線到語音路由的語音原則的屬性。</span><span class="sxs-lookup"><span data-stu-id="c21c3-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="c21c3-118">（語音原則和語音路由稱為有至少一個 PSTN 使用方式共通連接。）可以設定語音原則，但未指定 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="c21c3-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="c21c3-119">在此情況下，被指派該原則的使用者將無法透過 PSTN 網路撥出電話。</span><span class="sxs-lookup"><span data-stu-id="c21c3-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="c21c3-120">同樣地，語音路由，不需要至少一個指定的 PSTN 使用方式將無法將通話路由傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="c21c3-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="c21c3-121">測試 CsVoicePolicy cmdlet 會驗證指定的語音原則有 PSTN 使用方式和流量由至少一個語音路由共用。</span><span class="sxs-lookup"><span data-stu-id="c21c3-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="c21c3-122">如果驗證執行測試 CsVoicePolicy 成功，cmdlet 會回報它找到的第一個有效的語音路由的名稱以及 PSTN 使用方式路由所連線之原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c21c3-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c21c3-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="c21c3-123">Running the test</span></span>

<span data-ttu-id="c21c3-124">若要執行測試 CsVoicePolicy 指令程式，您必須先使用 Get-csvoicepolicy cmdlet 擷取執行個體要測試; 的語音原則該執行個體必須接著會以管線傳輸至測試 CsVoicePolicy。</span><span class="sxs-lookup"><span data-stu-id="c21c3-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="c21c3-125">例如：</span><span class="sxs-lookup"><span data-stu-id="c21c3-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="c21c3-126">請注意，此命令，它不會使用 Get-csvoicepolicy 擷取語音原則執行個體，將會失敗：</span><span class="sxs-lookup"><span data-stu-id="c21c3-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="c21c3-127">如果您想要檢查針對指定的電話號碼的所有語音原則，然後使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="c21c3-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="c21c3-128">請注意，必須使用 E.164 格式來指定 TargetNumber。</span><span class="sxs-lookup"><span data-stu-id="c21c3-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="c21c3-129">測試 CsVoicePolicy 不會嘗試正規化的需求，或將電話號碼轉譯成 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="c21c3-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="c21c3-130">如需詳細資訊，請參閱 < 測試 CsVoicePolicy cmdlet 的說明 」 文件。</span><span class="sxs-lookup"><span data-stu-id="c21c3-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c21c3-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="c21c3-131">Determining success or failure</span></span>

<span data-ttu-id="c21c3-132">如果語音原則可以找到相符的語音路由和相符的 PSTN 使用方式，然後將螢幕上顯示的路由與用法：</span><span class="sxs-lookup"><span data-stu-id="c21c3-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="c21c3-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c21c3-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="c21c3-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="c21c3-134">\------------------ -------------</span></span>

<span data-ttu-id="c21c3-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="c21c3-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="c21c3-136">如果適當的語音路由或適當的 PSTN 使用方式找不到然後空白將螢幕上顯示屬性值：</span><span class="sxs-lookup"><span data-stu-id="c21c3-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="c21c3-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c21c3-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="c21c3-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="c21c3-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c21c3-139">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="c21c3-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="c21c3-140">如果測試 CsVoicePolicy 不會傳回表示的比對的語音原則不共用 PSTN 使用方式與語音路由。</span><span class="sxs-lookup"><span data-stu-id="c21c3-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="c21c3-141">若要確認，請使用類似下列的指令程式來驗證 PSTN 使用方式指派給語音原則：</span><span class="sxs-lookup"><span data-stu-id="c21c3-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="c21c3-142">接著，執行此命令，以決定 PSTN 使用方式將指派給每個語音路由：</span><span class="sxs-lookup"><span data-stu-id="c21c3-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="c21c3-143">如果您看到任何符合項目 （亦即，如果您看到您的語音原則和共用至少一個 PSTN 使用方式的一或多個語音路由），您應該再執行測試 CsVoiceRoute cmdlet 確認語音路由可以撥號對應表提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c21c3-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c21c3-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c21c3-144">See Also</span></span>


[<span data-ttu-id="c21c3-145">測試 CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="c21c3-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

