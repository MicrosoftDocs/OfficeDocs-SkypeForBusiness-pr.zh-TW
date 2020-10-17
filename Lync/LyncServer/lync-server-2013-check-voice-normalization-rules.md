---
title: Lync Server 2013：檢查語音正常化規則
description: Lync Server 2013：檢查語音正常化規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f68bbde24a3dc7d8e8214dcfe506d4b8112fbbb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543529"
---
# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="d66ac-103">在 Lync Server 2013 中檢查語音正常化規則</span><span class="sxs-lookup"><span data-stu-id="d66ac-103">Check voice normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d66ac-104">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="d66ac-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d66ac-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="d66ac-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d66ac-106">每月</span><span class="sxs-lookup"><span data-stu-id="d66ac-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66ac-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="d66ac-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d66ac-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d66ac-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66ac-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d66ac-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d66ac-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d66ac-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d66ac-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceNormalizationRule Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d66ac-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="d66ac-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d66ac-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d66ac-113">描述</span><span class="sxs-lookup"><span data-stu-id="d66ac-113">Description</span></span>

<span data-ttu-id="d66ac-114">語音正規化規則是用來將使用者所撥打的電話號碼轉換 (例如，2065551219) 至 Lync Server (+ 12065551219) 所使用的 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="d66ac-114">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="d66ac-115">例如，如果使用者習慣撥打電話號碼，但未包含國家或地區碼 (例如，5551219) 則您必須具有可將該號碼轉換為 e.164 格式的語音正規化規則： + 12065551219。</span><span class="sxs-lookup"><span data-stu-id="d66ac-115">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="d66ac-116">若未使用此規則，使用者將無法呼叫555-1219。</span><span class="sxs-lookup"><span data-stu-id="d66ac-116">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="d66ac-117">Test-CsVoiceNormalizationRule Cmdlet 會驗證指定的語音正規化規則是否可成功轉換指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d66ac-117">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="d66ac-118">例如，此命令會檢查全域正規化規則 NoAreaCode 是否可以標準化及轉換撥號字串5551219。</span><span class="sxs-lookup"><span data-stu-id="d66ac-118">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d66ac-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="d66ac-119">Running the test</span></span>

<span data-ttu-id="d66ac-120">若要執行 Test-CsVoiceNormalizationRule Cmdlet，您必須先使用 Get-CsVoiceNormalizationRule 指令程式，以取得所測試之規則的實例，然後使用管道將此實例 Get-csvoicenormalizationrule。</span><span class="sxs-lookup"><span data-stu-id="d66ac-120">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="d66ac-121">類似下列的語法不起作用：</span><span class="sxs-lookup"><span data-stu-id="d66ac-121">Syntax similar to this won't work:</span></span>

<span data-ttu-id="d66ac-122">Test-CsVoiceNormalizationRule DialedNumber "12065551219" – NormalizationRule "global/Prefix All"</span><span class="sxs-lookup"><span data-stu-id="d66ac-122">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="d66ac-123">請改為使用下列語法，它會結合 Get-CsVoiceNormalizationRule 和 Test-CsVoiceNormalizationRule Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="d66ac-123">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="d66ac-124">Get-CsVoiceNormalizationRule 身分識別 "global/Prefix All" |Test-CsVoiceNormalizationRule-DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="d66ac-124">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d66ac-125">.</span><span class="sxs-lookup"><span data-stu-id="d66ac-125">.</span></span> <span data-ttu-id="d66ac-126">或者，您也可以使用此方法來取得規則的實例，然後根據指定的電話號碼來測試該規則：</span><span class="sxs-lookup"><span data-stu-id="d66ac-126">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="d66ac-127">輸入 DialedNumber 參數的值，就像您預期要撥打的號碼一樣。</span><span class="sxs-lookup"><span data-stu-id="d66ac-127">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="d66ac-128">例如，如果指定的語音正規化規則應該會自動將國家/地區代碼新增 (值12065551219中的初始 1) 則您應該保留國家/地區代碼：</span><span class="sxs-lookup"><span data-stu-id="d66ac-128">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="d66ac-129">如果規則設定正確，它會在將號碼轉換成 Lync Server 使用的 e.164 格式時，自動新增國家/地區代碼。</span><span class="sxs-lookup"><span data-stu-id="d66ac-129">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="d66ac-130">如需詳細資訊，請參閱 Test-CsVoiceNormalizationRule Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="d66ac-130">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d66ac-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="d66ac-131">Determining success or failure</span></span>

<span data-ttu-id="d66ac-132">如果指定的語音正規化規則可以轉譯所提供的數目，則會在螢幕上顯示轉譯後的數位：</span><span class="sxs-lookup"><span data-stu-id="d66ac-132">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="d66ac-133">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="d66ac-133">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="d66ac-134">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="d66ac-134">\+12065551219</span></span>

<span data-ttu-id="d66ac-135">如果測試失敗，則會傳回空白轉譯後的號碼：</span><span class="sxs-lookup"><span data-stu-id="d66ac-135">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="d66ac-136">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="d66ac-136">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d66ac-137">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="d66ac-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="d66ac-138">如果 Test-CsVoiceNormalizationRule 傳回轉譯後的數位，表示指定的語音正規化規則無法將提供的電話號碼轉譯成 Lync Server 所使用的 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="d66ac-138">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="d66ac-139">若要確認，請先確定您已正確輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d66ac-139">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="d66ac-140">例如，您預期您的語音正規化規則在轉譯類似以下的數位時會發生問題：</span><span class="sxs-lookup"><span data-stu-id="d66ac-140">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="d66ac-141">假設輸入的號碼正確，下一個步驟應該是驗證指定的正規化規則是設計用來處理該電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d66ac-141">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="d66ac-142">例如，一個正規化規則可能設計用來處理格式12065551219，但是第二個規則可能設計為處理數位2065551219。</span><span class="sxs-lookup"><span data-stu-id="d66ac-142">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="d66ac-143"> (相同的電話號碼，在最開始的位置減去國家碼1。 ) 若要傳回語音正規化規則的詳細資訊，請執行類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="d66ac-143">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="d66ac-144">若要傳回所有語音正規化規則的詳細資訊，請改為執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d66ac-144">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d66ac-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d66ac-145">See Also</span></span>


[<span data-ttu-id="d66ac-146">測試-Get-csvoicenormalizationrule</span><span class="sxs-lookup"><span data-stu-id="d66ac-146">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

