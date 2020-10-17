---
title: Lync Server 2013：定義 SIP/CSTA 閘道 IP 位址
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
ms.openlocfilehash: a3a88aa2209617a93b0feebf7c1cc6d8cccd0cf7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516380"
---
# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

若 Lync Server 會使用傳輸控制通訊協定 (TCP) 連線，連接至您為遠端呼叫控制部署的 SIP/CSTA 閘道，則您必須在拓撲產生器中定義閘道的 IP 位址。 在支援傳輸層安全性 (TLS) 連線的閘道時，不需要此步驟。 對於任何支援 TLS 連線的閘道，您可以跳過此程式，並遵循在 [Lync Server 2013 中啟用 [遠端呼叫] 控制中的 [啟用 lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)] 中的步驟，繼續部署遠端呼叫控制。

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>使用拓撲產生器定義 SIP/CSTA 閘道 IP 位址

1.  以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。

2.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

3.  選擇下載現有拓撲的選項。

4.  展開 **[信任的應用程式伺服器]** 節點。

5.  以滑鼠右鍵按一下您所建立的信任應用程式集區（如在 [Lync Server 2013 中設定遠端呼叫控制的信任應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)中所述），然後按一下 [ **編輯屬性**]。

6.  清除 [ **啟用設定資料到此集區的** 複寫] 核取方塊。

7.  按一下 [ **將服務使用方式限制為選取的 IP 位址**]。 預設設定是 **使用所有設定的 IP 位址**。

8.  在 [ **主要 IP 位址** ] 文字方塊中，輸入 SIP/CSTA 閘道的 IP 位址。

9.  若要更新中央管理存放區中的拓撲，請按一下主控台樹中的 [ **Lync Server**]，然後從 [ **動作** ] 窗格中，按一下 [ **發佈**]。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定遠端呼叫控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

