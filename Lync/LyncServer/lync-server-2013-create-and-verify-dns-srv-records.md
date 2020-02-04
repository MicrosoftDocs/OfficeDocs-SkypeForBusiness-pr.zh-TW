---
title: Lync Server 2013：建立並驗證 DNS SRV 記錄
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
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>在 Lync Server 2013 中建立並驗證 DNS SRV 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

若要成功完成此程式，您必須以網域管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。

本主題描述如何設定您必須在 Lync Server 2013 部署中建立的網域名稱系統（DNS）記錄，以及自動用戶端登入所需的網域名稱系統（DNS）記錄。 當您建立 [前端] 池時，安裝程式會為該池建立 Active Directory 物件和設定，包括 pool 完全限定的功能變數名稱（FQDN）。 針對標準版伺服器建立類似的物件和設定。 針對能連線到 pool 或 Standard Edition 伺服器的用戶端，必須在 DNS 中註冊 pool 或 Standard Edition server 的 FQDN。 您必須在內部 DNS 中為每個 SIP 網域建立 DNS SRV 記錄。 這個程式假設您的內部 DNS 擁有您 SIP 使用者網域的區域。

<div>

## <a name="to-configure-a-dns-srv-record"></a>若要設定 DNS SRV 記錄

1.  在 DNS 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。

2.  在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下將安裝 Lync Server 2013 的 SIP 網域。

3.  按一下 [**其他新記錄**]。

4.  在 [**選取資源記錄類型**] 中，按一下 **[服務位置（SRV）**]，然後按一下 [**建立記錄**]。

5.  按一下 [**服務**]，然後輸入** \_sipinternaltls**。

6.  按一下 [**通訊協定**]，然後輸入** \_tcp**。

7.  按一下 [**埠號碼**]，然後輸入**5061**。

8.  按一下 [**主機提供此服務**]，然後輸入 Pool 或 Standard Edition 伺服器的 FQDN。

9.  按一下 **[確定]**，然後按一下 [**完成**]。

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>驗證 DNS SRV 記錄的建立

1.  以已驗證使用者群組成員的帳戶登入網域中的用戶端電腦，或擁有同等許可權。

2.  按一下 [**開始**]，然後按一下 [**執行**]。

3.  在 [**開啟**] 方塊中，輸入**cmd**，然後按一下 **[確定]**。

4.  在命令提示字元中，輸入**nslookup**，然後按 enter 鍵。

5.  輸入**set type = srv**，然後按 enter。

6.  輸入** \_sipinternaltls。\_tcp.contoso.com**，然後按 enter。 針對傳輸層安全性（TLS）記錄顯示的輸出如下所示：
    
    伺服器： \<dns 伺服器\>. contoso.com
    
    Address （ \<位址）： DNS 伺服器的 IP 位址\>
    
    非權威性的答案：
    
    \_sipinternaltls.\_tcp.contoso.com SRV 服務位置：
    
    優先順序 = 0
    
    權數 = 0
    
    port = 5061
    
    svr hostname = poolname.contoso.com （或標準版伺服器 A 記錄）
    
    poolname.contoso.com 網際網路位址 = \<單一企業版伺服器的負載平衡\>器\<或 ip 位址的虛擬 IP 位址，其中只有一個企業版 server\>或\<標準版伺服器的 ip 位址\>

7.  完成時，請在命令提示字元中輸入**exit**，然後按 enter 鍵。

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>確認可以解析前端池或標準版伺服器的 FQDN

1.  登入網域中的用戶端電腦。

2.  按一下 [**開始**]，然後按一下 [**執行**]。

3.  在 [**開啟**] 方塊中，輸入**cmd**，然後按一下 **[確定]**。

4.  在命令提示字元中， **** \<輸入頂層結束池\>的 nslookup FQDN 或\<標準版伺服器\>的 FQDN，然後按 enter。

5.  確認您收到的回復會解析為適當的 FQDN IP 位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

