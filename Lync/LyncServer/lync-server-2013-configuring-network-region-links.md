---
title: Lync Server 2013：設定網路地區連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363baeb3065b04dc936b69fff34f2314726f495a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526930"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路地區連結

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 網路中的地區是透過實體廣域網路 (WAN) 連線相連結。 您可以使用 Lync Server 控制台定義兩個網路地區之間的連結，並設定這些地區之間音訊和影片連線的頻寬限制。 如需刪除現有網路地區連結的詳細資訊，請參閱 [刪除網路地區連結的 Lync Server 2013](lync-server-2013-deleting-network-region-links.md)。

<div>

## <a name="to-create-a-network-region-link"></a>建立網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下左導覽列中的 [網路設定]****，然後按一下 [地區連結]****。

4.  在 [ **地區連結** ] 頁面上，按一下 [ **新增**]。

5.  在 [ **新增地區連結**] 的 [ **名稱** ] 欄位中輸入值。
    
    <div>
    

    > [!NOTE]  
    > 此值在 Lync Server 2013 部署中必須是唯一的。

    
    </div>

6.  從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個要連結的地區之一。

7.  從 [ **網路地區 \# 2** ] 下拉式清單中，選取要連結的其他地區。 此區域必須與為網路地區1所選取的區域不同 \# 。

8.   (選用) 若您想要在這些地區之間的音訊或視頻通話上進行頻寬限制，請從 [ **頻寬原則** ] 下拉式清單中選取頻寬原則設定檔。

9.  按一下 **[認可]**。

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>若要修改網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下左導覽列中的 [網路設定]****，然後按一下 [地區連結]****。

4.  在 [ **地區連結** ] 頁面上，按一下您要修改的地區連結。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 [ **編輯地區連結**] 中，您可以修改連結的區域或此連結的頻寬原則設定檔。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除網路地區連結](lync-server-2013-deleting-network-region-links.md)  


[新 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
