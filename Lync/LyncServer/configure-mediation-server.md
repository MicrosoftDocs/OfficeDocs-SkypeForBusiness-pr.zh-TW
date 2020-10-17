---
title: 設定轉送伺服器
description: 設定轉送伺服器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5723d9446122b85f7bd1812f7c6f411c5c1c9dbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542999"
---
# <a name="configure-mediation-server"></a>設定轉送伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

本程式詳細說明設定 Lync Server 2013 集區使用 Lync Server 2013 轉送伺服器的步驟，而非舊版 Office 通訊伺服器的 2007 R2 轉送伺服器。

若要在新增或移除伺服器角色時順利發行、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和 Domain Admins 群組成員的使用者身分登入。您也可以委派適當的系統管理員權限與授權來新增伺服器角色。如需詳細資訊，請參閱 Standard Edition Server 或 Enterprise Edition Server 之部署文件中的委派設定權限。若要變更其他設定，只需具備 RTCUniversalServerAdmins 群組的成員資格即可。

<div>


> [!NOTE]  
> 如需尋找合格的 PSTN 閘道、IP PBXs 和 SIP 主幹服務（搭配 Lync Server 2013）的最新資訊，請參閱《 Microsoft 整合通訊開啟互通性程式》，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> 。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>使用拓撲產生器設定中繼伺服器

1.  從拓撲產生器開啟現有的拓撲。

2.  在左窗格中，瀏覽至 **[PSTN 閘道]**。

3.  以滑鼠右鍵按一下 [PSTN 閘道]****，然後按一下 [新增 IP/PSTN 閘道]****。

4.  在 **[定義新的 IP/PSTN 閘道]** 頁面中填入下列資訊：
    
      - 輸入閘道 FQDN 或 IP 位址。如果閘道使用 TLS 通訊協定，就需要閘道的 FQDN。
    
      - 接受 **[IP/PSTN 閘道的聆聽連接埠]** 的預設值；其如有修改，請輸入新的聆聽連接埠。
    
      - 設定 [Sip 傳輸通訊協定]****。

5.  在左窗格中，瀏覽至 [Enterprise Edition 前端集區]**** 或 [Standard Edition Server]****。

6.  以滑鼠右鍵按一下集區，然後按一下 [編輯屬性]****。

7.  在 **[中繼伺服器]** 底下，設定 **[聆聽連接埠]**。

8.  接著，選取新建的 PSTN 閘道並按一下 **[新增]**，建立關聯。

9.  在 **[拓撲產生器]** 中選取最頂端的節點 **[Lync Server]**。

10. 在 **[執行]** 功能表中，選取 **[發行拓撲]**，然後按 **[下一步]**。

11. 當 [發行精靈]**** 完成之後，按一下 [完成]****，以關閉精靈。

<div>


> [!NOTE]  
> 請務必完成下一個主題： <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">變更語音路由以使用新的 Lync server 2013 轉送伺服器</A> ，以確保語音路由指向正確的轉送伺服器。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

