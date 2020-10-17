---
title: Lync Server 2013：對照電話號碼檢查主幹設定
description: Lync Server 2013：對照電話號碼檢查主幹設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdfe1a2a9c5c87310ad561464960c5a01fea7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543539"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="c6c51-103">對照 Lync Server 2013 中的電話號碼檢查主幹設定</span><span class="sxs-lookup"><span data-stu-id="c6c51-103">Check trunk configuration against a phone number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6c51-104">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="c6c51-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6c51-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="c6c51-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c6c51-106">每月</span><span class="sxs-lookup"><span data-stu-id="c6c51-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6c51-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="c6c51-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c6c51-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6c51-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6c51-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="c6c51-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c6c51-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c6c51-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c6c51-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsTrunkConfiguration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c6c51-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="c6c51-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c6c51-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c6c51-113">描述</span><span class="sxs-lookup"><span data-stu-id="c6c51-113">Description</span></span>

<span data-ttu-id="c6c51-114">SIP 主幹將 Lync Server internal Enterprise Voice 網路連接至下列任何一種：</span><span class="sxs-lookup"><span data-stu-id="c6c51-114">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="c6c51-115">公用交換電話網路 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="c6c51-115">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="c6c51-116">IP 公用 exchange 交換器 (PBX) 。</span><span class="sxs-lookup"><span data-stu-id="c6c51-116">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="c6c51-117"> (SBC) 的會話邊界控制器。</span><span class="sxs-lookup"><span data-stu-id="c6c51-117">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="c6c51-118">Test-CsTrunkConfiguration 指令程式會驗證使用者 (所撥打的電話號碼，) 可轉換成 e.164 網路，並透過指定的 SIP 主幹進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c6c51-118">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c6c51-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="c6c51-119">Running the test</span></span>

<span data-ttu-id="c6c51-120">若要執行 Test-CsTrunkConfiguration Cmdlet，您必須先使用 Get-CsTrunkConfiguration Cmdlet，以取得 SIP 主幹設定設定的實例;然後，該實例會管線傳送至 Test-CsTrunkConfiguration：</span><span class="sxs-lookup"><span data-stu-id="c6c51-120">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="c6c51-121">執行 Test-CsTrunkConfiguration 但未先執行 Get-CsTrunkConfiguration 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="c6c51-121">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="c6c51-122">例如，此命令將會失敗，而不會傳回任何資料：</span><span class="sxs-lookup"><span data-stu-id="c6c51-122">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="c6c51-123">如果您有多個 SIP 主幹設定的集合，您可以使用類似下列的命令，對相同的電話號碼測試每個集合：</span><span class="sxs-lookup"><span data-stu-id="c6c51-123">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="c6c51-124">如需詳細資訊，請參閱 Test-CsTrunkConfiguration Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="c6c51-124">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c6c51-125">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="c6c51-125">Determining success or failure</span></span>

<span data-ttu-id="c6c51-126">如果 Test-CsTrunkConfiguration 可以撥打撥號號碼，則已轉譯的電話號碼 (為 e.164 格式) 而且用於轉譯該電話號碼的規則會顯示在畫面上：</span><span class="sxs-lookup"><span data-stu-id="c6c51-126">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="c6c51-127">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="c6c51-127">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="c6c51-128">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="c6c51-128">\---------------- ------------</span></span>

<span data-ttu-id="c6c51-129">\+12065551219全球/Redmond</span><span class="sxs-lookup"><span data-stu-id="c6c51-129">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="c6c51-130">測試失敗時，Test-CsTrunkConfiguration 會傳回空的屬性值：</span><span class="sxs-lookup"><span data-stu-id="c6c51-130">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="c6c51-131">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="c6c51-131">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="c6c51-132">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="c6c51-132">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c6c51-133">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="c6c51-133">Reasons why the test might have failed</span></span>

<span data-ttu-id="c6c51-134">如果 Test-CsTrunkConfiguration 不會傳回符合，通常表示所測試的主幹設定設定沒有可以將撥號號碼轉換為 e.164 格式的撥出電話號碼轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="c6c51-134">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="c6c51-135">若要取得指派給主幹設定設定集合的轉譯規則，您可以使用類似下列的語法：</span><span class="sxs-lookup"><span data-stu-id="c6c51-135">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="c6c51-136">針對每個轉譯規則傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="c6c51-136">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="c6c51-137">描述：沒有國家或地區代碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c6c51-137">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="c6c51-138">模式： ^ \\ + (\\ d \*) $</span><span class="sxs-lookup"><span data-stu-id="c6c51-138">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="c6c51-139">名稱： NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="c6c51-139">Name : NoAreaCode</span></span>

<span data-ttu-id="c6c51-140">此時，您會檢查 Pattern 屬性的值 (它是 [正則運算式](https://go.microsoft.com/fwlink/?linkid=400464) 字串) ，以查看是否有任何轉譯規則設定為處理撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="c6c51-140">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="c6c51-141">如果不是，您必須變更其中一個現有的規則 (CsOutboundTranslationRule) 或使用 New-CsOutboundTranslationRule 指令程式將新規則新增至集合。</span><span class="sxs-lookup"><span data-stu-id="c6c51-141">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6c51-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6c51-142">See Also</span></span>


[<span data-ttu-id="c6c51-143">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="c6c51-143">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

