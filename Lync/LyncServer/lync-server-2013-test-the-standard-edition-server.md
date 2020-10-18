---
title: Lync Server 2013：測試 Standard Edition Server
description: Lync Server 2013：測試 Standard Edition Server。
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
ms.openlocfilehash: 35dc13fc01979cc8b293d0647a7886b7d65d7669
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576007"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Standard Edition server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

下列程式說明如何測試 Standard Edition server 的部署。

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>若要測試 Standard Edition Server 的部署

1.  使用 [Active Directory 電腦和使用者] 將 lync server 2013 部署 (的系統管理員角色的 Active Directory 使用者物件，加入) **CSAdministrator** 群組中的「安裝 lync Server」控制台。

2.  如果使用者物件目前已登入，請先登出再登入，以註冊新的群組指派。
    
    <div>
    

    > [!NOTE]  
    > 使用者帳戶不可以是執行 Lync Server 2013，Standard Edition 之伺服器的本機系統管理員。 如果您未將適當的使用者和群組新增至 CsAdministors 群組，當您開啟 Lync Server 2013 控制台時，將會收到錯誤訊息，指出「未經授權：存取因角色型的存取控制 (RBAC) 授權失敗」而遭到拒絕。

    
    </div>

3.  使用系統管理帳戶登入安裝 Lync Server 控制台的電腦。

4.  啟動 Lync Server 控制台，並在出現提示時提供認證。 Lync Server 2013 控制台會顯示部署資訊。

5.  在左導覽列中，按一下 [ **拓撲**]，然後確認服務狀態是具有綠色箭頭的電腦圖示，且每個已部署並聯機的 Lync server server role 旁邊都有綠色核取記號。

6.  在左導覽列中，按一下 [ **使用者**]，然後啟用兩個使用者的 Lync Server 2013。

7.  將一個使用者登入已加入網域的電腦，並將另一個使用者登入網域中的另一部電腦。

8.  在兩部用戶端電腦上安裝 Lync Server 2013，然後確認這兩位使用者皆可登入 Lync Server 2013，而且可以傳送立即訊息給對方。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

