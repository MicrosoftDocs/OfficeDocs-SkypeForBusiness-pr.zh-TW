---
title: Lync Server 2013：建立或修改網路地區路由
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
ms.openlocfilehash: 0cdc05978b6fb8d81c81995d7b089d14ed4bec3b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516740"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改網路地區路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。 地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。 您可以使用 Lync Server 控制台設定網路地區路由。 在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路地區路由。 若要建立或修改網路地區路由，請利用本節主題。 如需刪除現有網路地區路由的詳細資訊，請參閱 [在 Lync Server 2013 中刪除現有的網路地區路由](lync-server-2013-deleting-existing-network-region-routes.md)。

<div>

## <a name="to-create-a-network-region-route"></a>若要建立網路地區路由

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[地區路由]**。

4.  在 **[地區路由]** 頁面上，按一下 **[新增]**。

5.  在 **[新的地區路由]** 的 **[名稱]** 欄位中，輸入一個值。
    
    <div>
    

    > [!NOTE]  
    > 此值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。

    
    </div>

6.  從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個區域中的其中一個要透過此路由來連線。

7.  從 [ **網路地區 \# 2** ] 下拉式清單中，選取此路由的其他地區。 此區域必須與為網路地區1所選取的區域不同 \# 。

8.  使用 **[網路地區連結]** 清單方塊，將地區連結新增至路由。按一下 **[新增]** 按鈕以顯示 **[地區連結]** 頁面。按一下要新增至此路由的地區連結，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 若要新增更多連結，請繼續按 <STRONG>[新增]</STRONG> 按鈕；若要移除連結，請選取連結，然後按一下 <STRONG>[移除]</STRONG>。

    
    </div>

9.  按一下 **[認可]**。

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>若要修改網路地區路由

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[地區路由]**。

4.  在 **[地區路由]** 頁面上，按一下您要修改的地區路由。

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 **[編輯地區路由]** 中，您可以修改此路由所聯結的地區，以及與路由相關聯的地區連結。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中刪除現有的網路地區路由](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

