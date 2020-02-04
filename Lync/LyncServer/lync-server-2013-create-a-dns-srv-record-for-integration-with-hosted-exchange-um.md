---
title: 針對與主控 Exchange UM 的整合建立 DNS SRV 記錄
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
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>針對與主控 Exchange UM 的整合建立 DNS SRV 記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

本主題描述如何設定 Lync Server 2013 Edge 伺服器傳送到託管 Exchange 服務（例如 Microsoft Exchange Online）所需的網域名稱系統（DNS） SRV 記錄。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>若要建立託管 Exchange 服務的外部 DNS SRV 記錄

1.  以 DnsAdmins 群組成員的身分登入外部 DNS 伺服器。

2.  按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。

3.  在您 SIP 網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後選取將安裝 Lync Server 2013 的 SIP 網域。
    
    <div>
    

    > [!IMPORTANT]
    > 您必須在安裝 Lync Server 的 SIP 網域中建立 DNS SRV 記錄。 當您建立 SRV 記錄時，用於提供此服務欄位之主機的 FQDN 必須是 Edge 池的外部 FQDN。 例如，如果 Edge 池的外部 FQDN 是 edge01.contoso.net，請輸入此值。 這也必須與 DNS 主機（A）記錄位於同一個網域中。

    
    </div>

4.  以滑鼠右鍵按一下選取的網域，然後按一下 [**其他新記錄**]。

5.  在 [**資源記錄類型**] 中，按一下 **[服務位置（SRV）**]，然後按一下 [**建立記錄**]。

6.  在 [**新增資源記錄**] 中，按一下 [**服務**]，然後輸入** \_sipfederationtls**。

7.  按一下 [**通訊協定**]，然後輸入** \_tcp**。

8.  按一下 [**埠號碼**]，然後輸入**5061**。

9.  按一下 [**主機提供此服務**]，然後輸入 lync Server 2013 Edge 池的完整功能變數名稱（FQDN），提供對您的 lync server 2013 系統（適用于信任的外部用戶端）的存取權。
    
    <div>
    

    > [!NOTE]
    > 網域也必須在 Exchange Online 設定中設定為權威性、已接受的網域。 如需詳細資訊，請參閱在<A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>上建立接受的網域。

    
    </div>

10. 按一下 **[確定]**，然後按一下 [**完成**]。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>確認已成功建立 DNS SRV 記錄

1.  登入網域中的用戶端電腦。

2.  按一下 [**開始**]，然後按一下 [**執行**]。

3.  在命令提示字元中，執行下列命令：
    
        nslookup <FQDN Lync Edge Pool>

4.  確認您收到的回復會解析為適當的 FQDN IP 位址。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立反向 Proxy 伺服器的 DNS 記錄](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

