---
title: Lync Server 2013：建立或修改網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路區域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

*網路區域*是網路中樞或 backbones，用於設定通話許可控制、E9-1 及媒體旁路。 使用下列程式來建立或修改網路區域。 例如，如果您已為單一語音功能建立網路區域，就不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。 不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。 例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），而您想要部署 [呼叫許可控制]，您必須修改網路區域定義，以指定中央網站。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定 CAC 的網路區域](lync-server-2013-configure-network-regions-for-cac.md)。

<div>


> [!NOTE]  
> 此功能的部署主題中記錄了網路區域定義的任何特定功能需求。



</div>

如需有關使用網路區域的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - [新-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [移除-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>建立網路區域

建立可供通話許可控制、E9-1 或媒體旁路使用的網路區域。

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面建立網路區域

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsNetworkRegion Cmdlet 來建立網路區域：
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例如：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    在這個範例中，您建立了一個名為「北美洲」的網路區域，該區域與含「網站 ID 芝加哥」的中央網站相關聯。

3.  若要為您的拓撲建立網路區域，請對每個網路區域重複步驟2的設定。

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立網路區域

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**地區**]。

4.  按一下 [**新增**]。

5.  在 [**新區域**] 頁面上，按一下 [**名稱**]，然後輸入網路區域的名稱。

6.  按一下 [**中央網站**]，然後按一下清單中的中央網站。

7.  或者，按一下 [**描述**]，然後輸入說明此網路網站的其他資訊。

8.  按一下 [認可]****。

9.  若要為您的拓撲建立網路區域，請重複步驟4至8及其他地區的設定。

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>修改網路區域

修改現有網路區域的設定，以適應基本區域資訊的變更，或新功能所需的變更。

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面修改網路區域

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 CsNetworkRegion Cmdlet 來修改現有的網路區域：
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    例如：
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    在這個範例中，您修改了「北美」（使用本主題先前的程式建立）的現有網路區域，方法是變更說明。 如果「北美」區域的描述存在，這個命令會以這個值覆寫;如果沒有設定描述，則這個命令會將其設定。

3.  若要修改其他網路區域，請對其他地區的設定重複步驟2。

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 修改網路區域

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**地區**] 導覽按鈕。

4.  在表格中，按一下您要修改的網路區域。

5.  按一下 [**編輯**]，然後按一下 [**顯示詳細資料 ...**]。

6.  在 [**編輯區域**] 頁面上，視需要變更這個網路區域設定的值。

7.  按一下 [認可]****。

8.  若要完成修改網路區域，請重複步驟4至7及其他地區的設定。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

