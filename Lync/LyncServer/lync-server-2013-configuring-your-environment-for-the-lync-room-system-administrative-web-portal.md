---
title: Lync Server 2013：為 Lync Room System Administrative Web Portal 設定您的環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef7596e65c44f871da8c26a0526a389dde72a45
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>為 Lync Room System Administrative Web Portal 設定您的 Lync Server 2013 環境

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-22_

若要使用 Lync 會議室系統（LRS）的系統管理網頁入口網站，您必須安裝或設定下列先決條件。

<div>


> [!IMPORTANT]  
> 如果伺服器已設定 Kerberos 和 NTLM 驗證，且 LRS 是在未加入網域的電腦上執行，Kerberos 驗證將會失敗，而且使用者將無法在系統管理入口網站中看到 LRS 的狀態。 若要解決此問題，請使用 NTLM 驗證或 NTLM 與 TLS DSK 驗證（沒有 Kerberos）來設定伺服器，或將 LRS 電腦加入網域。



</div>

1.  安裝 Lync Server 2013 累計更新： Lync Server 拓撲中的2013年7月。
    
    若要取得更新或查看其隨附的內容，請參閱[Lync Server 2013 的更新](http://go.microsoft.com/fwlink/p/?linkid=323959)。

2.  建立啟用 SIP 的 Active Directory 使用者。
    
    LRS 系統管理網頁入口網站使用這些認證來查詢 Lync Server 的資訊。 建議的使用者名稱為 LRSApp。

3.  使用 [名稱 LRSSupportAdminGroup] 建立 Active Directory 安全性群組。
    
    建立群組範圍為全域且群組類型為安全性的群組。 加入到這個群組的 SIP 啟用的使用者，都會獲授權查看聊天室清單並執行某些命令，例如收集記錄。

4.  使用 [名稱 LRSFullAccessAdminGroup] 建立 Active Directory 安全性群組。
    
    建立將群組範圍作為全域和群組類型做為安全性的群組。加入此群組的 SIP 啟用使用者已獲授權使用所有系統管理入口網站功能。
    
     
    
    具有安全性群組(images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "角色之管理員群組之")![安全性群組角色清單的管理員群組清單]  
    
     

5.  將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。
    
    ![LRSSupportAdminGroup 屬性 [成員] 頁面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 屬性 [成員] 頁面")  
    
     

6.  使用 [名稱 LRSSupport] 建立啟用 SIP 的 Active Directory 使用者。 將此使用者新增至 LRSSupportAdminGroup。
    
    ![LRSSupportAdminGroup 屬性 [成員] 頁面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 屬性 [成員] 頁面")  
    
     

7.  安裝適用于 Visual Studio 2010 SP1 及 Visual Web Developer 2010 SP1 的 ASP.NET MVC 4，請參閱 Microsoft 下載中心中[http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)的。

</div>

<span> </span>

</div>

</div>

</div>

