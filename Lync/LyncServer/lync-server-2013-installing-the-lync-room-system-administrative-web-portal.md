---
title: Lync Server 2013： 安裝 Lync 會議室系統管理的入口網站
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
ms.openlocfilehash: 24757a87279f64dd903ed4fdfb26169b606f899c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>安裝 Lync Server 2013 中的 Lync 會議室系統管理的入口網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-04-09_

您可以從 Microsoft 下載中心下載 Microsoft Lync 會議室系統管理入口網站[https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044)。

若要安裝 Lync 會議室系統管理入口網站，請使用下列步驟。

1.  在 Lync Server 管理命令介面中執行下列 cmdlet 來設定信任的應用程式連接埠：
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  若要安裝會議會議室入口網站，請下載**LyncRoomAdminPortal.exe**並再執行身為系統管理員。

3.  開啟 Web.config 檔案，從下列位置：
    
    %程式檔案 %\\Microsoft Lync Server 2013\\Web 元件\\會議會議室入口網站\\Int\\處理常式\\

4.  在 Web.Config 檔案中，變更 PortalUserName 為在步驟 2 中建立的 「 設定必要條件的 Lync 會議室系統管理員入口網站 」 （中步驟的建議的名稱是 LRSApp）] 區段下的使用者名稱：
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  因為 LRS 系統管理入口網站中的受信任的應用程式，您不需要提供入口網站設定中的密碼。 如果此使用者使用本機登錄器比其他註冊機構，您需要指定它的登錄器的 Web.Config 檔案中加入下行：
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  如果使用的連接埠 5061 以外，請在 Web.Config 檔案中加入下列一行：
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>確認 Lync 會議室系統管理 Web 入口網站的安裝

若要確認安裝 Lync 會議室系統管理入口網站，請執行下列動作：


1.  在前端伺服器上，瀏覽至下列 URL:
    
    https://\<fe-server\>/lrs
    
    下圖所示，應該不會看到任何錯誤：
    
    ![Lync 會議室系統管理員入口網站登入畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理員入口網站登入畫面")

2.  如果看不到任何錯誤，請嘗試從拓撲中的任何其他電腦存取下列 URL:
    
    https://\<fe-server\>/lrs
    
    若要存取 [] 頁面上，您必須新增 DNS 記錄所述的 「 需要 DNS 記錄的自動用戶端登入 」 在[https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

