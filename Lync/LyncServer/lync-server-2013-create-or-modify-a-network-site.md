---
title: Lync Server 2013：建立或修改網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60119e137851bbaa8dc7b6735202132085bb8d34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506120"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

通話許可控制 (CAC)、E9-1-1 和媒體旁路的部署需視「網站」** 的設定而定，而網站是在網路地區內部定義，且一定與網路地區相關聯。 網路網站代表分支辦公室位置、一組大樓或校園。 多個網站可代表具有類似頻寬的子網路集合。

使用下列程序可建立或修改網站。例如，如果您已為一個語音功能建立網站，就不需要再建立新的網站，其他語音功能會使用這些相同的網站。不過，您可能需要修改現有網站定義，以便套用特定的功能設定。例如，如果已為 E9-1-1 建立了網站，在部署通話許可控制期間需要修改網站，以便套用頻寬原則設定檔。

<div>


> [!NOTE]  
> 您可在部署文件中，找到與每個進階語音功能相關之網站的特定範例與需求： 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中設定 CAC 的網路網站</A></P></LI></UL>



</div>

如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>建立網站

建立網路地區，以便提供給通話許可控制、E9-1-1 或媒體旁路使用。

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>使用管理命令介面建立網站

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 New-CsNetworkSite Cmdlet 建立網站：
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    例如：
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    此範例會建立一個稱為「芝加哥」的網站，位於「北美地區」網路地區中。
    
    <div>
    

    > [!NOTE]  
    > 「北美地區」網路地區必須已經存在，此命令才能成功執行。

    
    </div>

3.  使用其他網站的設定重複執行步驟 2，完成建立拓撲的網站。

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立網站

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 **[站台]** 導覽按鈕。

4.  按一下 **[新增]**。

5.  在 **[新增站台]** 頁面上，按一下 **[名稱]**，然後為網站輸入名稱。

6.  按一下 **[地區]**，然後按一下清單中的地區。

7.  (選用) 按一下 **[頻寬原則]**，然後按一下清單中的頻寬原則。
    
    <div>
    

    > [!NOTE]  
    > 如果您要在網站部署通話許可控制，才需要頻寬原則。

    
    </div>

8.  (選用) 按一下 **[位置原則]**，然後按一下清單中的位置原則。
    
    <div>
    

    > [!NOTE]  
    > 如果您要在網站部署 E9-1-1，才需要位置原則。

    
    </div>

9.  (選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。

10. 按一下 **[認可]**。

11. 使用其他網站的設定重複執行步驟 4 至 10，完成建立拓撲的網站。

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>修改網站

修改網路地區，以便提供給通話許可控制、E9-1-1 或媒體旁路使用。

<div>

## <a name="to-modify-a-network-site"></a>修改網站

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsNetworkSite Cmdlet 以修改網站：
    
        Set-CsNetworkSite -Identity <string>
    
    例如：
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    此範例會將稱為「阿布奎基」的網站移至「北美地區」網路地區。若要修改網站設定以便部署通話許可控制、E9-1-1 或媒體旁路，請執行 Set-CsNetworkSite Cmdlet 並分別搭配 BWPolicyProfileID 或 LocationPolicy 參數，修改網站設定。
    
    <div>
    

    > [!NOTE]  
    > 媒體旁路還有一個 BypassID 參數，但強烈建議您不要覆寫自動產生的旁路 ID。為媒體旁路設定網站時，不需要指定其他參數。

    
    </div>

3.  使用其他網站的設定重複執行步驟 2，完成修改拓撲的網站。

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台修改網站

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 **[站台]** 導覽按鈕。

4.  在表格中，按一下您要修改的網站。

5.  按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。

6.  在 **[編輯站台]** 頁面中，視需要變更此網站的設定值。

7.  按一下 **[認可]**。

8.  使用其他網站的設定重複執行步驟 4 至 7，完成修改網站。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

