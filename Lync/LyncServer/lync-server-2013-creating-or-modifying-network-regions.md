---
title: Lync Server 2013：建立或修改網路地區
description: Lync Server 2013：建立或修改網路地區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02a041272f0df27d2133ca26096caeb01816c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544029"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路地區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

網路地區會與跨多個地理區域的網路不同部分交互連線。 每個網路地區都必須與中央網站產生關聯。 中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。 您可以使用 Lync Server 控制台設定網路地區。 網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。 在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路地區。 使用此主題可建立及修改網路地區。 如需刪除現有網路地區的詳細資訊，請參閱 [在 Lync Server 2013 中刪除現有的網路地區](lync-server-2013-deleting-existing-network-regions.md)。

<div>

## <a name="to-create-a-network-region"></a>建立網路地區

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。

4.  在 [ **地區** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **新地區** ] 頁面的 [ **名稱** ] 欄位中輸入值。 此值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。

6.  從 [ **中央網站** ] 下拉式清單中，選取這個網路地區的中央網站。

7.  根據預設，會選取 [ **啟用音訊替代路徑** ] 核取方塊。 此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送音訊通話。 只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。 如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。

8.  預設會選取 [ **啟用影片替代路徑** ] 核取方塊。 此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送影片。 只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。 如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。

9.   (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示的此地區的詳細資訊。

10. 按一下 **[認可]**。

**關聯的網站**資料表不會用來建立網路地區。 當您建立或修改網站時，會將網站與區域產生關聯。 如需詳細資訊，請參閱 [建立或修改 Lync Server 2013 中的網路網站](lync-server-2013-creating-or-modifying-network-sites.md)。

</div>

<div>

## <a name="to-modify-a-network-region"></a>若要修改網路地區

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。

4.  在 [ **地區** ] 頁面上，按一下您要修改的地區。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯地區** ] 頁面上，您可以修改啟用和停用音訊和影片替代路徑的設定，以及變更描述 (如需詳細資訊，請參閱本主題前面的「建立網路地區」一節。

7.  按一下 **[認可]**。

您無法在此頁面上修改 **相關聯的網站** 。 會提供相關網站的清單以供參考，因此當您修改地區設定時，您就會知道哪些網站會受到影響。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除現有的網路地區](lync-server-2013-deleting-existing-network-regions.md)  
[在 Lync Server 2013 中設定 CAC 的網路地區](lync-server-2013-configure-network-regions-for-cac.md)  


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

