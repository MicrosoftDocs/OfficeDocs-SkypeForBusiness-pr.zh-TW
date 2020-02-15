---
title: Lync Server 2013： 定義 SIP/CSTA 閘道 IP 位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

如果您使用的傳輸控制通訊協定 (TCP) 連線部署遠端呼叫控制的 SIP/CSTA 閘道將連接 Lync 伺服器，您必須在拓撲產生器中定義閘道的 IP 位址。 這是不必要步驟支援傳輸層安全性 (TLS) 連線的閘道。 任何支援 TLS 連線的閘道，您可以略過此程序，然後繼續遠端呼叫控制的部署中[啟用 Lync 之使用者的 Lync Server 2013 中的遠端呼叫控制](lync-server-2013-enable-lync-users-for-remote-call-control.md)的步驟執行。

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>若要使用拓撲產生器定義 SIP/CSTA 閘道 IP 位址

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

3.  選擇下載現有拓撲的選項。

4.  展開 **[信任的應用程式伺服器]** 節點。

5.  以滑鼠右鍵按一下您建立的信任的應用程式集區[設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)，所述，然後按一下 [**編輯內容]**。

6.  清除 [**啟用組態資料複寫到此集區**] 核取方塊。

7.  按一下 [**選取 IP 位址限制服務使用情況**]。 預設值為**使用所有設定的 IP 位址**。

8.  在 [**主要 IP 位址**] 文字方塊中，輸入 SIP/CSTA 閘道的 IP 位址。

9.  若要更新的拓撲中的中央管理存放區，在主控台樹狀目錄中，[ **Lync Server**]，並再從 [**動作**] 窗格中，按一下 [**發佈**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定為遠端呼叫控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

