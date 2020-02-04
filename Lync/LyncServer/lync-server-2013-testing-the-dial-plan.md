---
title: Lync Server 2013：測試撥號計畫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0e39b88d7b6c90a55d236038d03cc4cc717319
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="0c46c-102">在 Lync Server 2013 中測試撥號方案</span><span class="sxs-lookup"><span data-stu-id="0c46c-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c46c-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0c46c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c46c-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="0c46c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0c46c-105">日常</span><span class="sxs-lookup"><span data-stu-id="0c46c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c46c-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="0c46c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0c46c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c46c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c46c-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="0c46c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0c46c-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0c46c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0c46c-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsDialPlan Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="0c46c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="0c46c-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0c46c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0c46c-112">說明</span><span class="sxs-lookup"><span data-stu-id="0c46c-112">Description</span></span>

<span data-ttu-id="0c46c-113">CsDialPlan Cmdlet 可讓您查看將撥號方案套用到指定電話號碼的結果。</span><span class="sxs-lookup"><span data-stu-id="0c46c-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="0c46c-114">撥號方案提供資訊（例如如何套用正常化規則），而必要的做法是讓企業語音使用者撥打電話。</span><span class="sxs-lookup"><span data-stu-id="0c46c-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="0c46c-115">考慮撥入號碼和撥號方案，這個 Cmdlet 會確認將套用撥號計畫中的哪個正常化規則，以及翻譯後的數位。</span><span class="sxs-lookup"><span data-stu-id="0c46c-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="0c46c-116">您可以使用這個 Cmdlet 來排查數位翻譯的問題，或驗證如何將規則套用至特定的數位。</span><span class="sxs-lookup"><span data-stu-id="0c46c-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0c46c-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="0c46c-117">Running the test</span></span>

<span data-ttu-id="0c46c-118">CsDialPlan Cmdlet 需要您執行兩項操作。</span><span class="sxs-lookup"><span data-stu-id="0c46c-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="0c46c-119">首先，您必須取得正在測試的撥號方案實例;使用 CsDialPlan Cmdlet 即可完成。</span><span class="sxs-lookup"><span data-stu-id="0c46c-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="0c46c-120">其次，您必須指定必須正常化的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0c46c-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="0c46c-121">電話號碼所用的格式，必須符合使用者撥打電話/輸入的數位。</span><span class="sxs-lookup"><span data-stu-id="0c46c-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="0c46c-122">例如，這個命令會檢索撥號計畫的實例、RedmondDialPlan，並檢查電話號碼12065551219是否可以正常化：</span><span class="sxs-lookup"><span data-stu-id="0c46c-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="0c46c-123">如果您有會自動新增國家/地區代碼（在此範例中為1）和區號（206）的正常化規則，您可能會想要檢查電話號碼5551219，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c46c-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="0c46c-124">如需詳細資訊，請參閱[Test CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="0c46c-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0c46c-125">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="0c46c-125">Determining success or failure</span></span>

<span data-ttu-id="0c46c-126">Test-CsDialPlan 不同于許多 Lync Server 測試 Cmdlet，因為它只會間接指示測試是否成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="0c46c-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="0c46c-127">使用 Test CsDialPlan 時，您不會收到類似以下所示的輸出結果，並清楚標示結果：</span><span class="sxs-lookup"><span data-stu-id="0c46c-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="0c46c-128">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0c46c-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0c46c-129">結果：成功</span><span class="sxs-lookup"><span data-stu-id="0c46c-129">Result : Success</span></span>

<span data-ttu-id="0c46c-130">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="0c46c-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="0c46c-131">出錯</span><span class="sxs-lookup"><span data-stu-id="0c46c-131">Error :</span></span>

<span data-ttu-id="0c46c-132">自檢</span><span class="sxs-lookup"><span data-stu-id="0c46c-132">Diagnosis :</span></span>

<span data-ttu-id="0c46c-133">相反地，如果 Test CsDialPlan 成功，則您會收到可成功翻譯並使用指定電話號碼的正常化規則資訊：</span><span class="sxs-lookup"><span data-stu-id="0c46c-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="0c46c-134">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="0c46c-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="0c46c-135">MatchingRule： Description =;Pattern = ^ （\\d （11）） $;譯文 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="0c46c-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="0c46c-136">Name = Prefix All;IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="0c46c-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="0c46c-137">如果 CsDialPlan 測試失敗（也就是，如果撥號方案沒有可翻譯指定之電話號碼的正常化規則），您就會收到如下所示的「空白」輸出：</span><span class="sxs-lookup"><span data-stu-id="0c46c-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="0c46c-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="0c46c-138">TranslatedNumber :</span></span>

<span data-ttu-id="0c46c-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="0c46c-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0c46c-140">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="0c46c-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="0c46c-141">以下是測試 CsDialPlan 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="0c46c-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="0c46c-142">指定電話號碼時，可能使用了不正確的格式。</span><span class="sxs-lookup"><span data-stu-id="0c46c-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="0c46c-143">撥號方案包括啟用 Lync Server 來轉譯使用者撥打電話或輸入之電話號碼的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="0c46c-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="0c46c-144">因此，您的撥號方案應該有符合使用者可能撥號的數位的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="0c46c-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="0c46c-145">例如，如果使用者可能先撥打國家/地區代碼、區號，然後撥打電話號碼本身，那表示您的撥號方案應該有一個標準化規則來處理電話號碼，例如：</span><span class="sxs-lookup"><span data-stu-id="0c46c-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="0c46c-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="0c46c-146">12065551219</span></span>
    
    <span data-ttu-id="0c46c-147">不過，如果您輸入不正確的電話號碼（例如，離開最後一個數位），則 Test-CsDialPlan 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0c46c-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="0c46c-148">這不是因為撥號方案有問題，但因為您輸入的是無法轉譯的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0c46c-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

