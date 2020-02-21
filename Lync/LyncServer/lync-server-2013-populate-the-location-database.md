---
title: Lync Server 2013： 填入位置資料庫
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
ms.openlocfilehash: 0216cada44f2512e33a0b33b627ed9a6d6582cda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="db886-102">填入位置資料庫在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db886-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db886-103">_**主題上次修改日期：** 2012年-09-17_</span><span class="sxs-lookup"><span data-stu-id="db886-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="db886-104">若要自動尋找網路內的用戶端，您必須先填入網路*接線圖*，這將網路元素對應到市街位置資料庫 (也就是街道) 地址。</span><span class="sxs-lookup"><span data-stu-id="db886-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="db886-105">若要定義接線圖，您可以使用子網路、 無線存取點、 交換器及連接埠。</span><span class="sxs-lookup"><span data-stu-id="db886-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="db886-106">您可以將地址至位置資料庫會個別或大量使用 CSV 檔案包含下表所述的欄格式。</span><span class="sxs-lookup"><span data-stu-id="db886-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="db886-107">如果您使用緊急位置識別號碼 (ELIN) 閘道，包括 ELIN 在**CompanyName**欄位中的每個位置。</span><span class="sxs-lookup"><span data-stu-id="db886-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="db886-108">您可以包含多個 Elin 為每個位置，每個由分號分隔。</span><span class="sxs-lookup"><span data-stu-id="db886-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db886-109">網路元素</span><span class="sxs-lookup"><span data-stu-id="db886-109">Network Element</span></span></th>
<th><span data-ttu-id="db886-110">必要欄數</span><span class="sxs-lookup"><span data-stu-id="db886-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db886-111"><strong>無線存取點</strong></span><span class="sxs-lookup"><span data-stu-id="db886-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="db886-112">&lt;BSSID&gt;、&lt;描述&gt;、&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，&lt;PreDirectional&gt;，...]</span><span class="sxs-lookup"><span data-stu-id="db886-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="db886-113">...]&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</span><span class="sxs-lookup"><span data-stu-id="db886-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db886-114"><strong>子網路</strong></span><span class="sxs-lookup"><span data-stu-id="db886-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="db886-115">&lt;子網路&gt;、&lt;描述&gt;、&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，&lt;PreDirectional&gt;，...]</span><span class="sxs-lookup"><span data-stu-id="db886-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="db886-116">...]&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</span><span class="sxs-lookup"><span data-stu-id="db886-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db886-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="db886-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="db886-118">&lt;ChassisID&gt;、&lt;PortIDSubType&gt;、&lt;PortID&gt;，&lt;描述&gt;，&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，...]</span><span class="sxs-lookup"><span data-stu-id="db886-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="db886-119">...]&lt;PreDirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;，&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</span><span class="sxs-lookup"><span data-stu-id="db886-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db886-120"><strong>參數</strong></span><span class="sxs-lookup"><span data-stu-id="db886-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="db886-121">&lt;ChassisID&gt;、&lt;描述&gt;、&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，&lt;PreDirectional&gt;，...]</span><span class="sxs-lookup"><span data-stu-id="db886-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="db886-122">...]&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</span><span class="sxs-lookup"><span data-stu-id="db886-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db886-123">如果您未填入位置資料庫，以及**所需的位置**原則中的位置設為 [**是**] 或 [**免責聲明**，用戶端會提示使用者手動輸入位置。</span><span class="sxs-lookup"><span data-stu-id="db886-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="db886-124">如需填入位置資料庫的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="db886-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="db886-125">**取得 CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="db886-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="db886-126">**設定 CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="db886-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="db886-127">移除 CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="db886-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="db886-128">**取得 CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="db886-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="db886-129">**設定 CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="db886-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="db886-130">**移除 CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="db886-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="db886-131">**取得 CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="db886-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="db886-132">**設定 CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="db886-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="db886-133">**移除 CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="db886-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="db886-134">**取得 CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="db886-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="db886-135">**設定 CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="db886-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="db886-136">**移除 CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="db886-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="db886-137">若要將網路元素加入至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="db886-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="db886-138">執行下列 cmdlet，將子網路位置加入至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="db886-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="db886-139">ELIN 閘道，請將 ELIN 放在 CompanyName 欄位中。</span><span class="sxs-lookup"><span data-stu-id="db886-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="db886-140">您可以包含多個 ELIN。</span><span class="sxs-lookup"><span data-stu-id="db886-140">You can include more than one ELIN.</span></span> <span data-ttu-id="db886-141">例如：</span><span class="sxs-lookup"><span data-stu-id="db886-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="db886-142">或者，您可以執行下列 cmdlet，並使用名為 「 subnets.csv 「 大量更新子網路位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="db886-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="db886-143">執行下列 cmdlet，將無線網路位置加入至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="db886-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="db886-144">或者，您可以執行下列 cmdlet，並使用名為 「 waps.csv 「 大量更新無線位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="db886-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="db886-145">執行下列 cmdlet 以將交換器位置加入至位置資料庫。</span><span class="sxs-lookup"><span data-stu-id="db886-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="db886-146">或者，您可以執行下列 cmdlet，並使用名為 「 switches.csv 「 大量更新交換器位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="db886-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="db886-147">執行下列 cmdlet，將連接埠位置加入至位置資料庫</span><span class="sxs-lookup"><span data-stu-id="db886-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="db886-148">PortIDSubType 預設值為 LocallyAssigned。</span><span class="sxs-lookup"><span data-stu-id="db886-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="db886-149">您也可以將它設 InterfaceAlias 或預設</span><span class="sxs-lookup"><span data-stu-id="db886-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="db886-150">或者，您可以執行下列 cmdlet，並使用名為 「 ports.csv 「 大量更新連接埠位置的檔案。</span><span class="sxs-lookup"><span data-stu-id="db886-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

