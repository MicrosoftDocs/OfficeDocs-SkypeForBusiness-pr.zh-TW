---
title: Lync Server 2013：新增及啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1277887e6ed866a832edce276f21195fb74f6e92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499550"
---
# <a name="add-and-enable-user-account-for-lync-server-2013"></a>新增及啟用 Lync Server 2013 的使用者帳戶

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-02_

在 [Active Directory 使用者及電腦] 中啟用使用者帳戶之後，您可以使用 Lync Server 控制台，將 Active Directory 使用者新增至 Lync Server，以建立及啟用新的 Lync Server 2013 使用者帳戶。

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a>新增及啟用新的 Lync Server 使用者

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  按一下 **[啟用使用者]**。

5.  在 **[新增 Lync Server 使用者]** 對話方塊中，按一下 **[新增]**。

6.  在 [搜尋使用者]**** 方塊中，輸入您要找的 Active Directory 使用者帳戶的名稱、顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、電子郵件地址、使用者主要名稱 (UPN) 或電話號碼的全部或頭幾個字，然後按一下 [尋找]****。

7.  在表格中，選取您要新增至 Lync Server 的帳戶，然後按一下 **[確定]**。

8.  指派使用者至集區、指定其他詳細資料，並指派原則給您要的使用者，然後按一下 **[啟用]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[從 Lync Server 2013 移除使用者帳戶](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

