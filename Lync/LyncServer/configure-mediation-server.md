---
title: 設定中繼伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>設定中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

此程式會詳細說明將 Lync Server 2013 池設定為使用 Lync Server 2013 轉送伺服器的步驟，而不是舊版 Office 通訊伺服器 2007 R2 轉送伺服器。

若要在新增或移除伺服器角色時成功發佈、啟用或停用拓撲，您應該以 RTCUniversalServerAdmins 和網域系統管理員群組成員的使用者身分登入。 您也可以委派適當的管理員權力和許可權來新增伺服器角色。 如需詳細資訊，請參閱標準版 server 或企業版 server 部署檔中的委派設定許可權。 針對其他設定變更，只需要 RTCUniversalServerAdmins 群組中的成員資格。

<div>


> [!NOTE]  
> 如需有關如何尋找符合 Lync Server 2013 之合格 PSTN 閘道、IP Pbx 及 SIP 中繼服務的最新資訊，請參閱「Microsoft 統一通訊開啟交互操作<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>性程式」。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>使用拓撲建立器設定中繼伺服器

1.  從拓撲建立器開啟現有的拓撲。

2.  在左窗格中，流覽至**PSTN 閘道**。

3.  以滑鼠右鍵按一下**PSTN 閘道**，然後按一下 [**新增 IP/PSTN 閘道**]。

4.  完成 [**定義新的 IP/PSTN 閘道**] 頁面，並提供下列資訊：
    
      - 輸入閘道 FQDN 或 IP 位址。 如果閘道使用 TLS 通訊協定，則需要閘道的 FQDN。
    
      - 接受**IP/PSTN 閘道偵聽埠**的預設值，或輸入新的偵聽埠（如果已修改的話）。
    
      - 設定**Sip 傳輸通訊協定**。

5.  在左窗格中，流覽至 [**企業版頂層端] 池**或 [**標準版] 伺服器**。

6.  以滑鼠右鍵按一下該池子，然後按一下 [**編輯屬性**]。

7.  在 [**中繼伺服器**] 底下，設定**偵聽埠**。

8.  接下來，選取新建立的 PSTN 閘道，然後按一下 [**新增**]。

9.  在 [**拓撲**建立器] 中，選取最上方的 [ **Lync Server**]。

10. 從 [**動作**] 功能表中，選取 [**發佈拓撲**]，然後按一下 **[下一步]**。

11. **發佈嚮導**完成後，請按一下 **[完成**] 以關閉嚮導。

<div>


> [!NOTE]  
> 請務必完成下一個主題，<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">將語音路由改為使用新的 Lync server 2013 轉送伺服器</A>，以確保語音路由指向正確的中繼伺服器。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

