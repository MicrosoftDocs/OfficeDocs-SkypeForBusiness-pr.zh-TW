---
title: Lync Server 2013;建立網路區間路由
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 156f2322d5b1b7cc1951f1cbd4df41eb231a8170
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>在 Lync Server 2013 中建立網路區間路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

*網路區間路由*定義了一組網路地區之間的路由。在您的通話許可控制部署中，每一組網路地區都需要搭配一個網路區間路由，以便讓部署內的每個網路地區都能互相存取。

地區連結會設定地區間連線的頻寬限制，而區間路由會決定從甲地連線到乙地時要採取的連結路徑。

如需使用網路區間路由的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [新 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

在範例拓撲當中，下列三組地區每一組都需要定義網路區間路由：North America/EMEA、EMEA/APAC，以及 North America/APAC。

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面建立網路區間路由

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 **New-CsNetworkInterRegionRoute** Cmdlet 以定義所需的路由。 例如，執行：
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 由於 North America/APAC 網路區間路由之間沒有直接的網路地區連結，因此需要用到兩個網路地區連結。

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立網路區間路由

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 **[地區路由]** 導覽按鈕。

4.  按一下 **[新增]**。

5.  按一下 **[新的地區路由]** 頁面上的 **[名稱]**，然後輸入網路區間路由的名稱。

6.  按一下 [**網路地區 \# 1**]，然後按一下清單中您要路由傳送至 [網路地區 2] 的網路地區 \# 。

7.  按一下 [**網路地區 \# 2**]，然後按一下清單中您要路由傳送至網路地區1的網路地區 \# 。

8.  按一下 **[網路地區連結]** 欄位旁邊的 **[新增]**，接著新增將用於網路區間路由的網路地區連結。
    
    <div class=" ">
    

    > [!NOTE]  
    > 如果您即將為尚未擁有直接網路地區連結的兩個網路地區建立路由，請新增所有必要的連結以便完成該路由。例如，由於 North America/APAC 網路區間路由之間沒有直接的網路地區連結，因此需要用到兩個網路地區連結。

    
    </div>

9.  按一下 **[認可]**。

10. 若要為您的拓撲完成建立網路區間路由，使用其他網路區間路由的設定並重複步驟 4 到 9。

</div>

</div>

<span> </span>

</div>

</div>

</div>

