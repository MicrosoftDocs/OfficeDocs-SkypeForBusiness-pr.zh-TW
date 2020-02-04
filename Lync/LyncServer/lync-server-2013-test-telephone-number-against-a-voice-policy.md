---
title: Lync Server 2013：根據語音原則測試電話號碼
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
ms.openlocfilehash: 37d0c9ae6512cb7755c7ef73e4cfd3e37b92884d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="fa587-102">在 Lync Server 2013 中根據語音原則測試電話號碼</span><span class="sxs-lookup"><span data-stu-id="fa587-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa587-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="fa587-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa587-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="fa587-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fa587-105">次</span><span class="sxs-lookup"><span data-stu-id="fa587-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa587-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="fa587-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fa587-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa587-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa587-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="fa587-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fa587-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fa587-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fa587-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoicePolicy Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="fa587-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="fa587-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fa587-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fa587-112">說明</span><span class="sxs-lookup"><span data-stu-id="fa587-112">Description</span></span>

<span data-ttu-id="fa587-113">企業語音使用者在公用交換電話網絡（PSTN）樞軸上撥打電話的能力，主要是在三個方面進行：</span><span class="sxs-lookup"><span data-stu-id="fa587-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="fa587-114">指派給使用者的語音原則。</span><span class="sxs-lookup"><span data-stu-id="fa587-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="fa587-115">用來從 Lync 伺服器將呼叫路由至 PSTN 網路的語音路由。</span><span class="sxs-lookup"><span data-stu-id="fa587-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="fa587-116">PSTN 使用量，即將語音原則連線到語音路由的 Lync Server 屬性。</span><span class="sxs-lookup"><span data-stu-id="fa587-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="fa587-117">PSTN 使用量特別重要：它是將語音原則連接至語音路線的屬性。</span><span class="sxs-lookup"><span data-stu-id="fa587-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="fa587-118">（語音原則和語音路線是在有至少一個 PSTN 用法的情況中說是連線）。語音原則無需指定 PSTN 用法即可加以設定。</span><span class="sxs-lookup"><span data-stu-id="fa587-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="fa587-119">在這種情況下，指派該原則的使用者將無法透過 PSTN 網路撥出通話。</span><span class="sxs-lookup"><span data-stu-id="fa587-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="fa587-120">同樣地，沒有指定 PSTN 使用的語音路由也無法將呼叫路由至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="fa587-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="fa587-121">CsVoicePolicy Cmdlet 會驗證指定的語音原則是否有 PSTN 使用狀況，以及此用法是由至少一個語音路由所共用。</span><span class="sxs-lookup"><span data-stu-id="fa587-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="fa587-122">如果由 Test CsVoicePolicy 的驗證執行成功，則 Cmdlet 會傳回所找到的第一個有效語音路由的名稱，以及將原則連接到路線的 PSTN 使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="fa587-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fa587-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="fa587-123">Running the test</span></span>

<span data-ttu-id="fa587-124">若要執行 Test CsVoicePolicy Cmdlet，您必須先使用 CsVoicePolicy Cmdlet 來檢索要測試的語音原則實例;然後必須將該實例以管道傳送給 Test CsVoicePolicy。</span><span class="sxs-lookup"><span data-stu-id="fa587-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="fa587-125">例如：</span><span class="sxs-lookup"><span data-stu-id="fa587-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="fa587-126">請注意，這個命令不會使用 CsVoicePolicy 來檢索語音原則實例，將會失敗：</span><span class="sxs-lookup"><span data-stu-id="fa587-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="fa587-127">如果您想要根據指定的電話號碼來檢查所有語音原則，請使用類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="fa587-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="fa587-128">請注意，您必須使用 E.i 格式來指定 TargetNumber。</span><span class="sxs-lookup"><span data-stu-id="fa587-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="fa587-129">CsVoicePolicy 不會嘗試將電話號碼標準化或轉換為 e. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="fa587-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="fa587-130">如需詳細資訊，請參閱 Test CsVoicePolicy Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="fa587-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fa587-131">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="fa587-131">Determining success or failure</span></span>

<span data-ttu-id="fa587-132">如果語音原則可以找到相符的語音路由及相符的 PSTN 使用，則會在螢幕上顯示路由與使用方式：</span><span class="sxs-lookup"><span data-stu-id="fa587-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="fa587-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="fa587-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="fa587-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="fa587-134">\------------------ -------------</span></span>

<span data-ttu-id="fa587-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="fa587-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="fa587-136">如果找不到合適的語音路線或適當的 PSTN 使用量，螢幕上就會顯示空白屬性值：</span><span class="sxs-lookup"><span data-stu-id="fa587-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="fa587-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="fa587-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="fa587-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="fa587-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fa587-139">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="fa587-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="fa587-140">如果 Test CsVoicePolicy 沒有傳回一個相符的值，這可能表示語音原則不會與語音路線共用 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="fa587-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="fa587-141">若要驗證，請使用類似下列的 Cmdlet 來驗證指派給語音原則的 PSTN 用法：</span><span class="sxs-lookup"><span data-stu-id="fa587-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="fa587-142">接著，執行這個命令來判斷 PSTN 用法指派給每個語音路由：</span><span class="sxs-lookup"><span data-stu-id="fa587-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="fa587-143">如果您看到任何相符的專案（也就是，如果您看到一個或多個與您的語音原則共用至少一個 PSTN 的語音路由），您就應該執行 CsVoiceRoute Cmdlet，以確認語音路由可以撥打所提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fa587-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa587-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="fa587-144">See Also</span></span>


[<span data-ttu-id="fa587-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="fa587-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

