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
ms.openlocfilehash: a93cee85afec1e3943af692d598d0d02ab678d58
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中填入位置資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

若要在網路中自動找到用戶端，您必須先使用網路*wiremap*填入位置資料庫，並將網元對應至市政（亦即街道）位址。 您可以使用子網、無線存取點、開關和埠來定義 wiremap。

您可以個別地將位址新增到位置資料庫，或使用包含下表所述之欄格式的 CSV 檔案，大量新增位址。

如果您使用緊急位置識別號碼（ELIN）閘道，請在 [**公司名稱**] 欄位中，為每個位置加入 ELIN。 您可以在每個位置包含多個 ELINs，並以分號分隔。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Network 元素</th>
<th>必要欄</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>無線存取點</strong></p></td>
<td><p>&lt;BSSID&gt;、&lt;描述&gt;、&lt;位置&gt;、&lt;公司&gt;名稱&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、&gt;PreDirectional,.。。</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;郵遞區號&gt;、&lt;國家/地區&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>子網路</strong></p></td>
<td><p>&lt;子&gt;網&lt;、&gt;描述&lt;、&gt;位置&lt;、&gt;公司&lt;名稱&gt;、&lt;HouseNumber&gt;、&lt;HouseNumberSuffix&gt;、PreDirectional,.。。</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;郵遞區號&gt;、&lt;國家/地區&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>通道</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;PortIDSubType&gt;、&lt;PortID&gt;、&lt;描述&gt;、&lt;位置&gt;、&lt;公司&gt;名稱&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix,.。。</p>
<p>...&lt;PreDirectional&gt;、&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;城市&gt;、&lt;州&gt;、&lt;郵遞區號&gt;、&lt;國家/地區&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Switch</strong></p></td>
<td><p>&lt;ChassisID&gt;、&lt;描述&gt;、&lt;位置&gt;、&lt;公司&gt;名稱&lt;、&gt;HouseNumber&lt;、&gt;HouseNumberSuffix&lt;、&gt;PreDirectional,.。。</p>
<p>...&lt;StreetName&gt;、&lt;StreetSuffix&gt;、&lt;PostDirectional&gt;、&lt;City&gt;、&lt;State&gt;、&lt;郵遞區號&gt;、&lt;國家/地區&gt;</p></td>
</tr>
</tbody>
</table>


如果您沒有填入位置資料庫，且位置原則中**所需的位置**設定為 **[是]** 或 [**免責聲明**]，則用戶端會提示使用者手動輸入位置。

如需有關填充位置資料庫的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - **CsLisSubnet**

  - **Set-CsLisSubnet**

  - 移除-CsLisSubnet

  - **CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **移除-CsLisWirelessAccessPoint**

  - **CsLisSwitch**

  - **Set-CsLisSwitch**

  - **移除-CsLisSwitch**

  - **CsLisPort**

  - **Set-CsLisPort**

  - **移除-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>在位置資料庫中新增網路元素

1.  執行下列 Cmdlet，將子網位置新增至位置資料庫。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    針對 ELIN 閘道，請將 ELIN 放在 [公司名稱] 欄位中。 您可以包含一個以上的 ELIN。 例如：
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    或者，您也可以執行下列 Cmdlet，並使用名為「subnet .csv」的檔案來大量更新子網位置。
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  執行下列 Cmdlet，以將無線位置新增至位置資料庫。
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    或者，您可以執行下列 Cmdlet，並使用名為 "waps" 的檔案來大量更新無線位置。
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  執行下列 Cmdlet，將切換位置新增到位置資料庫。
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    或者，您也可以執行下列 Cmdlet，並使用一個名為 "users.csv" 的檔案來大量更新切換位置。
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  執行下列 Cmdlet 以將埠位置新增到位置資料庫
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType 的預設值是 LocallyAssigned。 您也可以將它設定為 InterfaceAlias 或 InterfaceName
    
    或者，您可以執行下列 Cmdlet，並使用名為「埠 .csv」的檔案來大量更新埠位置。
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

