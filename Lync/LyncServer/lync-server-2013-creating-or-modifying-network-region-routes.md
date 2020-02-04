---
title: Lync Server 2013：建立或修改網路區域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路區路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。 雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。 您可以使用 Lync Server [控制台] 來設定網路區域路由。 您可以從 Lync Server [控制台] 建立、修改或刪除網路區域路由。 使用本主題來建立或修改網路區域路由。 如需有關刪除現有網路區域路由的詳細資訊，請參閱[在 Lync Server 2013 中刪除現有的網路區域路由](lync-server-2013-deleting-existing-network-region-routes.md)。

<div>

## <a name="to-create-a-network-region-route"></a>建立網路區域路由

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。

4.  在 [**地區路線**] 頁面上，按一下 [**新增**]。

5.  在 [**新區域路由**] 中，于 [**名稱**] 欄位中輸入值。
    
    <div>
    

    > [!NOTE]  
    > 這個值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。

    
    </div>

6.  從 [**網路區域\#1** ] 下拉式清單中，選取要由此路由連接的兩個區域中的其中一個。

7.  從 [**網路區域\#2** ] 下拉式清單中，選取此路由的另一個區域。 這個區域必須與針對 [網路區\#1] 所選取的區域不同。

8.  使用 [**網路區域連結**] 清單方塊來新增路由的區域連結。 按一下 [**新增**] 按鈕以顯示 [**地區連結**] 頁面。 按一下要新增至此路線的區域連結，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 繼續按一下 [<STRONG>新增</STRONG>] 按鈕以新增更多連結，或選取連結，然後按一下 [<STRONG>移除</STRONG>] 以移除連結。

    
    </div>

9.  按一下 [認可]****。

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>修改網路區域路由

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。

4.  在 [**地區路線**] 頁面上，按一下您要修改的地區路線。

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯區域] 路由**中，您可以修改由此路由加入的區域，以及與路由相關聯的區域連結。

7.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中刪除現有的網路區域路由](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

