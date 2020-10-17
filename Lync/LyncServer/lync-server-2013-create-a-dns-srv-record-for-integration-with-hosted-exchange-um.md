---
title: 建立 DNS SRV 記錄，以與主控 Exchange UM 整合
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
ms.openlocfilehash: ac215b5a0ba42ff031962e656e72fb355a808bf4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507470"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>建立 DNS SRV 記錄，以與主控 Exchange UM 整合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

本主題說明如何針對 Lync Server 2013 Edge Server 所需的 (DNS) SRV 記錄，設定網域名稱系統，以路由傳送至主控 Exchange 服務（如 Microsoft Exchange Online）。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>若要為主控的 Exchange 服務建立外部 DNS SRV 記錄

1.  以 DnsAdmins 群組成員的身分登入外部 DNS 伺服器。

2.  依序按一下 [開始]****、[系統管理工具]**** 及 [DNS]****。

3.  在 SIP 網域的主控台樹中，展開 [ **正向對應區域**]，然後選取將安裝 Lync Server 2013 的 SIP 網域。
    
    <div>
    

    > [!IMPORTANT]
    > 您必須在將安裝 Lync Server 的 SIP 網域中建立 DNS SRV 記錄。 當您建立 SRV 記錄時，用於提供此服務欄位之主機的 FQDN 必須是 Edge 集區的外部 FQDN。 例如，如果您 Edge 集區的外部 FQDN 是 edge01.contoso.net，請輸入該值。 這也必須與 DNS 主機位於相同的網域中 () 記錄。

    
    </div>

4.  以滑鼠右鍵按一下選取的網域，然後按一下 [ **其他新記錄**]。

5.  在 [ **資源記錄類型**] 中，按一下 [ **服務位置] (SRV) **]，然後按一下 [ **建立記錄**]。

6.  在 [**新增資源記錄**] 中，按一下 [**服務**]，然後輸入** \_ sipfederationtls**。

7.  按一下 [**通訊協定**]，然後輸入** \_ tcp**。

8.  按一下 [ **埠號碼**]，然後輸入 **5061**。

9.  按一下 [ **提供這項服務的主機**]，然後輸入 lync Server 2013 Edge 集區的完整功能變數名稱 (FQDN) ，為受信任的外部用戶端提供 lync server 2013 系統的存取權。
    
    <div>
    

    > [!NOTE]
    > 網域也必須設定為 Exchange Online 設定中的「授權」、「公認的網域」。 如需詳細資訊，請參閱建立公認的網域 at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> 。

    
    </div>

10. 按一下 **[確定]**，然後按一下 [ **完成**]。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>確認已成功建立 DNS SRV 記錄

1.  登入網域中的用戶端電腦。

2.  按一下 **[開始]**，再按一下 **[執行]**。

3.  在命令提示字元中，執行下列命令：
    
        nslookup <FQDN Lync Edge Pool>

4.  請確認您收到的回復可解析為 FQDN 的適當 IP 位址。

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

