---
title: Lync Server 2013： 設定您環境的 Lync 會議室系統管理入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c42b5541fb28646e4c01d9d070b67f6fe103234
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>設定 Lync Server 2013 環境的 Lync 會議室系統管理入口網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-22_

若要使用 Lync 會議室系統 (LRS) 系統管理員入口網站，您將需要安裝或設定下列必要條件。

<div>


> [!IMPORTANT]  
> 如果將伺服器設定 Kerberos 及 NTLM 驗證，而且 LRS 執行不會加入網域的電腦上，Kerberos 驗證會失敗，但使用者看不到 LRS 管理入口網站中的狀態。 若要解決此問題，請使用 NTLM 驗證] 或 [NTLM 和 TLS DSK 驗證 （不含 Kerberos)]，設定伺服器或 LRS 電腦加入網域。



</div>

1.  安裝 Lync Server 2013 累計更新： 7 月 2013 中的 Lync Server 拓撲。
    
    若要取得更新，或請參閱與其其中包含哪些功能，請參閱[Lync Server 2013 的更新](http://go.microsoft.com/fwlink/p/?linkid=323959)。

2.  建立已啟用 SIP 的 Active Directory 的使用者。
    
    LRS 管理入口網站會使用這些認證查詢資訊從 Lync Server。 建議的 username 是 LRSApp。

3.  建立 Active Directory 安全性群組名稱 LRSSupportAdminGroup。
    
    建立群組，其為全域群組領域] 和 [作為安全性的群組類型。 授權新增至這個群組的 SIP 啟用使用者看到的會議室清單和執行某些命令，如 [收集記錄檔。

4.  建立 Active Directory 安全性群組名稱 LRSFullAccessAdminGroup。
    
    建立做為全域系統管理員和群組類型的群組範圍群組為 Security.SIP 啟用的使用者新增至這個群組會獲授權使用所有的系統管理員入口網站的功能。
    
     
    
    ![系統管理員群組的清單與安全性群組角色](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "系統管理員群組的清單與安全性群組角色")  
    
     

5.  新增 LRSFullAccessAdminGroup 作為 LRSSupportAdminGroup 的成員。
    
    ![LRSSupportAdminGroup Properties 成員] 頁面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties 成員] 頁面")  
    
     

6.  以名稱 LRSSupport 建立 SIP 啟用 Active Directory 使用者。 此使用者新增至 LRSSupportAdminGroup。
    
    ![LRSSupportAdminGroup Properties 成員] 頁面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties 成員] 頁面")  
    
     

7.  Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1，用於在 Microsoft 下載中心取得安裝 ASP.NET MVC 4 [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)。

</div>

<span> </span>

</div>

</div>

</div>

