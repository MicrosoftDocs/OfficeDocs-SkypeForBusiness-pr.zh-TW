---
title: Lync Server 2013：硬體安裝程式
description: Lync Server 2013：硬體設定。
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
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552909"
---
# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 的硬體設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

若要在需要執行拓撲的基礎結構中設定硬體和其他元件，需要在在拓撲產生器中發佈拓撲之前，執行下列動作：

  - 使用拓撲產生器來安裝拓撲設計中每個元件的硬體，包括所有必要的電腦 (執行 Lync Server 2013 的伺服器、資料庫伺服器、執行網際網路資訊服務的伺服器 (IIS) 和反向 proxy 伺服器，如檔案伺服器 (等) 、網路介面卡、硬體負載平衡器和儲存裝置) 等。 確認已遵照網路介面卡之數量及速度的建議。 若要使用硬體負載平衡器，請確定您有適當的資訊可供廠商設定，以用於 Lync Server 2013。 如果您要使用檔案伺服器或其他伺服器來存放 Lync Server 所需的檔案共用，請確定伺服器已可使用，且已準備好進行檔案共用的設定。 如需如何定義拓撲以指定部署所需的元件的詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。 如需有關伺服器硬體需求的詳細資訊，請參閱支援檔中的 [支援的 Lync Server 2013 硬體](lync-server-2013-supported-hardware.md) 。

  - 請確定網路基礎結構符合需求。 如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md) 。

  - 設定 Active Directory 網域服務。 設定 AD DS 的動作包括準備 AD DS 和定義所有您想在 AD DS 中部署的元件。 如需有關準備 AD DS 的詳細資訊，請參閱部署檔中的 [準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md) 。

  - 設定建立檔案共用所需的權限。 當您發行拓撲時，拓撲產生器會自動設定使用 Lync Server 2013 的檔案共用的許可權。 不過，用來發佈拓撲的使用者帳戶必須具有檔案共用上的「完全控制」 (讀取/寫入/修改) ，才能讓拓撲產生器設定必要的許可權。 若要確定在拓撲產生器發佈程式時可以正確地管理檔案共用，使用者所屬的使用者或網域群組應該成為檔案共用所在機器上的本機管理員群組成員。 在多網域的情況下，則網域 A 的使用者或群組在檔案共用所在網域 B 電腦上必須是本機 Administrators 群組的成員。
    
    如需使用分散式檔案系統中的檔案共用進行更新的詳細資訊 (DFS) ，請參閱 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013，Enterprise Edition 的檔案共用不能位於前端伺服器上。

    
    </div>

  - 安裝和設定 Web 服務的硬體負載平衡器。 部署網域名稱系統 (DNS) 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限 HTTP/HTTPS 流量。 硬體負載平衡器用於連接埠 443 和 80 上來自用戶端的 HTTPS 流量。 雖然這些集區仍然需要硬體負載平衡器，但其設定和管理主要是針對 HTTP/HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。

完成本主題所述的所有準備工作後，在發行拓撲前，您還需要：

  - [在 Lync Server 2013 的伺服器上安裝作業系統和必要軟體](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [設定 Lync Server 2013 的 IIS](lync-server-2013-configure-iis.md)

  - [針對 Lync Server 2013 設定 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [設定前端集區或 Standard Edition Server 的 Lync Server 2013 中的 DNS 記錄](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

