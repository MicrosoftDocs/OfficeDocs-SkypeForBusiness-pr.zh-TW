---
title: Lync Server 2013： 檢查語音正規化規則
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
ms.openlocfilehash: 52820473a632598779aae9023967598b8ae27f89
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="bd7c4-102">核取 [Lync Server 2013 中的語音正規化規則</span><span class="sxs-lookup"><span data-stu-id="bd7c4-102">Check voice normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd7c4-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="bd7c4-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd7c4-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="bd7c4-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bd7c4-105">每月</span><span class="sxs-lookup"><span data-stu-id="bd7c4-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd7c4-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="bd7c4-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bd7c4-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd7c4-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd7c4-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="bd7c4-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bd7c4-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bd7c4-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試來 cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="bd7c4-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bd7c4-112">描述</span><span class="sxs-lookup"><span data-stu-id="bd7c4-112">Description</span></span>

<span data-ttu-id="bd7c4-113">語音正規化規則可用來將轉換為 E.164 格式使用 Lync Server (+ 12065551219) 的使用者 (例如，2065551219) 所撥打的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-113">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="bd7c4-114">例如，如果使用者在撥打的電話號碼，但不包括國家/地區或區域程式碼 (例如 5551219) 習慣然後您必須可以將該數字轉換成 E.164 格式的語音正規化規則: + 12065551219。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-114">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="bd7c4-115">沒有這類規則，使用者無法呼叫 555-1219。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-115">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="bd7c4-116">測試來 cmdlet 會驗證指定的語音正規化規則可以成功轉換的指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-116">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="bd7c4-117">例如，此命令會檢查全域正規化規則 NoAreaCode 可以正規化的需求，並將撥號對應表字串 5551219 轉換。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-117">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bd7c4-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="bd7c4-118">Running the test</span></span>

<span data-ttu-id="bd7c4-119">若要執行測試來指令程式，您必須先使用 Get-csvoicenormalizationrule cmdlet 來擷取要測試之規則的執行個體，並再將以管線傳輸至測試來執行個體。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-119">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="bd7c4-120">將無法使用類似如下的語法：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-120">Syntax similar to this won't work:</span></span>

<span data-ttu-id="bd7c4-121">來測試 DialedNumber 」 12065551219"– NormalizationRule 「 全域/前置詞所有 」</span><span class="sxs-lookup"><span data-stu-id="bd7c4-121">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="bd7c4-122">相反地，使用語法如下所示，結合了 Get-csvoicenormalizationrule 及測試來 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bd7c4-122">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="bd7c4-123">Get-csvoicenormalizationrule-Identity"全域/前置詞所有 「 |來測試 DialedNumber 「 12065551219 」</span><span class="sxs-lookup"><span data-stu-id="bd7c4-123">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd7c4-124">.</span><span class="sxs-lookup"><span data-stu-id="bd7c4-124">.</span></span> <span data-ttu-id="bd7c4-125">或者，您也可以使用這種方法來擷取規則的執行個體，然後測試對指定的電話號碼的規則：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-125">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="bd7c4-126">完全依照您預期該號碼撥打 DialedNumber 參數輸入值。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-126">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="bd7c4-127">例如，如果指定的語音正規化規則應會自動新增國碼/地區碼 (值 12065551219 中的初始 1)，則應該將維持關閉國碼/地區碼：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-127">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="bd7c4-128">如果規則設定正確，它會自動加入國碼/地區碼轉譯 Lync 伺服器所使用的 E.164 格式號碼時。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-128">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="bd7c4-129">如需詳細資訊，請參閱 < 測試來 cmdlet 的說明 」 文件。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-129">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bd7c4-130">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="bd7c4-130">Determining success or failure</span></span>

<span data-ttu-id="bd7c4-131">如果指定的語音正規化規則可以翻譯提供的號碼然後轉譯後的數字會顯示畫面上：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-131">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="bd7c4-132">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="bd7c4-132">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="bd7c4-133">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="bd7c4-133">\+12065551219</span></span>

<span data-ttu-id="bd7c4-134">如果測試失敗，則會傳回空白的翻譯的數目：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-134">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="bd7c4-135">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="bd7c4-135">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bd7c4-136">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="bd7c4-136">Reasons why the test might have failed</span></span>

<span data-ttu-id="bd7c4-137">如果測試來並傳回表示指定之的語音正規化規則無法將提供的電話號碼轉譯成 Lync 伺服器所使用的 E.164 格式轉譯的號碼。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-137">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="bd7c4-138">若要確認，請先確認您正確輸入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-138">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="bd7c4-139">例如，您所預期的轉譯類似這樣的數字的問題您語音正規化規則：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-139">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="bd7c4-140">假設已正確輸入號碼，接著應該若要確認指定的正規化規則設計來處理該電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-140">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="bd7c4-141">例如，一個正規化規則可能設計來處理格式 12065551219，但第二個規則可能設計來處理數 2065551219。</span><span class="sxs-lookup"><span data-stu-id="bd7c4-141">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="bd7c4-142">（這是相同的電話號碼，減一開始時國家/地區碼為 1）。若要傳回的語音正規化規則的詳細的資訊，請執行命令類似這樣：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-142">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="bd7c4-143">若要傳回所有語音正規化規則的詳細的資訊，請改為執行此命令：</span><span class="sxs-lookup"><span data-stu-id="bd7c4-143">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd7c4-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bd7c4-144">See Also</span></span>


[<span data-ttu-id="bd7c4-145">測試來</span><span class="sxs-lookup"><span data-stu-id="bd7c4-145">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

