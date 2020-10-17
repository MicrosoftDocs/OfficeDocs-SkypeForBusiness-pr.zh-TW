---
title: Lync Server 2013：設定自動探索的 DNS
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
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520050"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中設定自動探索的 DNS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

若要支援 Lync 用戶端的自動探索，您必須建立下列網域名稱系統 (DNS) 記錄：

  - 內部 DNS 記錄，以支援從組織網路內部連線的 Lync 用戶端

  - 支援從網際網路連線之 Lync 用戶端的外部（或公用） DNS 記錄

您必須為每個 SIP 網域建立內部 DNS 記錄及外部 DNS 記錄。

DNS 記錄可以是 (主機) 記錄或 CNAME 記錄，其依據您使用其他主體別名 (SAN) 建立新憑證的能力。 如果您無法向 lyncdiscover 要求及部署新的外部 (公開) 憑證。\<domain name\> SAN，請使用 HTTP/TCP 埠80的程式。 下列程序說明如何建立內部及外部 DNS 記錄。

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
        > 此網域是安裝 Lync Server 2013 &nbsp; Director 集區和前端集區的 Active Directory 網域。

        
        </div>
    
      - 針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。

4.  請確認 Director 集區的主機 A 記錄存在，如下所示：
    
      - 針對內部 DNS 記錄，主機 A 記錄應該存在於 Director 集區的內部 Web 服務完整功能變數名稱 (FQDN)  (例如，lyncwebdir01.contoso.local) 。
    
      - 針對外部 DNS 記錄，Director 集區的外部 web 服務 FQDN 應該存在主機 A 記錄 (例如，lyncwebextdir.contoso.com) 。

5.  請確認您的前端集區的主機 A 記錄存在，如下所示：
    
      - 針對內部 DNS 記錄，您的前端集區的內部 Web 服務 FQDN 應該存在主機 A 記錄 (例如，lyncwebpool01.contoso.local local) 。
    
      - 針對外部 DNS 記錄，您的前端集區的外部 Web 服務 FQDN 應該會有主機 A 記錄 (例如，lyncwebextpool01.contoso.com) 。

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
    
      - 針對內部 DNS 記錄，輸入或流覽至 Director 集區的內部 Web 服務 FQDN (例如，lyncwebdir01.contoso.local local) ，然後按一下 **[確定]**。
    
      - 針對外部 DNS 記錄，輸入或流覽至 Director 集區的外部 Web 服務 FQDN (例如，lyncwebextdir.contoso.com) ，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您不使用 Director，請使用前端集區的內部及外部 Web 服務 FQDN，或針對單一伺服器（前端伺服器或 Standard Edition server 的 FQDN）。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>建立 DNS A 記錄

1.  登入 DNS 伺服器，如下所示：
    
      - 若要建立內部 DNS 記錄，請以 Domain Admins 群組成員身分或 DnsAdmins 群組成員身分，登入您網路中的 DNS 伺服器。
    
      - 若要建立外部 DNS 記錄，請連接至您的公用 DNS 提供者或外部 DNS 伺服器。

2.  開啟 DNS 系統管理嵌入式管理單元：依序按一下 [開始]****、[系統管理工具]**** 和 [DNS]****。

3.  執行下列其中一項作業：
    
      - 針對內部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 Active Directory 網域 (例如 contoso.local) 的 [正向對應區域]****。
        
        <div>
        

        > [!NOTE]  
        > 此網域是安裝 Lync Server 2013 &nbsp; Director 集區和前端集區的 Active Directory 網域。

        
        </div>
    
      - 針對外部 DNS 記錄，在 DNS 伺服器的主控台樹狀目錄中，展開 SIP 網域 (例如 contoso.com) 的 [正向對應區域]****。

4.  針對您的 Director 集區，確認主機 A IPv6 的 (存在 AAAA) 記錄，如下所示：
    
      - 針對內部 DNS 記錄，您的 Director 集區的內部 Web 服務 FQDN 應該會有一個主機 A (IPv6，AAAA) 記錄應該存在 (例如，lyncwebdir01.contoso.local) 。
    
      - 針對外部 DNS 記錄，您的 Director 集區的外部 Web 服務 FQDN 應該會有一個主機的 (IPv6，AAAA) 記錄應該存在 (例如，lyncwebextdir.contoso.com) 。

5.  請確認您的前端集區的主機 A (IPv6，AAAA) 記錄都存在，如下所示：
    
      - 針對內部 DNS 記錄，a 主機 A IPv6 的 (，AAAA) 記錄應該存在於前端集區的內部 Web 服務 FQDN (例如，lyncwebpool01.contoso.local) 。
    
      - 針對外部 DNS 記錄，a 主機 A IPv6 的 (，AAAA) 記錄應該存在於前端集區的外部 Web 服務 FQDN (例如，lyncwebextpool01.contoso.com) 。

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
    
      - 針對內部 DNS 記錄，輸入 Director (的內部 Web 服務 IP 位址，或者，如果使用負載平衡器，請輸入 Director 負載平衡器) 的虛擬 IP (VIP) 。
        
        <div>
        

        > [!NOTE]  
        > 如果您不使用 Director，請輸入前端伺服器或 Standard Edition Server 的 IP 位址，或者，如果使用負載平衡器，請輸入前端集區負載平衡器的 VIP。

        
        </div>
    
      - 針對外部 DNS 記錄，輸入反向 Proxy 的外部或公用 IP 位址。

10. 按一下 [新增主機]****，然後按一下 [確定]****。

11. 如果要建立其他 A 記錄，請重複步驟 8 到 10。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的正向對應區域中建立新的 lyncdiscover 和 lyncdiscoverinternal A 記錄。

    
    </div>

12. 完成建立 A (對於 IPv6 為 AAAA) 記錄時，按一下 [完成]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

