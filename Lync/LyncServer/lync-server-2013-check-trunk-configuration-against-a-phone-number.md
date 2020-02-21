---
title: Lync Server 2013： 檢查針對電話號碼的主幹組態
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
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="0d37f-102">檢查針對 Lync Server 2013 中的電話號碼的主幹組態</span><span class="sxs-lookup"><span data-stu-id="0d37f-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d37f-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="0d37f-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d37f-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="0d37f-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0d37f-105">每月</span><span class="sxs-lookup"><span data-stu-id="0d37f-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d37f-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="0d37f-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0d37f-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d37f-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d37f-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="0d37f-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0d37f-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0d37f-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0d37f-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 Test-cstrunkconfiguration cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="0d37f-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="0d37f-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0d37f-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0d37f-112">說明</span><span class="sxs-lookup"><span data-stu-id="0d37f-112">Description</span></span>

<span data-ttu-id="0d37f-113">SIP 主幹將 Lync Server 的內部企業語音網路連線至下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0d37f-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="0d37f-114">公用交換電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="0d37f-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="0d37f-115">IP 公用交換機 (PBX)。</span><span class="sxs-lookup"><span data-stu-id="0d37f-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="0d37f-116">工作階段邊界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="0d37f-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="0d37f-117">測試 Test-cstrunkconfiguration cmdlet 驗證 （視使用者所撥打） 的電話號碼可以轉換成 E.164 網路，並透過指定的 SIP 主幹路由傳送。</span><span class="sxs-lookup"><span data-stu-id="0d37f-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0d37f-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="0d37f-118">Running the test</span></span>

<span data-ttu-id="0d37f-119">若要執行測試 Test-cstrunkconfiguration 指令程式，您必須先使用 Get-cstrunkconfiguration cmdlet 來擷取 SIP 主幹組態設定; 執行個體該執行個體然後以管線傳輸至測試 Test-cstrunkconfiguration:</span><span class="sxs-lookup"><span data-stu-id="0d37f-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="0d37f-120">執行測試 Test-cstrunkconfiguration 第一個執行 Get-cstrunkconfiguration 而將無法運作。</span><span class="sxs-lookup"><span data-stu-id="0d37f-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="0d37f-121">例如，此命令將會失敗但不傳回任何資料：</span><span class="sxs-lookup"><span data-stu-id="0d37f-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="0d37f-122">如果您有多個 SIP 主幹組態設定集合，您可以使用類似下列的命令來同時測試每個集合針對相同的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="0d37f-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="0d37f-123">如需詳細資訊，請參閱 < 測試 Test-cstrunkconfiguration cmdlet 的說明 」 文件。</span><span class="sxs-lookup"><span data-stu-id="0d37f-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0d37f-124">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="0d37f-124">Determining success or failure</span></span>

<span data-ttu-id="0d37f-125">如果測試 Test-cstrunkconfiguration 可以再撥打電話對撥打的號碼，轉譯的電話號碼 （以 E.164 格式） 及用來轉譯該電話號碼的規則會同時顯示在畫面上：</span><span class="sxs-lookup"><span data-stu-id="0d37f-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="0d37f-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="0d37f-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="0d37f-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="0d37f-127">\---------------- ------------</span></span>

<span data-ttu-id="0d37f-128">\+12065551219 全域/Redmond</span><span class="sxs-lookup"><span data-stu-id="0d37f-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="0d37f-129">如果測試失敗，測試 Test-cstrunkconfiguration 會傳回空的屬性值：</span><span class="sxs-lookup"><span data-stu-id="0d37f-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="0d37f-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="0d37f-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="0d37f-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="0d37f-131">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0d37f-132">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="0d37f-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="0d37f-133">如果測試 Test-cstrunkconfiguration 不會傳回相符項目，通常表示正在測試主幹組態設定中沒有撥出電話號碼轉譯規則能夠將撥打的號碼轉換為 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="0d37f-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="0d37f-134">若要擷取指派給主幹組態設定集合的轉譯規則，您可以使用類似如下的語法：</span><span class="sxs-lookup"><span data-stu-id="0d37f-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="0d37f-135">會傳回的資訊類似的每個轉譯規則：</span><span class="sxs-lookup"><span data-stu-id="0d37f-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="0d37f-136">描述： 沒有國家/地區或區域程式碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0d37f-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="0d37f-137">模式: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="0d37f-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="0d37f-138">名稱： NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="0d37f-138">Name : NoAreaCode</span></span>

<span data-ttu-id="0d37f-139">此時，您可以檢查圖樣屬性 （也就是[規則運算式](https://go.microsoft.com/fwlink/?linkid=400464)的字串） 的值若要查看是否任何轉譯規則設定為處理撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="0d37f-139">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="0d37f-140">如果不是，您也必須變更其中一個現有的規則 (Set-CsOutboundTranslationRule)，或使用 New-csoutboundtranslationrule cmdlet 來新增至集合中新的規則。</span><span class="sxs-lookup"><span data-stu-id="0d37f-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d37f-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0d37f-141">See Also</span></span>


[<span data-ttu-id="0d37f-142">測試 Test-cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="0d37f-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

