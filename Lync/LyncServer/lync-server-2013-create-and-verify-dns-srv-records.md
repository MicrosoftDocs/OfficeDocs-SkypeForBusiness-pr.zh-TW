---
title: Lync Server 2013：建立並驗證 DNS SRV 記錄
description: Lync Server 2013：建立並驗證 DNS SRV 記錄。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71c876d0b26b9305feed7146fa6321a3983588d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562379"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>在 Lync Server 2013 中建立並驗證 DNS SRV 記錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

本主題說明如何在 Lync Server 2013 部署中設定網域名稱系統 (DNS) 記錄，以及自動用戶端登入所需的記錄。 當您建立前端集區時，安裝程式會為集區建立 Active Directory 物件和設定，包括集區的完整功能變數名稱 (FQDN) 。 為 Standard Edition server 建立類似的物件和設定。 若要讓用戶端能夠連線至集區或 Standard Edition 伺服器，則必須在 DNS 中登錄集區或 Standard Edition server 的 FQDN。 您必須在內部 DNS 中為每個 SIP 網域建立 DNS SRV 記錄。 此程式假設您的內部 DNS 具有您 SIP 使用者網域的區域。

<div>

## <a name="to-configure-a-dns-srv-record"></a>設定 DNS SRV 記錄

1.  在 DNS 伺服器上，按一下 [ **開始** ]，按一下 [系統 **管理工具** ]，然後按一下 [ **DNS** ]。

2.  在 SIP 網域的主控台樹中，展開 [ **正向對應區域** ]，然後在將安裝 Lync Server 2013 的 SIP 網域上按一下滑鼠右鍵。

3.  按一下 [ **其他新記錄** ]。

4.  在 [ **選取資源記錄類型** ] 中，按一下 [ **服務位置] (SRV)** ]，然後按一下 [ **建立記錄** ]。

5.  按一下 [ **服務** ]，然後輸入 **\_ sipinternaltls** 。

6.  按一下 [ **通訊協定** ]，然後輸入 **\_ tcp** 。

7.  按一下 [ **埠號碼** ]，然後輸入 **5061** 。

8.  按一下 [ **提供這項服務的主機** ]，然後輸入集區或 Standard Edition SERVER 的 FQDN。

9.  按一下 **[確定]** ，然後按一下 [ **完成** ]。

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>驗證 DNS SRV 記錄的建立

1.  使用已驗證使用者群組的成員帳戶，或具有相等許可權的帳戶，登入網域中的用戶端電腦。

2.  按一下 **[開始]** ，再按一下 **[執行]** 。

3.  在 [ **開啟** ] 方塊中輸入 **cmd** ，然後按一下 **[確定]** 。

4.  在命令提示字元中輸入 **nslookup** ，然後按 enter 鍵。

5.  輸入 **set type = srv** ，然後按 enter 鍵。

6.  輸入 **\_ sipinternaltls。 \_tcp.contoso.com** ，然後按 enter。 傳輸層安全性 (TLS) record 顯示的輸出如下：
    
    伺服器： \<dns server\> . contoso.com
    
    位址： \<IP address of DNS server\>
    
    非絕對回應：
    
    \_sipinternaltls。 \_tcp.contoso.com SRV 服務位置：
    
    priority = 0
    
    權數 = 0
    
    埠 = 5061
    
    svr hostname = poolname.contoso.com (或 Standard Edition server A record) 
    
    poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> 或（ \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> 或） \<IP address of the Standard Edition server\>

7.  完成後，請在命令提示字元處輸入 **exit** ，然後按 enter 鍵。

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>確認可解析前端集區或 Standard Edition server 的 FQDN

1.  登入網域中的用戶端電腦。

2.  按一下 **[開始]** ，再按一下 **[執行]** 。

3.  在 [ **開啟** ] 方塊中輸入 **cmd** ，然後按一下 **[確定]** 。

4.  在命令提示字元中輸入 **nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然後按 enter 鍵。

5.  請確認您收到的回復可解析為 FQDN 的適當 IP 位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

