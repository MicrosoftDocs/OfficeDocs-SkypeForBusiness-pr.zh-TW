---
title: Lync Server 2013;建立網路 interregion 路由
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 0eff2c1dd75258451002a41e0f284c4ad05c9728
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40974435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>在 Lync Server 2013 中建立網路 interregion 路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

*網路 interregion 路由*定義一對網路區域之間的路由。 通話許可控制部署中的每一組網路區域都需要有網路 interregion 路由。 這可讓部署中的每個網路區域存取每一個其他區域。

雖然區域連結會針對區域之間的連線設定頻寬限制，但 interregion 路由決定了連線將從一個區域傳遞到另一個區域的連結路徑。

如需使用網路 interregion 路由的詳細資料，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - [新-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [移除-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

在範例拓朴中，您必須為三個地區對中的每一組定義網路 interregion 路由：北美/EMEA、EMEA/APAC，以及北美/APAC。

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面建立網路 interregion 路由

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行**新的 CsNetworkInterRegionRoute** Cmdlet，以定義所需的路由。 例如，執行：
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 北美/APAC 網路 interregion 路由需要兩個網路區域連結，因為它們之間沒有直接的網路區域連結。

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立網路 interregion 路由

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**地區路線**] 導覽按鈕。

4.  按一下 [**新增**]。

5.  在 [**新增地區路線**] 頁面上，按一下 [**名稱**]，然後輸入網路 interregion 路由的名稱。

6.  按一下 [**網路\#區域 1**]，然後按一下清單中您要路由至 [網路區域\#2] 的網路區域。

7.  按一下 [**網路\#區域 2**]，然後按一下清單中您要路由至 [網路區域\#1] 的網路區域。

8.  按一下 [**網路區域連結**] 欄位旁的 [**新增**]，然後新增將在網路 interregion 路由中使用的 [網路區域] 連結。
    
    <div class=" ">
    

    > [!NOTE]  
    > 如果您要為兩個網路區域建立路線，而這些區域之間沒有直接的網路區域連結，您必須新增所有必要的連結，才能完成路線。 例如，北美/APAC 網路 interregion 路由需要兩個網路區域連結，因為它們之間沒有直接的網路區域連結。

    
    </div>

9.  按一下 [認可]****。

10. 若要為您的拓撲完成建立網路 interregion 路由，請重複步驟4到9，並設定其他網路 interregion 路由。

</div>

</div>

<span> </span>

</div>

</div>

</div>

