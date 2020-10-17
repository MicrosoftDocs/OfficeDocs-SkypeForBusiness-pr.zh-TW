---
title: Lync Server 2013：設定 Lync 會議室系統管理 Web 入口網站的環境
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
ms.openlocfilehash: ea3269b9594df0597220648313ec79acfa329cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502100"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>設定 lync 會議室系統管理 Web 入口網站的 Lync Server 2013 環境

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-22_

若要使用 Lync 會議室系統 (LRS) 管理網頁入口網站，您必須安裝或設定下列必要條件。

<div>


> [!IMPORTANT]  
> 如果伺服器設定了 Kerberos 和 NTLM 驗證，且 LRS 是在未加入網域的電腦上執行，則 Kerberos 驗證會失敗，且使用者將不會在系統管理入口網站看到 LRS 的狀態。 若要解決此問題，請使用沒有 Kerberos) 的 ntlm 和 TLS DSK 驗證 (來設定伺服器，或將 LRS 電腦加入網域。



</div>

1.  安裝 Lync Server 2013 累計更新： Lync Server 拓撲中的7月2013。
    
    若要取得更新或查看其隨附的內容，請參閱 [Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=323959)。

2.  建立 SIP-enabled Active Directory 使用者。
    
    LRS 系統管理 Web 入口網站會使用這些認證來查詢 Lync Server 的資訊。 建議的使用者名稱是 LRSApp。

3.  使用 name LRSSupportAdminGroup 建立 Active Directory 安全性群組。
    
    以「全域」和「群組」類型為安全性的群組範圍建立群組。 新增至此群組的 SIP 啟用使用者可查看聊天室清單，並執行某些命令，例如收集記錄檔。

4.  使用名稱 LRSFullAccessAdminGroup 建立 Active Directory 安全性群組。
    
    以「全域」和「群組」類型為安全性的群組範圍建立群組。加入此群組的 SIP 啟用使用者已獲得授權，可使用所有系統管理員入口網站功能。
    
     
    
    ![具有安全性群組角色的系統管理員群組清單](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全性群組角色的系統管理員群組清單")  
    
     

5.  將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。
    
    ![LRSSupportAdminGroup 屬性成員] 頁面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 屬性成員] 頁面")  
    
     

6.  使用名稱 LRSSupport 建立啟用 SIP 的 Active Directory 使用者。 將此使用者新增至 LRSSupportAdminGroup。
    
    ![LRSSupportAdminGroup 屬性成員] 頁面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 屬性成員] 頁面")  
    
     

7.  在的 Microsoft 下載中心中，安裝 ASP.NET 的 MVC 4，以供 Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 使用 [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) 。

</div>

<span> </span>

</div>

</div>

</div>

