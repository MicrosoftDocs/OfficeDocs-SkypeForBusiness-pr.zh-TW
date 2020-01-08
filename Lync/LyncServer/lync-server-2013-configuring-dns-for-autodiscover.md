---
title: Lync Server 2013：針對自動探索設定 DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中針對自動探索設定 DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-12_

若要支援 Lync 用戶端的自動探索，您需要建立下列網域名稱系統（DNS）記錄：

  - 支援從貴組織網路內部連線的 Lync 用戶端的內部 DNS 記錄

  - 支援連線至網際網路的 Lync 用戶端的外部或公用 DNS 記錄

您必須為每個 SIP 網域建立內部 DNS 記錄和外部 DNS 記錄。

DNS 記錄可以是 [（主機）記錄] 或 [CNAME 記錄]，這是根據您使用其他消費者替換名稱（SAN）建立新憑證的能力而定。 如果您無法使用 lyncdiscover 來要求並部署新的外部（公開）憑證。\<網功能變數名稱稱\> SAN 中，請使用 HTTP/TCP 埠80的程式。 下列程式描述如何建立內部和外部 DNS 記錄。

<div>

## <a name="to-create-dns-cname-records"></a>建立 DNS CNAME 記錄

1.  登入 DNS 伺服器，如下所示：
    
      - 若要建立內部 DNS 記錄，請以網域系統管理員群組或 DnsAdmins 群組成員的身分登入您網路中的 DNS 伺服器。
    
      - 若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者。

2.  開啟 [DNS 管理] 管理單元：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **dns**]。

3.  請執行下列其中一項操作：
    
      - 如果是內部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開 Active Directory 網域的 [**正向查閱區域**] （例如，[contoso. local]）。
        
        <div>
        

        > [!NOTE]  
        > 這個網域是您在其中安裝 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 網域。

        
        </div>
    
      - 針對外部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。

4.  驗證主機 A 記錄是否針對您的主管池而存在，如下所示：
    
      - 對於內部 DNS 記錄，對於內部 Web 服務，您的控制器池必須有一個主機 A 記錄（例如，lyncwebdir01）的主機 A 記錄。
    
      - 對於外部 DNS 記錄，您的控制器池的外部 web 服務 FQDN 應該有一個主機 A 記錄（例如，lyncwebextdir.contoso.com）。

5.  驗證主機 A 記錄是否存在於您的前臺池，如下所示：
    
      - 如果是內部 DNS 記錄，則主機 A 記錄應該存在於您的前端池（例如，lyncwebpool01）的內部 Web 服務 FQDN 中。
    
      - 如果是外部 DNS 記錄，則主機 A 記錄應該存在於您的前端池的外部 Web 服務 FQDN （例如，lyncwebextpool01.contoso.com）。

6.  如果是內部 DNS 記錄，請在您的 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。
    
    <div>
    

    > [!NOTE]  
    > 如果您要建立外部 DNS 記錄，您的 SIP 網域已在步驟3中展開 [<STRONG>轉寄查閱區域</STRONG>]。

    
    </div>

7.  以滑鼠右鍵按一下 SIP 網功能變數名稱稱，然後按一下 **[新增別名（CNAME）**]。

8.  在 [**別名名稱**] 中，輸入下列其中一項：
    
      - 針對內部 DNS 記錄，請輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。
    
      - 針對外部 DNS 記錄，請輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。

9.  在 [**目標主機的完整功能變數名稱（FQDN）**] 中，執行下列其中一項操作：
    
      - 針對內部 DNS 記錄，請輸入或流覽至您的主管池（例如，lyncwebdir01）的內部 Web 服務 FQDN，然後按一下 **[確定]**。
    
      - 針對外部 DNS 記錄，請輸入或流覽至主管池的外部 Web 服務 FQDN （例如，lyncwebextdir.contoso.com），然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 如果您不是使用 Director，請針對前端池使用內部和外部 Web 服務 FQDN，或針對單一伺服器（前端伺服器或標準版伺服器的 FQDN）。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須在 Lync Server 2013 環境支援的每個 SIP 網域的轉寄查閱區域中建立新的自動探索 CNAME 記錄。

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>建立 DNS 記錄

1.  登入 DNS 伺服器，如下所示：
    
      - 若要建立內部 DNS 記錄，請以網域系統管理員群組或 DnsAdmins 群組成員的身分登入您網路中的 DNS 伺服器。
    
      - 若要建立外部 DNS 記錄，請連接到您的公用 DNS 提供者或外部 DNS 伺服器。

2.  開啟 [DNS 管理] 管理單元：按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **dns**]。

3.  請執行下列其中一項操作：
    
      - 如果是內部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開 Active Directory 網域的 [**正向查閱區域**] （例如，[contoso. local]）。
        
        <div>
        

        > [!NOTE]  
        > 這個網域是您在其中安裝 Lync Server 2013&nbsp;控制器池和前端池的 Active Directory 網域。

        
        </div>
    
      - 針對外部 DNS 記錄，請在 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。

4.  確認主機 A （適用于 IPv6、AAAA）記錄對於您的主管池是否存在，如下所示：
    
      - 對於內部 DNS 記錄，您的控制器池（例如，lyncwebdir01）應該有主機 A （適用于 IPv6、AAAA）的記錄。
    
      - 針對外部 DNS 記錄，您的主管池（例如，lyncwebextdir.contoso.com）應該有一個主機 A （適用于 IPv6、AAAA）記錄。

5.  針對您的前臺池，確認主機 A （針對 IPv6、AAAA）記錄存在如下所示：
    
      - 對於內部 DNS 記錄，您的主機 A （適用于 IPv6、AAAA）記錄應該存在於您的前端池（例如，lyncwebpool01）內部 Web 服務 FQDN 中。
    
      - 對於外部 DNS 記錄，您的前端池（例如，lyncwebextpool01.contoso.com）應該有主機 A （適用于 IPv6、AAAA）記錄。

6.  如果是內部 DNS 記錄，請在您的 DNS 伺服器的主控台樹中，展開您 SIP 網域的**正向查閱區域**（例如，contoso.com）。
    
    <div>
    

    > [!NOTE]  
    > 如果您要建立外部 DNS 記錄，您的 SIP 網域已在步驟3中展開 [<STRONG>轉寄查閱區域</STRONG>]。

    
    </div>

7.  以滑鼠右鍵按一下 SIP 網功能變數名稱稱，然後按一下 **[新增主機（A 或 AAAA）**]。

8.  在 [**名稱**] 中，輸入主機名稱，如下所示：
    
      - 針對內部 DNS 記錄，請輸入 lyncdiscoverinternal 做為內部自動探索服務 URL 的主機名稱。
    
      - 針對外部 DNS 記錄，請輸入 lyncdiscover 做為外部自動探索服務 URL 的主機名稱。
    
    <div>
    

    > [!NOTE]  
    > 功能變數名稱是從定義該記錄的區域中假設，因此不需要在 A 記錄中輸入該功能變數名稱。

    
    </div>

9.  在 [ **Ip 位址**] 中，輸入 ip 位址，如下所示：
    
      - 如果是內部 DNS 記錄，請輸入主管的內部 Web 服務 IP 位址（或者，如果您使用負載平衡器，請輸入控制器負載平衡器的虛擬 IP （VIP））。
        
        <div>
        

        > [!NOTE]  
        > 如果您不使用 Director，請輸入前端伺服器或標準版伺服器的 IP 位址，或者，如果您使用負載平衡器，請輸入前端池負載平衡器的 VIP。

        
        </div>
    
      - 針對外部 DNS 記錄，請輸入反向 proxy 的外部或公用 IP 位址。

10. 按一下 [**新增主機**]，然後按一下 **[確定]**。

11. 若要建立額外的 A 記錄，請重複步驟8到10。
    
    <div>
    

    > [!IMPORTANT]  
    > 您必須在 Lync Server 2013 環境中所支援的每個 SIP 網域的轉寄式查閱區域中，建立新的 lyncdiscover，並 lyncdiscoverinternal 記錄。

    
    </div>

12. 完成建立（適用于 IPv6、AAAA）記錄之後，按一下 [**完成**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

