---
title: Lync Server 2013： 建立並確認 DNS SRV 記錄
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
ms.openlocfilehash: c7faf0cd00b59d5df5bab1650a28eff8b9563f91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>建立並確認 Lync Server 2013 中的 DNS SRV 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

本主題說明如何設定您所建立的 Lync Server 2013 部署以及所需的用戶端自動登入的網域名稱系統 (DNS) 記錄。 當您建立前端集區時，安裝程式會建立集區，包括集區完整的網域名稱 (FQDN) 設定及 Active Directory 物件。 Standard Edition server 建立類似物件和設定。 若要能夠連線到集區或 Standard Edition server 的用戶端，集區或 Standard Edition server 的 FQDN 必須登錄在 DNS 中。 您必須針對每個 SIP 網域內部部署 DNS 中建立 DNS SRV 記錄。 此程序假設您的內部 DNS 有 SIP 使用者網域的區域。

<div>

## <a name="to-configure-a-dns-srv-record"></a>若要設定 DNS SRV 記錄

1.  在 DNS 伺服器上，按一下 [**開始]**、 [**系統管理工具**] 和 [ **DNS**。

2.  在 SIP 網域的主控台樹狀目錄，展開 [**正向對應區域**，，然後在要安裝 Lync Server 2013 的 SIP 網域上按一下滑鼠右鍵。

3.  按一下 [**新增其他記錄**]。

4.  在 [**選擇資源記錄類型**，按一下 [**服務位置 (SRV)**，，，然後按一下 [**建立記錄**。

5.  按一下 [**服務**]，然後輸入**\_sipinternaltls**。

6.  按一下 [**通訊協定**，然後輸入**\_tcp**。

7.  按一下 [**連接埠號碼**，然後輸入**5061**。

8.  按一下 [**提供這項服務的主機**，，，然後輸入集區或 Standard Edition server 的 FQDN。

9.  按一下 [**確定**]，然後按一下 [**完成**。

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>若要確認 DNS SRV 記錄的建立

1.  以 Authenticated Users 群組成員或具有相等權限的帳戶的網域中的用戶端電腦登入。

2.  按一下 [開始]****，然後按一下 [執行]****。

3.  在 [**開啟**] 方塊中輸入**cmd**，，然後按一下 [**確定]**。

4.  在命令提示字元處，輸入**nslookup**，，然後按 ENTER。

5.  型別**設定 type = srv**，然後按 ENTER 鍵。

6.  類型**\_sipinternaltls。\_tcp.contoso.com**，然後按 ENTER 鍵。 顯示傳輸層安全性 (TLS) 記錄的輸出是，如下所示：
    
    Server: \<dns server\>。 contoso.com
    
    地址： \<DNS 伺服器 IP 位址\>
    
    非代表性頁面的答案：
    
    \_sipinternaltls。\_tcp.contoso.com SRV 服務位置：
    
    優先順序 = 0
    
    weight = 0
    
    連接埠 = 5061
    
    svr hostname = poolname.contoso.com （或 Standard Edition server A 記錄）
    
    poolname.contoso.com internet address =\<負載平衡器虛擬 IP 位址\>或\<只能有一個 Enterprise Edition 伺服器與集區的單一 Enterprise Edition 伺服器的 IP 位址\>或\<Standard Edition server 的 IP 位址\>

7.  完成時，在命令提示字元處，輸入**exit**，並按 ENTER。

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>若要確認可以解析前端集區或 Standard Edition server 的 FQDN

1.  登入網域中的用戶端電腦。

2.  按一下 [開始]****，然後按一下 [執行]****。

3.  在 [**開啟**] 方塊中輸入**cmd**，，然後按一下 [**確定]**。

4.  在命令提示字元處，輸入**nslookup** \<的前端集區 FQDN\>或\<Standard Edition server 的 FQDN\>，然後按 ENTER 鍵。

5.  確認您收到的 fqdn 解析為適當的 IP 位址的回覆。

</div>

</div>

<span> </span>

</div>

</div>

</div>

