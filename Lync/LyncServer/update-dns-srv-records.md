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
ms.openlocfilehash: ef1440740e8fc25f5873dcb7bbdf5e8db953f6cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>更新 DNS SRV 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-29_

若要順利完成此程序，您應該伺服器或網域的 Domain Admins 群組成員或 DnsAdmins 群組成員登入。

本主題說明如何移轉至 Lync Server 2013 之後更新的網域名稱系統 (DNS) 記錄。 所有使用者已將其都移至 Lync Server 2013，但之前的舊版的 Lync Server 2010 集區或委任 Director 之後，您必須在每個 SIP 網域的內部部署 DNS 中更新 DNS SRV 記錄。 此程序假設您的內部 DNS 有 SIP 使用者網域的區域。

**若要設定 DNS SRV 記錄**

1.  在 DNS 伺服器上，按一下 [**開始]**、 [**系統管理工具**] 和 [ **DNS**。

2.  在 [SIP 網域的主控台樹狀目錄，請依序展開 [**正向對應區域**，展開 SIP 網域中安裝 Lync Server 2013，並瀏覽至**\_tcp**設定。

3.  在右窗格中，以滑鼠右鍵按一下 [ ** \_sipinternaltls**並選取 [**內容**]。

4.  在 [**提供這項服務的主機**，更新主機 FQDN 以指向 Lync Server 2013 集區。

5.  按一下 [確定]****。

**若要確認可以解析前端集區或 Standard Edition server 的 FQDN**

1.  登入網域中的用戶端電腦。

2.  按一下 [開始]****，然後按一下 [執行]****。

3.  在 [**開啟**] 方塊中輸入**cmd**，，然後按一下 [**確定]**。

4.  在命令提示字元處，輸入**nslookup** \<的前端集區 FQDN\>或\<Standard Edition server 的 FQDN\>，然後按 ENTER 鍵。

5.  確認您收到的 fqdn 解析為適當的 IP 位址的回覆。

</div>

<span> </span>

</div>

</div>

</div>

