---
title: Lync Server 2013：硬體設定
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013 的硬體設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在您要實現拓朴所需的基礎結構中設定硬體及其他元件，需要在拓撲建立器中發佈拓撲之前，執行下列動作：

  - 針對您使用拓撲建立器建立並儲存的拓撲設計中的每個元件安裝硬體，包括所有所需的電腦（執行 Lync Server 2013、資料庫伺服器、執行網際網路資訊服務的伺服器（IIS），以及視需要反向 proxy 伺服器、網路介面卡、硬體負載平衡器和儲存裝置（例如檔案伺服器）。 確認您已遵循網路介面卡編號與速度的建議。 如果您要使用硬體負載平衡器，請確認您有供應商提供的適當資訊，以便將其設定為搭配 Lync Server 2013 使用。 如果您要使用檔案伺服器或其他伺服器來存放 Lync Server 所需的檔案共用，請確認伺服器可供使用，且已準備好配置檔案共用。 如需如何定義拓朴以指定您的部署所需元件的詳細資料，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。 如需伺服器硬體需求的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的硬體](lync-server-2013-supported-hardware.md)。

  - 請確定網路基礎結構符合需求。 如需詳細資訊，請參閱規劃檔中[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。

  - 設定 Active Directory 網域服務。 設定 AD DS 包括準備 AD DS，並定義您想要部署在 AD DS 中的所有元件。 如需有關準備 AD DS 的詳細資料，請參閱在部署檔中[為 Lync Server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 設定建立檔案共用所需的許可權。 Lync Server 2013 使用檔案共用的許可權會在您發佈拓撲時自動由拓撲產生器進行設定。 不過，用於發佈拓朴的使用者帳戶必須在檔案共用上擁有 [完全控制] （讀取/寫入/修改），才能讓拓撲建立程式設定必要的許可權。 若要確保在拓撲建立器發佈程式中能正確地管理檔案共用，使用者所屬的使用者或網域群組應該成為檔案共用所在電腦上的本機管理員群組成員。 在多網域案例中，您應該在網域 B 的電腦上，將網域 A 的使用者或群組設為本機管理員群組的成員。
    
    如需使用分散式檔案系統（DFS）中的檔案共用進行更新的詳細資訊，請參閱[設定 Lync Server 2013 的檔案儲存空間](lync-server-2013-configure-dfs-file-storage.md)。
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013、Enterprise Edition 的檔案共用無法位於前端伺服器上。

    
    </div>

  - 安裝並設定適用于 Web 服務的硬體負載平衡器。 隨著已部署的網域名稱系統（DNS）負載平衡，您仍然需要同時針對這些池使用硬體負載平衡器，但僅適用于 HTTP/HTTPS 流量。 硬體負載平衡器用於來自埠443和80的用戶端的 HTTPS 流量。 雖然您仍需要這些池的硬體負載平衡器，但它們的設定和管理主要是針對 HTTP/HTTPS 流量（硬體負載平衡器的系統管理員習慣）。

完成本主題所述的所有準備工作之後，但在發佈拓撲之前，您也需要：

  - [在伺服器上安裝 Lync Server 2013 的作業系統和必要軟體](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [針對 Lync Server 2013 設定 IIS](lync-server-2013-configure-iis.md)

  - [為 Lync Server 2013 設定 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 中設定前端集區或 Standard Edition Server 的 DNS 記錄](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

