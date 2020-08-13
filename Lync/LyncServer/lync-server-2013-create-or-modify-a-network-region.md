---
title: Lync Server 2013：建立或修改網路地區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fece34f8e5177760e470083cd929cbddaab60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路地區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

「網路區域」** 是用於通話許可控制、E9-1-1 及媒體旁路設定的網路中樞或骨幹。 請使用下列程式來建立或修改網路地區。 例如，您已為一個語音功能建立網路區域，便不需要建立新的網路區域；其他的進階 Enterprise Voice 功能會使用那些相同的網路區域。 不過，您必須修改現有的網路區域定義，以套用功能特定的設定。 例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定 CAC 的網路地區](lync-server-2013-configure-network-regions-for-cac.md)。

<div>


> [!NOTE]  
> 網路地區定義的任何功能特定需求都記載在功能的部署主題中。



</div>

如需使用網路地區的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>建立網路地區

建立網路地區，以便提供給通話許可控制、E9-1-1 或媒體旁路使用。

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面建立網路地區

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 New-CsNetworkRegion Cmdlet 來建立網路地區：
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例如：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    在此範例中，您會建立一個名為「NorthAmerica」的網路地區，該網路地區與網站識別碼芝加哥相關聯的中央網站。

3.  若要完成建立拓撲的網路地區，請使用每個網路地區的設定重複步驟2。

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立網路地區

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 [**地區**]。

4.  按一下 [ **新增**]。

5.  在 [**新地區**] 頁面上，按一下 [**名稱**]，然後輸入網路地區的名稱。

6.  按一下 [**中央網站**]，然後按一下清單中的中央網站。

7.  (選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。

8.  按一下 **[認可]**。

9.  若要完成建立拓撲的網路地區，請使用其他地區的設定重複步驟4到8。

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>修改網路地區

修改現有網路地區的設定，以容納基本區域資訊的變更或新功能所需的變更。

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面來修改網路地區

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsNetworkRegion Cmdlet 以修改現有的網路地區：
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例如：
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    在此範例中，您會使用本) 主題稍早的程式（透過變更描述）來建立名為「NorthAmerica」 (的現有網路地區。 如果「NorthAmerica」區域的描述存在，此命令會以此值覆寫該描述。如果未設定任何描述，則此命令會將其設定。

3.  若要修改其他網路地區，請使用其他地區的設定重複步驟2。

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>使用 Lync Server 控制台修改網路地區

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 [**地區**] 導覽按鈕。

4.  在表格中，按一下您要修改的網路地區。

5.  按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。

6.  在 [**編輯地區**] 頁面上，視需要變更此網路地區的設定值。

7.  按一下 **[認可]**。

8.  若要完成修改網路地區，請使用其他地區的設定重複步驟4到7。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

