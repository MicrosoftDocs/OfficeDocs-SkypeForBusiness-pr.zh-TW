---
title: Lync Server 2013：建立或修改網站
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
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

通話許可控制（CAC）、E9-1-1 和媒體旁路部署，都依賴于定義的*網路網站*設定，且與網路區域之間永遠關聯。 網路網站代表分支辦公室位置、一組建築物或校園。 網路網站代表具有相似頻寬的子網集合。

使用下列程式來建立或修改網路網站。 例如，如果您已建立單一語音功能的網路網站，就不需要建立新的網路網站;其他語音功能將會使用相同的網站。 不過，您可能需要修改現有的網路網站定義，才能套用特定功能的設定。 例如，如果您已建立 E9 的網路網站-1-1，您需要在部署通話許可控制期間修改網路網站，以套用頻寬原則設定檔。

<div>


> [!NOTE]  
> 在其中，您可以找到網路網站的特定範例與需求，因為它們與每個功能之部署檔中的 [高級語音] 功能相關： 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中設定 CAC 的網路網站</A></P></LI></UL>



</div>

如需使用網路網站的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [新-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [移除-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>建立網路網站

建立可供通話許可控制、E9-1 或媒體旁路使用的網路區域。

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>使用管理命令介面建立網路網站

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsNetworkSite Cmdlet 來建立網路網站：
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    例如：
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    在這個範例中，您已建立名為「芝加哥」的網路網站，該網路網站是「北美」網路區域。
    
    <div>
    

    > [!NOTE]  
    > [北美] 網路區域必須已經存在，此命令才能順利執行。

    
    </div>

3.  若要為拓撲建立網路網站，請對 [其他網站] 的設定重複步驟2。

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立網路網站

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**網站導航**] 按鈕。

4.  按一下 [**新增**]。

5.  在 [**新網站**] 頁面上，按一下 [**名稱**]，然後輸入網路網站的名稱。

6.  按一下 [**地區**]，然後按一下清單中的區域。

7.  或者，按一下 [**頻寬原則**]，然後按一下清單中的頻寬原則。
    
    <div>
    

    > [!NOTE]  
    > 只有當您在網站上部署 [通話許可控制] 時，才需要頻寬原則。

    
    </div>

8.  或者，按一下 [**位置原則**]，然後按一下清單中的位置原則。
    
    <div>
    

    > [!NOTE]  
    > 只有當您在網站上部署 E9-1-1 時，才需要位置原則。

    
    </div>

9.  或者，按一下 [**描述**]，然後輸入說明此網路網站的其他資訊。

10. 按一下 [認可]****。

11. 若要為您的拓撲建立網路網站，請重複步驟4至10，並使用 [其他網站] 的設定。

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>修改網路網站

修改可供通話許可控制、E9-1 或媒體旁路使用的網路區域。

<div>

## <a name="to-modify-a-network-site"></a>修改網路網站

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 CsNetworkSite Cmdlet 來修改網路網站：
    
        Set-CsNetworkSite -Identity <string>
    
    例如：
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    在這個範例中，名為 "Albuquerque" 的網站會移至 [北美] 網路區域。 若要修改網路網站設定以部署呼叫許可控制、E9-1 或媒體旁路，請分別執行設定 CsNetworkSite Cmdlet 及 BWPolicyProfileID 或 LocationPolicy 參數，以修改網路網站設定。
    
    <div>
    

    > [!NOTE]  
    > 雖然 BypassID 參數存在於媒體旁路，但我們強烈建議您不要覆寫自動產生的旁路 Id。 您不需要指定其他參數，即可設定媒體旁路的網路網站。

    
    </div>

3.  若要完成拓撲的網路網站修改，請對 [其他網站] 的設定重複步驟2。

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 修改網路網站

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**網站導航**] 按鈕。

4.  在表格中，按一下您要修改的網路網站。

5.  按一下 [**編輯**]，然後按一下 [**顯示詳細資料 ...**]。

6.  在 [**編輯網站**] 頁面上，視需要變更此網路網站設定的值。

7.  按一下 [認可]****。

8.  若要完成修改網路網站，請重複步驟4至7及 [其他網站] 的設定。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

