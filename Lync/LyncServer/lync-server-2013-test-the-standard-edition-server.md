---
title: Lync Server 2013：測試 Standard Edition Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Standard Edition Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

下列程式說明如何測試標準版伺服器的部署。

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>測試標準版伺服器的部署

1.  使用 Active Directory 電腦和使用者將 Lync Server 2013 部署（安裝 Lync Server 控制台）的系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組。

2.  如果使用者物件目前已登入，請先登出後再登入，以註冊新的群組指派。
    
    <div>
    

    > [!NOTE]  
    > 使用者帳戶不能是執行 Lync Server 2013 標準版伺服器的本機系統管理員。 如果您沒有將適當的使用者和群組新增至 CsAdministors 群組，當您開啟 Lync Server 2013 控制台時，會收到錯誤訊息，指出「未授權：存取權因角色式存取控制（RBAC）授權失敗」而遭到拒絕。」

    
    </div>

3.  使用 [系統管理] 帳戶登入安裝 Lync Server [控制台] 的電腦。

4.  如果出現提示，請啟動 Lync Server 的 [控制台] 並提供認證。 Lync Server 2013 [控制台] 會顯示部署資訊。

5.  在左側導覽列中，按一下 [**拓撲**]，然後確認 [服務狀態] 是電腦圖示，且已部署並線上的每個 Lync server 伺服器角色旁邊都有一個綠色的核取記號。

6.  在左側導覽列中，按一下 [**使用者**]，然後啟用兩個使用者的 Lync Server 2013。

7.  在已加入網域的電腦上登入一個使用者，並將另一個使用者登入到網域中的另一部電腦。

8.  在兩個用戶端電腦上安裝 Lync Server 2013，然後確認這兩個使用者都可以登入 Lync Server 2013，而且可以傳送立即訊息給對方。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

