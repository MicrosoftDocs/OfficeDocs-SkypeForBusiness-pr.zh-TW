---
title: Lync Server 2013：安裝 Lync 會議室系統管理 Web 入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b772311865a36ba17699fc876c32c5504214e5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534900"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>在 Lync Server 2013 中安裝 Lync 會議室系統管理 Web 入口網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-04-09_

您可以從 Microsoft 下載中心下載 Microsoft Lync 會議室系統管理 Web 入口網站 [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) 。

若要安裝 Lync 會議室系統管理 Web 入口網站，請使用下列步驟。

1.  在 Lync Server 管理命令介面中執行下列 Cmdlet，以設定信任的應用程式埠：
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  若要安裝會議室入口網站，請下載 **LyncRoomAdminPortal.exe** ，然後以系統管理員身分執行。

3.  從下列位置開啟 Web.config 檔案：
    
    % Program Files% \\ Microsoft Lync Server 2013 \\ 網頁元件 \\ 會議室入口網站 \\ Int \\ 處理常式\\

4.  在 Web.Config 檔案中，將 PortalUserName 變更為在步驟2中建立的使用者名稱，並在 [設定 Lync 會議室系統管理員入口網站的必要條件] 區段下， (步驟中的建議名稱是 LRSApp) ：
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  由於 LRS 系統管理入口網站是信任的應用程式，因此您不需要在入口網站設定中提供密碼。 若此使用者使用不同的註冊機構，您必須在 Web.Config 檔案中新增下列一行，以指定其註冊機構：
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  如果使用的埠不是5061，請在 Web.Config 檔案中新增下行：
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>驗證 Lync 會議室系統管理 Web 入口網站的安裝

若要驗證 Lync 會議室系統管理 Web 入口網站的安裝，請執行下列操作：


1.  在前端伺服器上，流覽至下列 URL:
    
    HTTPs:// \<fe-server\> /lrs
    
    您不應該看到任何錯誤，如下圖所示：
    
    ![Lync 會議室系統管理入口網站登錄畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理入口網站登錄畫面")

2.  如果您未看到任何錯誤，請嘗試從拓撲中的任何其他電腦存取下列 URL：
    
    HTTPs:// \<fe-server\> /lrs
    
    若要存取此頁面，您必須以「自動用戶端 Sign-In 所需的 DNS 記錄」所述，新增 DNS 記錄 [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

