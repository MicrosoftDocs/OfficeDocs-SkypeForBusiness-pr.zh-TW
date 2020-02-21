---
title: 建立與裝載 Exchange UM 整合的 DNS SRV 記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c30164813619a271f2321db3ff3e8019067193c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>建立與裝載 Exchange UM 整合的 DNS SRV 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-20 個_

本主題說明如何設定網域名稱系統 (DNS) SRV 記錄所需的 Lync Server 2013 Edge Server 路由傳送至裝載的 Exchange 服務，例如 Microsoft Exchange Online。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>若要建立託管式 Exchange 服務的外部 DNS SRV 記錄

1.  以 DnsAdmins 群組成員身分登入外部 DNS 伺服器。

2.  依序按一下 [開始]****、[系統管理工具]**** 及 [DNS]****。

3.  在 [SIP 網域的主控台樹狀目錄，展開 [**正向對應區域**]，然後選取 [在要安裝 Lync Server 2013 的 SIP 網域。
    
    <div>
    

    > [!IMPORTANT]
    > 您必須在 Lync Server 是或安裝的 SIP 網域中建立 DNS SRV 記錄。 當您建立的 SRV 記錄時，用於提供此服務欄位主機的 FQDN 必須將 Edge 集區的外部 FQDN。 例如，如果您的 Edge 集區的外部 FQDN 是 edge01.contoso.net，請輸入這個值。 這也必須位於相同網域的 DNS 主機 (A) 記錄。

    
    </div>

4.  選取的網域，以滑鼠右鍵按一下，然後按一下 [**新增其他記錄**。

5.  在 [**資源記錄類型**] 中，按一下 [**服務位置 (SRV)**，，，然後按一下 [**建立記錄**。

6.  在 [**新增資源記錄**中，按一下**服務**]，然後輸入**\_sipfederationtls**。

7.  按一下 [**通訊協定**，然後輸入**\_tcp**。

8.  按一下 [**連接埠號碼**，然後輸入**5061**。

9.  按一下 [**提供這項服務的主機**，，然後輸入為信任的外部用戶端提供 Lync Server 2013 系統存取權的 Lync Server 2013 Edge 集區的 [完整的網域名稱 (FQDN)。
    
    <div>
    

    > [!NOTE]
    > 網域必須也設定為授權、 公認的網域在您的 Exchange Online 設定。 如需詳細資訊，請參閱建立公認的網域在<A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>。

    
    </div>

10. 按一下 [**確定**]，然後按一下 [**完成**。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>若要確認已成功建立 DNS SRV 記錄

1.  登入網域中的用戶端電腦。

2.  按一下 [開始]****，然後按一下 [執行]****。

3.  在命令提示字元中，執行下列命令：
    
        nslookup <FQDN Lync Edge Pool>

4.  確認您收到的 fqdn 解析為適當的 IP 位址的回覆。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立反向 proxy 伺服器的 DNS 記錄](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

