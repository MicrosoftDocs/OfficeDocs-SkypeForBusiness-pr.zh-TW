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

# <a name="populate-the-location-database-in-lync-server-2013"></a>填入位置資料庫在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-17_

若要自動尋找網路內的用戶端，您必須先填入網路*接線圖*，這將網路元素對應到市街位置資料庫 (也就是街道) 地址。 若要定義接線圖，您可以使用子網路、 無線存取點、 交換器及連接埠。

您可以將地址至位置資料庫會個別或大量使用 CSV 檔案包含下表所述的欄格式。

如果您使用緊急位置識別號碼 (ELIN) 閘道，包括 ELIN 在**CompanyName**欄位中的每個位置。 您可以包含多個 Elin 為每個位置，每個由分號分隔。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>網路元素</th>
<th>必要欄數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>無線存取點</strong></p></td>
<td><p>&lt;BSSID&gt;、&lt;描述&gt;、&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，&lt;PreDirectional&gt;，...]</p>
<p>...]&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>子網路</strong></p></td>
<td><p>&lt;子網路&gt;、&lt;描述&gt;、&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，&lt;PreDirectional&gt;，...]</p>
<p>...]&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;PortIDSubType&gt;、&lt;PortID&gt;，&lt;描述&gt;，&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，...]</p>
<p>...]&lt;PreDirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;，&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>參數</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;描述&gt;、&lt;位置&gt;，&lt;CompanyName&gt;，&lt;HouseNumber&gt;，&lt;HouseNumberSuffix&gt;，&lt;PreDirectional&gt;，...]</p>
<p>...]&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;，&lt;縣/市&gt;，&lt;狀態&gt;，&lt;PostalCode&gt;，&lt;國家/地區&gt;</p></td>
</tr>
</tbody>
</table>


如果您未填入位置資料庫，以及**所需的位置**原則中的位置設為 [**是**] 或 [**免責聲明**，用戶端會提示使用者手動輸入位置。

如需填入位置資料庫的詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:

  - **取得 CsLisSubnet**

  - **設定 CsLisSubnet**

  - 移除 CsLisSubnet

  - **取得 CsLisWirelessAccessPoint**

  - **設定 CsLisWirelessAccessPoint**

  - **移除 CsLisWirelessAccessPoint**

  - **取得 CsLisSwitch**

  - **設定 CsLisSwitch**

  - **移除 CsLisSwitch**

  - **取得 CsLisPort**

  - **設定 CsLisPort**

  - **移除 CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>若要將網路元素加入至位置資料庫

1.  執行下列 cmdlet，將子網路位置加入至位置資料庫。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    ELIN 閘道，請將 ELIN 放在 CompanyName 欄位中。 您可以包含多個 ELIN。 例如：
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    或者，您可以執行下列 cmdlet，並使用名為 「 subnets.csv 「 大量更新子網路位置的檔案。
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  執行下列 cmdlet，將無線網路位置加入至位置資料庫。
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    或者，您可以執行下列 cmdlet，並使用名為 「 waps.csv 「 大量更新無線位置的檔案。
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  執行下列 cmdlet 以將交換器位置加入至位置資料庫。
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    或者，您可以執行下列 cmdlet，並使用名為 「 switches.csv 「 大量更新交換器位置的檔案。
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  執行下列 cmdlet，將連接埠位置加入至位置資料庫
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType 預設值為 LocallyAssigned。 您也可以將它設 InterfaceAlias 或預設
    
    或者，您可以執行下列 cmdlet，並使用名為 「 ports.csv 「 大量更新連接埠位置的檔案。
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

