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
# <a name="populate-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中填入位置資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

若要自動在網路中尋找用戶端，您必須先以網路 *線路圖*填入位置資料庫，它會將網路元素對應至市政 (，也就是街道) 位址。 您可以使用子網、無線存取點、開關及埠來定義線路圖。

您可以個別地將位址新增至位置資料庫，或是使用包含下表所述欄格式的 CSV 檔案大量新增位址。

如果您使用緊急位置識別號碼 (ELIN) 閘道，請在每個位置的 [ **CompanyName** ] 欄位中包含 ELIN。 您可以在每個位置中包含多個 Elin，每個位置都是以分號分隔。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>網元</th>
<th>必要欄</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>無線存取點</strong></p></td>
<td><p>&lt;BSSID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</p>
<p>&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>子網路</strong></p></td>
<td><p>&lt;子網 &gt; 、 &lt; 描述 &gt; 、 &lt; 位置 &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</p>
<p>&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID &gt; 、 &lt; PortIDSubType &gt; 、 &lt; PortID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; ,.。。</p>
<p>&lt;。PreDirectional &gt; 、 &lt; StreetName &gt; 、 &lt; StreetSuffix &gt; 、 &lt; PostDirectional &gt; 、 &lt; City &gt; 、 &lt; State &gt; 、 &lt; PostalCode &gt; 、 &lt; Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>參數</strong></p></td>
<td><p>&lt;ChassisID &gt; 、 &lt; Description &gt; 、 &lt; Location &gt; 、 &lt; CompanyName &gt; 、 &lt; HouseNumber &gt; 、 &lt; HouseNumberSuffix &gt; 、 &lt; PreDirectional &gt; ,.。。</p>
<p>&lt;。StreetName &gt; ， &lt; StreetSuffix &gt; ， &lt; PostDirectional &gt; ， &lt; City &gt; ， &lt; State &gt; ， &lt; PostalCode &gt; ， &lt; Country&gt;</p></td>
</tr>
</tbody>
</table>


如果您未填入位置資料庫，且位置原則中 **所需的位置** 設定為 **[是]** 或 [ **免責聲明**]，用戶端將會提示使用者手動輸入位置。

如需有關填充位置資料庫的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - **CsLisSubnet**

  - **CsLisSubnet**

  - Remove-CsLisSubnet

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **CsLisSwitch**

  - **CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **CsLisPort**

  - **CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>若要將網路元素新增至位置資料庫

1.  執行下列 Cmdlet，將子網位置新增至位置資料庫。
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    若為 ELIN 閘道，請將 ELIN 放在 [CompanyName] 欄位中。 您可以包含一個以上的 ELIN。 例如：
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    或者，您也可以執行下列指令程式，並使用名為 "subnets.csv" 的檔案大量更新子網位置。
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  執行下列 Cmdlet，將無線位置新增至位置資料庫。
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    或者，您也可以執行下列指令程式，並使用名為 "waps.csv" 的檔案大量更新無線位置。
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  執行下列 Cmdlet，將切換位置新增至位置資料庫。
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    或者，您也可以執行下列指令程式，並使用名為 "switches.csv" 的檔案大量更新切換位置。
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  執行下列 Cmdlet，將埠位置新增至位置資料庫
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType 的預設值為 LocallyAssigned。 您也可以將它設定為 InterfaceAlias 或 InterfaceName
    
    或者，您也可以執行下列指令程式，並使用名為 "ports.csv" 的檔案大量更新埠位置。
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

