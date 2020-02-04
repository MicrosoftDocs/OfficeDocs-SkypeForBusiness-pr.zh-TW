---
title: Lync Server 2013：對照電話號碼檢查幹線設定
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
ms.openlocfilehash: 7932e4cb7a7a9d74b945dcd60c2a1211ca5af694
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="9be9f-102">在 Lync Server 2013 中檢查 [中繼] 設定與電話號碼</span><span class="sxs-lookup"><span data-stu-id="9be9f-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be9f-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9be9f-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9be9f-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="9be9f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9be9f-105">次</span><span class="sxs-lookup"><span data-stu-id="9be9f-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be9f-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="9be9f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9be9f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9be9f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be9f-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="9be9f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9be9f-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="9be9f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9be9f-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 New-cstrunkconfiguration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9be9f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="9be9f-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9be9f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9be9f-112">說明</span><span class="sxs-lookup"><span data-stu-id="9be9f-112">Description</span></span>

<span data-ttu-id="9be9f-113">SIP trunks 將 Lync Server 內部企業語音網路連線至下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="9be9f-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="9be9f-114">公用交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="9be9f-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="9be9f-115">IP 公用分支交換（PBX）。</span><span class="sxs-lookup"><span data-stu-id="9be9f-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="9be9f-116">會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="9be9f-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="9be9f-117">New-cstrunkconfiguration Cmdlet 會驗證電話號碼（由使用者撥打電話）可以轉換成 E. 164 網路，並透過指定的 SIP 幹線路由。</span><span class="sxs-lookup"><span data-stu-id="9be9f-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9be9f-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="9be9f-118">Running the test</span></span>

<span data-ttu-id="9be9f-119">若要執行 Test New-cstrunkconfiguration Cmdlet，您必須先使用 New-cstrunkconfiguration Cmdlet 來檢索 SIP 幹線設定的實例;然後，該實例會以管道的方法傳送給 Test New-cstrunkconfiguration：</span><span class="sxs-lookup"><span data-stu-id="9be9f-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9be9f-120">執行測試-New-cstrunkconfiguration，而不事先執行 New-cstrunkconfiguration 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="9be9f-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="9be9f-121">例如，此命令將會失敗，而不會傳回任何資料：</span><span class="sxs-lookup"><span data-stu-id="9be9f-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="9be9f-122">如果您有多個 SIP 幹線設定的集合，您可以使用類似下列的命令來針對相同的電話號碼測試每個集合：</span><span class="sxs-lookup"><span data-stu-id="9be9f-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="9be9f-123">如需詳細資訊，請參閱 Test New-cstrunkconfiguration Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="9be9f-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9be9f-124">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="9be9f-124">Determining success or failure</span></span>

<span data-ttu-id="9be9f-125">如果測試 New-cstrunkconfiguration 可以撥打電話給撥打的號碼，則已翻譯的電話號碼（以 E 為格式），而用來翻譯該電話號碼的規則將會顯示在螢幕上：</span><span class="sxs-lookup"><span data-stu-id="9be9f-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="9be9f-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9be9f-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9be9f-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9be9f-127">\---------------- ------------</span></span>

<span data-ttu-id="9be9f-128">\+12065551219全球/雷蒙德</span><span class="sxs-lookup"><span data-stu-id="9be9f-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="9be9f-129">如果測試失敗，測試 New-cstrunkconfiguration 會傳回空屬性值：</span><span class="sxs-lookup"><span data-stu-id="9be9f-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="9be9f-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="9be9f-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="9be9f-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="9be9f-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9be9f-132">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="9be9f-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="9be9f-133">如果 Test New-cstrunkconfiguration 沒有傳回 match，通常表示測試的幹線設定設定沒有撥出電話號碼轉換規則，可將撥打的號碼轉換為 e. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="9be9f-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="9be9f-134">若要取得指派給主幹設定設定集合的翻譯規則，您可以使用類似以下的語法：</span><span class="sxs-lookup"><span data-stu-id="9be9f-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="9be9f-135">針對每個翻譯規則傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="9be9f-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="9be9f-136">描述：不含國家/地區代碼或區號的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9be9f-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="9be9f-137">模式： ^\\+ （\\d\*） $</span><span class="sxs-lookup"><span data-stu-id="9be9f-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="9be9f-138">名稱： NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="9be9f-138">Name : NoAreaCode</span></span>

<span data-ttu-id="9be9f-139">此時，您會檢查 Pattern 屬性的值（這是一個[正則運算式](http://go.microsoft.com/fwlink/?linkid=400464)字串），以查看是否有任何翻譯規則設定為處理撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="9be9f-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="9be9f-140">如果不是，您必須變更其中一個現有規則（CsOutboundTranslationRule），或使用新的-CsOutboundTranslationRule Cmdlet，才能在集合中新增規則。</span><span class="sxs-lookup"><span data-stu-id="9be9f-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9be9f-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="9be9f-141">See Also</span></span>


[<span data-ttu-id="9be9f-142">Test-New-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="9be9f-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

