---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e00093859a6e252c019183617b4548dfc00218a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>更新 DNS SRV 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。

本主題說明如何在遷移至 Lync Server 2013 之後，更新網域名稱系統（DNS）記錄。 在已將所有使用者移至 Lync Server 2013 之後，但在解除舊版 Lync Server 2010 池或主管之前，您必須在內部 DNS 中為每個 SIP 網域更新 DNS SRV 記錄。 這個程式假設您的內部 DNS 擁有您 SIP 使用者網域的區域。

**若要設定 DNS SRV 記錄**

1.  在 DNS 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。

2.  在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，展開已安裝 Lync Server 2013 的 SIP 網域，然後流覽至** \_tcp**設定。

3.  在右窗格中，以滑鼠** \_** 按右鍵 [sipinternaltls]，然後選取 [**屬性**]。

4.  在**提供此服務的主機**中，更新主機 FQDN 以指向 Lync Server 2013 池。

5.  按一下 [確定]****。

**確認可以解析前端池或標準版伺服器的 FQDN**

1.  登入網域中的用戶端電腦。

2.  按一下 [**開始**]，然後按一下 [**執行**]。

3.  在 [**開啟**] 方塊中，輸入**cmd**，然後按一下 **[確定]**。

4.  在命令提示字元中， **** \<輸入頂層結束池\>的 nslookup FQDN 或\<標準版伺服器\>的 FQDN，然後按 enter。

5.  確認您收到的回復會解析為適當的 FQDN IP 位址。

</div>

<span> </span>

</div>

</div>

</div>

