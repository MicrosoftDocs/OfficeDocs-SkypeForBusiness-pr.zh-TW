---
title: Lync Server 2013：設定網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895c85a80d3e5a7fadee3dccad25f9d89f04028a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中設定網路區域連結

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。 網路中的區域是透過物理廣域網路（WAN）連線來連結。 您可以使用 Lync Server [控制台] 定義兩個網路區域之間的連結，並設定這些區域之間音訊與視頻連線的頻寬限制。 如需有關刪除現有網路區域連結的詳細資訊，請參閱[刪除 Lync Server 2013 中的 [網路區域] 連結](lync-server-2013-deleting-network-region-links.md)。

<div>

## <a name="to-create-a-network-region-link"></a>建立網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下 [**新增**]。

5.  在 [**新區域] 連結**的 [**名稱**] 欄位中輸入值。
    
    <div>
    

    > [!NOTE]  
    > 這個值在您的 Lync Server 2013 部署中必須是唯一的。

    
    </div>

6.  從 [**網路區域\#1** ] 下拉式清單中，選取兩個要連結的區域之一。

7.  從 [**網路區域\#2** ] 下拉式清單中，選取要連結的其他區域。 這個區域必須與針對 [網路區\#1] 所選取的區域不同。

8.  可選如果您想要將頻寬限制放在這些區域之間的音訊或視頻通話中，請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔。

9.  按一下 [認可]****。

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>修改網路區域連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下您要修改的區域連結。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯區域] 連結**中，您可以修改連結的區域或此連結的頻寬原則設定檔。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[刪除 Lync Server 2013 中的 [網路區域] 連結](lync-server-2013-deleting-network-region-links.md)  


[新-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[移除-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
