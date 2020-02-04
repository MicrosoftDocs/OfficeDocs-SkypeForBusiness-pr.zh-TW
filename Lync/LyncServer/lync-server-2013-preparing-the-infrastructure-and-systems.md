---
title: Lync Server 2013：準備基礎結構和系統
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>準備 Lync Server 2013 的基礎結構和系統

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

部署 Lync Server 2013 需要使用拓撲建立器來定義及發佈拓撲設計。 若要找出您的拓撲所需的元件，請使用 [拓撲建立器] 來建立並儲存拓撲設計。 在拓撲建立器中發佈拓撲前，請執行下列動作：

  - 在您使用拓撲建立器建立並儲存的拓撲設計中，針對每個元件取得並安裝硬體，包括所有所需的電腦（執行 Lync Server 2013 的伺服器、資料庫伺服器、運行 Internet 資訊服務的伺服器）（IIS）及反向 proxy 伺服器（視需要）、網路介面卡、硬體負載平衡器，以及儲存裝置（例如檔案伺服器）。 如需如何定義拓朴以指定您的部署所需元件的詳細資料，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。 如需伺服器硬體需求的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的硬體](lync-server-2013-supported-hardware.md)。

  - 請確定網路基礎結構符合需求。 如需詳細資訊，請參閱規劃檔中[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。

  - 設定 Active Directory 網域服務。 若要發佈並啟用拓撲，您必須在 AD DS 中，由電腦帳戶來代表內部伺服器。 這是透過將電腦加入到 AD DS 來完成。 如需有關準備 AD DS 的詳細資料，請參閱[準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 建立檔案共用。 標準版伺服器可託管所需檔案的檔案共用，而在企業版部署中，檔案共用不能裝載在前端伺服器上。 在資料夾和共用上部署及設定存取控制清單（ACL）所需的許可權和群組成員資格必須正確地設定為拓撲建立程式才能順利完成。 您應該確定執行拓撲建立器的人員具有下列許可權和群組成員資格：
    
      - 本機管理員的成員
    
      - 網域使用者的成員
    
      - 檔案存放區的 [共用] 和 [資料夾] 完全控制

  - 針對企業版，請安裝並設定 SQL Server。 若要讓 SQL Server 安裝程式成功，必須在線上，且發佈拓朴的人員是 SQL Server 上的本機系統管理員，而且必須是 SQL server 實例上 SQL Server 系統管理員群組的成員。

完成本主題所述的所有準備工作，但在發佈拓撲之前，您也需要執行其他準備工作，包括安裝 Windows 作業系統及其他必備軟體，以及設定[IIS]，然後設定 DNS。 如需這些工作的詳細資訊，請參閱執行[Lync server 2013 的伺服器系統需求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、[設定 lync SERVER 2013 的 IIS](lync-server-2013-configure-iis.md)，以及[準備 lync server 2013 的基礎結構和系統](lync-server-2013-preparing-the-infrastructure-and-systems.md)。 此外，您應該熟悉用戶端和用戶端需求。 如需詳細資訊，請參閱[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 的硬體設定](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 的軟體設定](lync-server-2013-software-setup.md)

  - [為 Lync Server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)

  - [為 Lync Server 2013 設定 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [在 Lync Server 2013 中設定前端集區或 Standard Edition Server 的 DNS 記錄](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

