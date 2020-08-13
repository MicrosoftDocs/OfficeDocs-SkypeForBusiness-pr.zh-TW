---
title: Lync Server 2013：停用企業語音的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdcc6f69280357730e34f987f3c197db6950c285
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>停用 Lync Server 2013 的 Enterprise Voice 使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

使用下列程式可停用 Lync Server 2013 啟用之使用者帳戶的 Enterprise Voice。

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>停用 Enterprise Voice 的使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。

5.  在表格中，按一下您要為 Enterprise Voice 啟用的使用者帳戶。

6.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

7.  在 [ **編輯 Lync Server 使用者** ] 頁面的 [ **電話**語音] 下，按一下 [ **Enterprise Voice**以外的任何選項]。
    
    <div>
    

    > [!NOTE]  
    > 若要使用 Lync 限制使用者進行音訊或視頻通話，請在 [ <STRONG>電話語音</STRONG>] 下，按一下 [ <STRONG>音訊/視頻已停用</STRONG>]。

    
    </div>

8.  按一下 **[認可]**。

使用者現在無法使用 Enterprise Voice 功能。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中啟用使用者的 Enterprise Voice](lync-server-2013-enable-users-for-enterprise-voice.md)  


[在 Lync Server 2013 中管理使用者的企業語音](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 管理命令介面](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

