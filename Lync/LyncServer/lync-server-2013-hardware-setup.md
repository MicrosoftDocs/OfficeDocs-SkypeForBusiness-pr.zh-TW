---
title: Lync Server 2013： 硬體設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02161765e6d3bd9c56eaddcb7f79b9d41dac3b16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 的硬體設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

設定硬體和其他所需的基礎結構，您必須實作您的拓撲中的元件需要，在拓撲產生器中發行拓撲之前, 您執行下列動作：

  - 在您建立及使用拓撲產生器，包括所有必要的電腦儲存拓撲設計中安裝每個元件的硬體 (執行 Lync Server 2013、 資料庫伺服器、 執行網際網路資訊服務 (IIS) 伺服器的伺服器和反向 proxy 伺服器，視）、 網路介面卡，硬體負載平衡器，以及儲存裝置 （例如檔案伺服器）。 確認已遵照網路介面卡之數量及速度的建議。 如果您使用硬體負載平衡器，請確定您已從廠商連絡，以將其設定與 Lync Server 2013 搭配使用的適當資訊。 您將使用 「 檔案伺服器或另一部伺服器來家檔案共用所需的 Lync Server，請確定伺服器可以使用並準備好進行檔案共用的組態。 如需如何定義拓撲，指定您的部署所需的元件的詳細資訊，請參閱[定義和設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。 如需伺服器硬體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 支援硬體](lync-server-2013-supported-hardware.md)。

  - 請確定網路基礎結構符合需求。 如需詳細資訊，請參閱規劃文件中的[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。

  - 設定 Active Directory 網域服務。 設定 AD DS 的動作包括準備 AD DS 和定義所有您想在 AD DS 中部署的元件。 如需準備 AD DS 的詳細資訊，請參閱部署文件中的[準備 Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) 。

  - 設定建立檔案共用所需的權限。 發行拓撲時，使用的 Lync Server 2013 的檔案共用的權限會自動會由拓撲產生器設定。 不過，用來發行拓撲的使用者帳戶必須具有完全控制權 （讀取/寫入/修改） 在檔案共用為了讓拓撲產生器來設定必要的權限。 若要確定檔案共用可以妥善管理在拓撲產生器的發佈程序期間，使用者為成員的網域群組應進行本機 Administrators 群組的成員的檔案共用所在電腦上。 在多網域的情況下，則網域 A 的使用者或群組在檔案共用所在網域 B 電腦上必須是本機 Administrators 群組的成員。
    
    如需更新的詳細資訊使用檔案共用中分散式檔案系統 (DFS)，請參閱[Lync Server 2013 的設定檔儲存](lync-server-2013-configure-dfs-file-storage.md)。
    
    <div>
    

    > [!WARNING]  
    > 前端伺服器上找不到 Lync Server 2013，企業版的檔案共用。

    
    </div>

  - 安裝及設定 Web 服務的硬體負載平衡器。 部署網域名稱系統 (DNS) 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限 HTTP/HTTPS 流量。 硬體負載平衡器用於連接埠 443 和 80 上來自用戶端的 HTTPS 流量。 雖然這些集區仍然需要硬體負載平衡器，但其設定和管理主要是針對 HTTP/HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。

完成本主題所述的所有準備工作後，在發行拓撲前，您還需要：

  - [Lync Server 2013 伺服器上安裝作業系統和必要軟體](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [將 Lync Server 2013 的 IIS 設定](lync-server-2013-configure-iis.md)

  - [針對 Lync Server 2013 設定 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [設定 Lync Server 2013 中的前端集區或 Standard Edition server 的 DNS 記錄](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

