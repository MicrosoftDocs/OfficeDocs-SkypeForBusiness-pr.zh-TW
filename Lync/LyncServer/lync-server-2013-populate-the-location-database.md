---
title: Lync Server 2013：填入位置資料庫
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
ms.openlocfilehash: de9a5c9015dcaf83252260c89837a473a6a2291f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527970"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="c372e-102">在 Lync Server 2013 中填入位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c372e-102">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c372e-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c372e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c372e-104">若要自動在網路中尋找用戶端，您必須先以網路 *線路圖*填入位置資料庫，它會將網路元素對應至市政 (，也就是街道) 位址。</span><span class="sxs-lookup"><span data-stu-id="c372e-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="c372e-105">您可以使用子網、無線存取點、開關及埠來定義線路圖。</span><span class="sxs-lookup"><span data-stu-id="c372e-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="c372e-106">您可以個別地將位址新增至位置資料庫，或是使用包含下表所述欄格式的 CSV 檔案大量新增位址。</span><span class="sxs-lookup"><span data-stu-id="c372e-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="c372e-107">如果您使用緊急位置識別號碼 (ELIN) 閘道，請在每個位置的 [ **CompanyName** ] 欄位中包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="c372e-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="c372e-108">您可以在每個位置中包含多個 Elin，每個位置都是以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="c372e-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c372e-109">網元</span><span class="sxs-lookup"><span data-stu-id="c372e-109">Network Element</span></span></th>
<th><span data-ttu-id="c372e-110">必要欄</span><span class="sxs-lookup"><span data-stu-id="c372e-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c372e-111"><strong>無線存取點</strong></span><span class="sxs-lookup"><span data-stu-id="c372e-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="c372e-112">&lt;BSSID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="c372e-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="c372e-113">&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="c372e-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c372e-114"><strong>子網路</strong></span><span class="sxs-lookup"><span data-stu-id="c372e-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="c372e-115">&lt;子網 &gt; 、 &lt; 描述 &gt; 、 &lt; 位置 &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="c372e-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="c372e-116">&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="c372e-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c372e-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="c372e-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="c372e-118">&lt;ChassisID &gt; 、 &lt; PortIDSubType &gt; 、 &lt; PortID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="c372e-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="c372e-119">&lt;。PreDirectional &gt; 、 &lt; StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; City &gt; 、 &lt; State &gt; 、 &lt; PostalCode &gt; 、 &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="c372e-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c372e-120"><strong>參數</strong></span><span class="sxs-lookup"><span data-stu-id="c372e-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="c372e-121">&lt;ChassisID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</span><span class="sxs-lookup"><span data-stu-id="c372e-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="c372e-122">&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="c372e-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c372e-123">如果您未填入位置資料庫，且位置原則中 **所需的位置** 設定為 **[是]** 或 [ **免責聲明**]，用戶端將會提示使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="c372e-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="c372e-124">如需有關填充位置資料庫的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c372e-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="c372e-125">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="c372e-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="c372e-126">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="c372e-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="c372e-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="c372e-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="c372e-128">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="c372e-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="c372e-129">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="c372e-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="c372e-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="c372e-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="c372e-131">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="c372e-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="c372e-132">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="c372e-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="c372e-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="c372e-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="c372e-134">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="c372e-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="c372e-135">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="c372e-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="c372e-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="c372e-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="c372e-137">若要將網路元素新增至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c372e-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="c372e-138">執行下列 Cmdlet，將子網位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c372e-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="c372e-139">若為 ELIN 閘道，請將 ELIN 放在 [CompanyName] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="c372e-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="c372e-140">您可以包含一個以上的 ELIN。</span><span class="sxs-lookup"><span data-stu-id="c372e-140">You can include more than one ELIN.</span></span> <span data-ttu-id="c372e-141">例如：</span><span class="sxs-lookup"><span data-stu-id="c372e-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="c372e-142">或者，您也可以執行下列指令程式，並使用名為 "subnets.csv" 的檔案大量更新子網位置。</span><span class="sxs-lookup"><span data-stu-id="c372e-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="c372e-143">執行下列 Cmdlet，將無線位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c372e-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="c372e-144">或者，您也可以執行下列指令程式，並使用名為 "waps.csv" 的檔案大量更新無線位置。</span><span class="sxs-lookup"><span data-stu-id="c372e-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="c372e-145">執行下列 Cmdlet，將切換位置新增至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="c372e-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="c372e-146">或者，您也可以執行下列指令程式，並使用名為 "switches.csv" 的檔案大量更新切換位置。</span><span class="sxs-lookup"><span data-stu-id="c372e-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="c372e-147">執行下列 Cmdlet，將埠位置新增至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="c372e-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="c372e-148">PortIDSubType 的預設值為 LocallyAssigned。</span><span class="sxs-lookup"><span data-stu-id="c372e-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="c372e-149">您也可以將它設定為 InterfaceAlias 或 InterfaceName</span><span class="sxs-lookup"><span data-stu-id="c372e-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="c372e-150">或者，您也可以執行下列指令程式，並使用名為 "ports.csv" 的檔案大量更新埠位置。</span><span class="sxs-lookup"><span data-stu-id="c372e-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

