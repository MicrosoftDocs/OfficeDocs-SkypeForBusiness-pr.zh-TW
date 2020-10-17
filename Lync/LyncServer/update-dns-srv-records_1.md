---
title: 更新 DNS SRV 記錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf77df16b7681cf6cfd3c1608f1adb40e2e09f43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527190"
---
# <a name="update-dns-srv-records"></a>更新 DNS SRV 記錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

本主題說明如何在遷移至 Lync Server 2013 之後，更新網域名稱系統 (DNS) 記錄。 將所有使用者移至 Lync Server 2013 之後，但在解除舊版 Office 通訊伺服器 2007 R2 集區或 Director 之前，您必須針對每個 SIP 網域更新內部 DNS 中的 DNS SRV 記錄。 此程式假設您的內部 DNS 具有您 SIP 使用者網域的區域。

**設定 DNS SRV 記錄**

1.  在 DNS 伺服器上，按一下 [ **開始**]，按一下 [系統 **管理工具**]，然後按一下 [ **DNS**]。

2.  在 SIP 網域的主控台樹中，展開 [**正向對應區域**]，展開 [已安裝 Lync Server 2013 的 SIP 網域]，然後流覽至 [ ** \_ tcp** ] 設定。

3.  在右窗格中，以滑鼠右鍵按一下 [ ** \_ sipinternaltls** ]，然後選取 [**屬性**]。

4.  在 [ **提供這項服務的主機**] 中，將主機 FQDN 更新為指向 Lync Server 2013 集區。

5.  按一下 [確定]****。

**確認可解析前端集區或 Standard Edition server 的 FQDN**

1.  登入網域中的用戶端電腦。

2.  按一下 **[開始]**，再按一下 **[執行]**。

3.  在 [ **開啟** ] 方塊中輸入 **cmd**，然後按一下 **[確定]**。

4.  在命令提示字元中輸入 **nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然後按 enter 鍵。

5.  請確認您收到的回復可解析為 FQDN 的適當 IP 位址。

</div>

<span> </span>

</div>

</div>

</div>

