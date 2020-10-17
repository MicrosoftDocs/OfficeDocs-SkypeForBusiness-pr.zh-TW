---
title: Lync Server 2013：建立網路地區連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e8c3d0fd254ba780b91d554402ca38d30f7073
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515560"
---
# <a name="create-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中建立網路地區連結

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

網路中的區域是透過實體 WAN 連線相互連結。 *網路地區連結*會在設定為通話許可控制的兩個地區之間建立連結 (CAC) 並設定這些地區之間音訊和影片流量的頻寬限制。

如需使用網路地區連結的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [新 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

這個範例拓撲有一個北美和 APAC 地區之間的連結，以及 EMEA 和 APAC 地區之間的連結。 每個地區連結都受 WAN 頻寬限制，如範例中的地區連結頻寬資訊表格所述：在規劃檔的 [ [Lync Server 2013] 區段中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面建立網路地區連結

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 New-CsNetworkRegionLink Cmdlet 來建立地區連結，並套用適當的頻寬原則設定檔。 例如，執行：
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台建立網路地區連結

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 **[網路組態]**。

3.  按一下 [ **地區連結** ] 導覽按鈕。

4.  按一下 [ **新增**]。

5.  在 [ **新增地區連結** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路地區連結的名稱。

6.  按一下 [ **網路地區 \# 1**]，然後按一下清單中要連結至 [網路地區 2] 的網路地區 \# 。

7.  按一下 [ **網路地區 \# 2**]，然後按一下清單中要連結至 [網路地區 1] 的網路地區 \# 。

8.  （選用）按一下 [ **頻寬原則**]，然後選取您要套用到網路地區連結的頻寬原則設定檔。
    
    <div class=" ">
    

    > [!NOTE]  
    > [！注意事項] 只有在網路地區連結受到頻寬限制，且您想要使用 CAC 來控制該連結上的媒體流量時，才套用頻寬原則。

    
    </div>

9.  按一下 **[認可]**。

10. 若要完成建立拓撲的網路地區連結，請使用其他地區的設定重複步驟4到9。

</div>

</div>

<span> </span>

</div>

</div>

</div>
