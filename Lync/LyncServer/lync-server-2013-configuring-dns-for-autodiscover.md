---
title: Lync Server 2013： 設定 DNS 自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff6e72d13ddfb80369a0a522abc14a1de459536
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的自動探索設定 DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-12_

若要支援 Lync 用戶端自動探索，您需要建立下列網域名稱系統 (DNS) 記錄：

  - 內部 DNS 記錄，以支援 Lync 用戶端連線從貴組織的網路

  - 外部或公用 DNS 記錄，以支援 Lync 用戶端從網際網路連線

您必須為每個 SIP 網域建立內部 DNS 記錄及外部 DNS 記錄。

DNS 記錄可以是其中一個 A （主機） 記錄或 CNAME 記錄，根據您建立新的憑證與其他主體替代名稱 (SAN) 的能力。 如果您不可以要求並部署 lyncdiscover 與新的外部 （公用） 憑證。\<網域名稱\>SAN (英文），使用此程序使用 HTTP/TCP 連接埠 80。 下列程序說明如何建立內部及外部 DNS 記錄。

<div>

## <a name="to-create-dns-cname-records"></a>建立 DNS CNAME 記錄

1.  登入 DNS 伺服器，如下所示：
    
      - 若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。
    
      - 若要建立外部 DNS 記錄，請連線至公用 DNS 提供者。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  執行下列其中一項作業：
    
      - 針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]****。
        
        <div>
        

        > [!NOTE]  
        > 此網域是 Active Directory 網域，您的 Lync Server 2013&nbsp;安裝 Director 集區與前端集區。

        
        </div>
    
      - 針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。

4.  確認主機 A 記錄存在，您的 Director 集區，如下所示：
    
      - 針對內部 DNS 記錄，主機 A 記錄應該存在的內部 Web 服務完整的網域名稱 (FQDN) Director 集區 (例如 lyncwebdir01.contoso.local)。
    
      - 針對外部 DNS 記錄，您的 Director 集區 (例如 lyncwebextdir.contoso.com) 的外部 web 服務 FQDN 應有存在的主機 A 記錄。

5.  確認主機 A 記錄存在，您的前端集區，如下所示：
    
      - 針對內部 DNS 記錄，您的前端集區 (例如 lyncwebpool01.contoso.local) 的內部 Web 服務 fqdn 應有存在主機 A 記錄。
    
      - 針對外部 DNS 記錄，您的前端集區 (例如 lyncwebextpool01.contoso.com) 的外部 Web 服務 fqdn 應有存在主機 A 記錄。

6.  針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。
    
    <div>
    

    > [!NOTE]  
    > 如果您要建立外部 DNS 記錄，從步驟 3 就已展開 SIP 網域的 [正向對應區域]<STRONG></STRONG>。

    
    </div>

7.  用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增別名 (CNAME)]****。

8.  在 [別名]**** 中，輸入下列其中一項：
    
      - 針對內部 DNS 記錄，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。
    
      - 針對外部 DNS 記錄，輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱。

9.  在 [目標主機完整網域名稱 (FQDN)]**** 中，執行下列其中一項：
    
      - 針對內部 DNS 記錄，輸入或瀏覽至您的 Director 集區 (例如 lyncwebdir01.contoso.local)，內部 Web 服務 FQDN，然後按一下 **[確定]**。
    
      - 針對外部 DNS 記錄，輸入或瀏覽至您的 Director 集區 (例如 lyncwebextdir.contoso.com)，外部 Web 服務 FQDN，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您不使用 Director，使用內部和外部 Web 服務 FQDN 的前端集區或單一伺服器的前端伺服器或 Standard Edition server 的 FQDN。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須在您支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>建立 DNS A 記錄

1.  登入 DNS 伺服器，如下所示：
    
      - 若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。
    
      - 若要建立外部 DNS 記錄，連線至您的公用 DNS 提供者或外部 DNS 伺服器。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  執行下列其中一項作業：
    
      - 針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]****。
        
        <div>
        

        > [!NOTE]  
        > 此網域是 Active Directory 網域，您的 Lync Server 2013&nbsp;安裝 Director 集區與前端集區。

        
        </div>
    
      - 針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。

4.  確認主機 A （對於 IPv6 為 AAAA) 記錄存在，您的 Director 集區，如下所示：
    
      - 針對內部 DNS 記錄，您的 Director 集區 (例如 lyncwebdir01.contoso.local) 的內部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。
    
      - 針對外部 DNS 記錄，您的 Director 集區 (例如 lyncwebextdir.contoso.com) 的外部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。

5.  確認主機 A （對於 IPv6 為 AAAA) 記錄存在，您的前端集區，如下所示：
    
      - 針對內部 DNS 記錄，您的前端集區 (例如 lyncwebpool01.contoso.local) 的內部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。
    
      - 針對外部 DNS 記錄，您的前端集區 (例如 lyncwebextpool01.contoso.com) 的外部 Web 服務 fqdn 應有存在主機 A （對於 IPv6 為 AAAA) 記錄。

6.  針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。
    
    <div>
    

    > [!NOTE]  
    > 如果您要建立外部 DNS 記錄，從步驟 3 就已展開 SIP 網域的 [正向對應區域]<STRONG></STRONG>。

    
    </div>

7.  用滑鼠右鍵按一下 SIP 網域名稱，然後按一下 [新增主機 (A 或 AAAA)]****。

8.  在 [名稱]**** 中輸入主機名稱，如下所示：
    
      - 針對內部 DNS 記錄，輸入 lyncdiscoverinternal 作為內部自動探索服務 URL 的主機名稱。
    
      - 針對外部 DNS 記錄，輸入 lyncdiscover 作為外部自動探索服務 URL 的主機名稱。
    
    <div>
    

    > [!NOTE]  
    > 網域名稱是從定義記錄所在的區域取得，因此，不需要當作 A 記錄的一部分來輸入。

    
    </div>

9.  在 [IP 位址]**** 中輸入 IP 位址，如下所示：
    
      - 針對內部 DNS 記錄，輸入 Director 的內部 Web 服務 IP 位址 （或者，如果您使用負載平衡器，請輸入虛擬 IP (VIP) Director 負載平衡器）。
        
        <div>
        

        > [!NOTE]  
        > 如果您不使用 Director、 輸入 IP 位址的前端伺服器或 Standard Edition server，或，如果您使用負載平衡器中，輸入前端集區負載平衡器的 VIP。

        
        </div>
    
      - 針對外部 DNS 記錄，輸入反向 Proxy 的外部或公用 IP 位址。

10. 按一下 [新增主機]****，然後按一下 [確定]****。

11. 如果要建立其他 A 記錄，請重複步驟 8 到 10。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須在您支援 Lync Server 2013 環境中的每個 SIP 網域的正向對應區域中建立新的 lyncdiscover 和 lyncdiscoverinternal A 記錄。

    
    </div>

12. 完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

