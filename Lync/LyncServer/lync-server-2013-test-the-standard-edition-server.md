---
title: Lync Server 2013： 測試 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d22a904005637ffcc6675f1e70328c3dad6f53
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Standard Edition server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

下列程序說明如何測試 Standard Edition server 的部署。

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>若要測試 Standard Edition Server 的部署

1.  將 Lync Server 2013 部署 （Lync Server Control Panel 安裝所在） 中系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組使用 Active Directory 電腦和使用者。

2.  如果使用者物件目前登入，請先登出，然後再次登入註冊新的群組指派。
    
    <div>
    

    > [!NOTE]  
    > 使用者帳戶不能執行 Lync Server 2013，標準版之伺服器的本機系統管理員。 如果您未加入至 CsAdministors 群組新增適當的使用者和群組，您就會收到錯誤，當開啟 Lync Server 2013 控制台]，表示 「 未授權： 存取被拒，因為角色型存取控制 (RBAC) 授權失敗。 」

    
    </div>

3.  使用系統管理帳戶來登入電腦已安裝 Lync Server Control Panel。

4.  啟動 Lync Server Control Panel，並提供認證，如果系統提示。 Lync Server 2013 Control Panel 顯示部署資訊。

5.  在左的導覽列中，[**拓撲**]，然後確認服務狀態是帶有綠色箭頭的電腦圖示，而且沒有每個已部署且上線的 Lync Server 伺服器角色旁的綠色核取記號。

6.  在左的導覽列中，按一下 [**使用者**]，然後啟用 Lync Server 2013 的兩個使用者。

7.  一個使用者登入已加入網域的電腦並其他使用者登入另一部電腦的網域中。

8.  在每個兩部用戶端電腦上安裝 Lync Server 2013，然後確認 [兩個使用者可以登入 Lync Server 2013，並傳送立即訊息給對方。

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署用戶端和 Lync Server 2013 中的裝置](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

