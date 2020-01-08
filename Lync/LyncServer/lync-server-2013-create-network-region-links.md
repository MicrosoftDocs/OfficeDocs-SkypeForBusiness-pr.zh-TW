---
title: Lync Server 2013：建立網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c0f21f599b8afa4f9f31ec16aad82e305c8a08e
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40977229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中建立網路區域連結

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

網路中的區域是透過物理 WAN 連線來連結。 [*網路區域] 連結*會建立兩個設定為 [呼叫許可控制] （CAC）的區域之間的連結，並設定這些區域之間音訊與視頻流量的頻寬限制。

如需使用網路區域連結的詳細資訊，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [新-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [移除-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

此範例拓撲在北美與 APAC 區域之間有連結，以及 EMEA 與 APAC 區域之間的連結。 上述每一個區域連結都受 WAN 頻寬的限制，如範例中的區域連結頻寬資訊資料表所述：在規劃檔的 [Lync Server 2013] 區段中，[收集您對撥號許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面建立網路區域連結

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsNetworkRegionLink Cmdlet 來建立區域連結，並套用適當的頻寬原則設定檔。 例如，執行：
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立網路區域連結

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**網路**設定]。

3.  按一下 [**地區] 連結**瀏覽按鈕。

4.  按一下 [**新增**]。

5.  在 [**新增區域連結**] 頁面上，按一下 [**名稱**]，然後輸入網路區域連結的名稱。

6.  按一下 [**網路\#區域 1**]，然後按一下清單中您要連結至 [網路區域\#2] 的網路區域。

7.  按一下 [**網路\#區域 2**]，然後在清單中按一下您要連結至 [網路區域\#1] 的網路區域。

8.  或者，按一下 [**頻寬原則**]，然後選取您要套用到 [網路區域] 連結的頻寬原則設定檔。
    
    <div class=" ">
    

    > [!NOTE]  
    > 只有在 [網路區域] 連結受到頻寬限制且您想要使用 CAC 來控制該連結上的媒體流量時，才能套用頻寬原則。

    
    </div>

9.  按一下 [認可]****。

10. 若要為您的拓撲建立網路區域連結，請重複步驟4到9，以及其他地區的設定。

</div>

</div>

<span> </span>

</div>

</div>

</div>
