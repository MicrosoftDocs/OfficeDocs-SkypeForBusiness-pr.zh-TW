---
title: Lync Server 2013：檢查語音正常化規則
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
ms.openlocfilehash: 04e383f38d5af6f106354a766c857635bcd87eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="b8646-102">在 Lync Server 2013 中檢查語音正常化規則</span><span class="sxs-lookup"><span data-stu-id="b8646-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8646-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b8646-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8646-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="b8646-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b8646-105">次</span><span class="sxs-lookup"><span data-stu-id="b8646-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8646-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="b8646-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b8646-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8646-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8646-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="b8646-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b8646-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b8646-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b8646-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceNormalizationRule Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="b8646-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="b8646-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b8646-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b8646-112">說明</span><span class="sxs-lookup"><span data-stu-id="b8646-112">Description</span></span>

<span data-ttu-id="b8646-113">語音正常化規則是用來將使用者所撥的電話號碼（例如2065551219）轉換為 Lync Server （+ 12065551219）所使用的 E. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="b8646-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="b8646-114">例如，如果使用者習慣撥電話號碼（不包括國家/地區碼或區號（例如5551219）），則您必須有可將該數位轉換為 E.i 格式的語音正常化規則： + 12065551219。</span><span class="sxs-lookup"><span data-stu-id="b8646-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="b8646-115">如果沒有這類規則，使用者將無法呼叫555-1219。</span><span class="sxs-lookup"><span data-stu-id="b8646-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="b8646-116">CsVoiceNormalizationRule Cmdlet 會驗證指定的語音正常化規則是否可以成功轉換指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b8646-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="b8646-117">例如，這個命令會檢查全域正常化規則 NoAreaCode 是否可以正常化並轉換撥號字串5551219。</span><span class="sxs-lookup"><span data-stu-id="b8646-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b8646-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="b8646-118">Running the test</span></span>

<span data-ttu-id="b8646-119">若要執行 CsVoiceNormalizationRule Cmdlet，您必須先使用 CsVoiceNormalizationRule Cmdlet 來檢索所測試規則的實例，然後將該實例管路為 Test-CsVoiceNormalizationRule。</span><span class="sxs-lookup"><span data-stu-id="b8646-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="b8646-120">類似以下的語法將無法運作：</span><span class="sxs-lookup"><span data-stu-id="b8646-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="b8646-121">Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "全域/全部首碼"</span><span class="sxs-lookup"><span data-stu-id="b8646-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="b8646-122">相反地，請使用如下所示的語法，其中結合了 CsVoiceNormalizationRule 和 CsVoiceNormalizationRule Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b8646-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="b8646-123">CsVoiceNormalizationRule-身分識別 "全域/前置全部" |Test-CsVoiceNormalizationRule-DialedNumber "12065551219"</span><span class="sxs-lookup"><span data-stu-id="b8646-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8646-124">.</span><span class="sxs-lookup"><span data-stu-id="b8646-124">.</span></span> <span data-ttu-id="b8646-125">或者，您也可以使用此方法來取得規則的實例，然後根據指定的電話號碼來測試該規則：</span><span class="sxs-lookup"><span data-stu-id="b8646-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="b8646-126">輸入 DialedNumber 參數的值，就像您預期要撥打的號碼一樣。</span><span class="sxs-lookup"><span data-stu-id="b8646-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="b8646-127">例如，如果指定的語音正常化規則應該自動新增國家/地區代碼（值12065551219中的初始1），那麼您應該離開國家/地區代碼：</span><span class="sxs-lookup"><span data-stu-id="b8646-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="b8646-128">如果規則設定正確，則會在將號碼轉換為 Lync Server 所使用的 E. 164 格式時，自動新增國家/地區代碼。</span><span class="sxs-lookup"><span data-stu-id="b8646-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="b8646-129">如需詳細資訊，請參閱 Test CsVoiceNormalizationRule Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="b8646-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b8646-130">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="b8646-130">Determining success or failure</span></span>

<span data-ttu-id="b8646-131">如果指定的語音正常化規則可以翻譯所提供的數位，則會在螢幕上顯示已翻譯的數位：</span><span class="sxs-lookup"><span data-stu-id="b8646-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="b8646-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="b8646-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="b8646-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="b8646-133">\+12065551219</span></span>

<span data-ttu-id="b8646-134">如果測試失敗，則會傳回一個空白翻譯的數位：</span><span class="sxs-lookup"><span data-stu-id="b8646-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="b8646-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="b8646-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b8646-136">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="b8646-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="b8646-137">如果測試 CsVoiceNormalizationRule 確實傳回已翻譯的數位，表示指定的語音正常化規則無法將提供的電話號碼轉譯成 Lync Server 所使用的 e. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="b8646-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="b8646-138">若要確認，請先確認您已正確輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b8646-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="b8646-139">例如，您會希望語音正常化規則在翻譯如下所示的數位時發生問題：</span><span class="sxs-lookup"><span data-stu-id="b8646-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="b8646-140">假設輸入的數位正確，下一個步驟應該是確認指定的正常化規則是設計來處理該電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b8646-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="b8646-141">例如，一個正常化規則可能是設計用來處理12065551219格式，但第二個規則可能是用來處理數位2065551219的設計。</span><span class="sxs-lookup"><span data-stu-id="b8646-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="b8646-142">（這是相同的電話號碼，在最開頭則不是國家/地區代碼1）。若要傳回有關語音正常化規則的詳細資訊，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="b8646-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="b8646-143">若要返回所有語音正常化規則的詳細資訊，請改為執行此命令：</span><span class="sxs-lookup"><span data-stu-id="b8646-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8646-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="b8646-144">See Also</span></span>


[<span data-ttu-id="b8646-145">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="b8646-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

