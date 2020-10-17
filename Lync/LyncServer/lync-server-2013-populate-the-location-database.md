---
title: Lync Server 2013：填入位置資料庫
description: Lync Server 2013：填入位置資料庫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cf3204795ae2c4f8248517b84d7a5ac1bad0d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543169"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="7d429-103">在 Lync Server 2013 中填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="7d429-103">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d429-104">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="7d429-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="7d429-105">若要自動在網路中尋找用戶端，您必須先以網路 *線路圖*填入位置資料庫，它會將網路元素對應至市政 (，也就是街道) 位址。</span><span class="sxs-lookup"><span data-stu-id="7d429-105">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="7d429-106">您可以使用子網、無線存取點、開關及埠來定義線路圖。</span><span class="sxs-lookup"><span data-stu-id="7d429-106">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="7d429-107">您可以個別地將位址新增至位置資料庫，或是使用包含下表所述欄格式的 CSV 檔案大量新增位址。</span><span class="sxs-lookup"><span data-stu-id="7d429-107">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="7d429-108">如果您使用緊急位置識別號碼 (ELIN) 閘道，請在每個位置的 [ **CompanyName** ] 欄位中包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="7d429-108">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="7d429-109">您可以在每個位置中包含多個 Elin，每個位置都是以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="7d429-109">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d429-110">網元</span><span class="sxs-lookup"><span data-stu-id="7d429-110">Network Element</span></span></th>
<th><span data-ttu-id="7d429-111">必要欄</span><span class="sxs-lookup"><span data-stu-id="7d429-111">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d429-112"><strong>無線存取點</strong></span><span class="sxs-lookup"><span data-stu-id="7d429-112"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="7d429-113">&lt;BSSID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="7d429-113">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="7d429-114">&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="7d429-114">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d429-115"><strong>子網路</strong></span><span class="sxs-lookup"><span data-stu-id="7d429-115"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="7d429-116">&lt;子網 &gt; 、 &lt; 描述 &gt; 、 &lt; 位置 &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="7d429-116">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="7d429-117">&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="7d429-117">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d429-118"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="7d429-118"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="7d429-119">&lt;ChassisID &gt; 、 &lt; PortIDSubType &gt; 、 &lt; PortID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="7d429-119">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="7d429-120">&lt;。PreDirectional &gt; 、 &lt; StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; City &gt; 、 &lt; State &gt; 、 &lt; PostalCode &gt; 、 &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="7d429-120">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d429-121"><strong>參數</strong></span><span class="sxs-lookup"><span data-stu-id="7d429-121"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="7d429-122">&lt;ChassisID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="7d429-122">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="7d429-123">&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="7d429-123">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7d429-124">如果您未填入位置資料庫，且位置原則中 **所需的位置** 設定為 **[是]** 或 [ **免責聲明**]，用戶端將會提示使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="7d429-124">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="7d429-125">如需有關填充位置資料庫的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7d429-125">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="7d429-126">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="7d429-126">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="7d429-127">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="7d429-127">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="7d429-128">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="7d429-128">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="7d429-129">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="7d429-129">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="7d429-130">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="7d429-130">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="7d429-131">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="7d429-131">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="7d429-132">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="7d429-132">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="7d429-133">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="7d429-133">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="7d429-134">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="7d429-134">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="7d429-135">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="7d429-135">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="7d429-136">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="7d429-136">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="7d429-137">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="7d429-137">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="7d429-138">若要將網路元素新增至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="7d429-138">To add network elements to the location database</span></span>

1.  <span data-ttu-id="7d429-139">執行下列 Cmdlet，將子網位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="7d429-139">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="7d429-140">若為 ELIN 閘道，請將 ELIN 放在 [CompanyName] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="7d429-140">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="7d429-141">您可以包含一個以上的 ELIN。</span><span class="sxs-lookup"><span data-stu-id="7d429-141">You can include more than one ELIN.</span></span> <span data-ttu-id="7d429-142">例如：</span><span class="sxs-lookup"><span data-stu-id="7d429-142">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="7d429-143">或者，您也可以執行下列指令程式，並使用名為 "subnets.csv" 的檔案大量更新子網位置。</span><span class="sxs-lookup"><span data-stu-id="7d429-143">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="7d429-144">執行下列 Cmdlet，將無線位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="7d429-144">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="7d429-145">或者，您也可以執行下列指令程式，並使用名為 "waps.csv" 的檔案大量更新無線位置。</span><span class="sxs-lookup"><span data-stu-id="7d429-145">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="7d429-146">執行下列 Cmdlet，將切換位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="7d429-146">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="7d429-147">或者，您也可以執行下列指令程式，並使用名為 "switches.csv" 的檔案大量更新切換位置。</span><span class="sxs-lookup"><span data-stu-id="7d429-147">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="7d429-148">執行下列 Cmdlet，將埠位置新增至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="7d429-148">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="7d429-149">PortIDSubType 的預設值為 LocallyAssigned。</span><span class="sxs-lookup"><span data-stu-id="7d429-149">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="7d429-150">您也可以將它設定為 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="7d429-150">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="7d429-151">或者，您也可以執行下列指令程式，並使用名為 "ports.csv" 的檔案大量更新埠位置。</span><span class="sxs-lookup"><span data-stu-id="7d429-151">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

