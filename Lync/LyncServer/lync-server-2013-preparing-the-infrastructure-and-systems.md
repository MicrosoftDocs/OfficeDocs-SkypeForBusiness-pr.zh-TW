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
ms.openlocfilehash: bb33552fde0da6dc91f21eeecaf1ea5e85d72159
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>準備 Lync Server 2013 的基礎結構和系統

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

部署 Lync Server 2013 需要使用拓撲產生器來定義及發行拓撲設計。 若要識別拓撲所需的元件，您可以使用拓撲產生器來建立及儲存拓撲設計。 在拓撲產生器中發行拓撲之前，請執行下列作業：

  - 使用拓撲產生器，針對您建立及儲存的拓撲設計中的每個元件，取得並安裝硬體，包括所有必要的電腦 (執行 Lync Server 2013 的伺服器、資料庫伺服器、執行網際網路資訊服務的伺服器 (IIS) 和反向 proxy 伺服器，如檔案伺服器 (等) 、網路介面卡、硬體負載平衡器和儲存裝置) 等。 如需如何定義拓撲以指定部署所需的元件的詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。 如需有關伺服器硬體需求的詳細資訊，請參閱支援檔中的[支援的 Lync Server 2013 硬體](lync-server-2013-supported-hardware.md)。

  - 請確定網路基礎結構符合需求。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。

  - 設定 Active Directory 網域服務。 若要發行及啟用拓撲，您需要 AD DS 中的電腦帳戶來代表內部伺服器。 您可以將電腦加入 AD DS 來達到這個目的。 如需有關準備 AD DS 的詳細資訊，請參閱[準備 Active Directory 網域服務 For Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)。

  - 建立檔案共用。 Standard Edition Server 可以裝載必要檔案的檔案共用，而在 Enterprise 部署中，檔案共用不能裝載在前端伺服器上。 在資料夾和共用上部署及設定存取控制清單 (ACL) 時所需的權限和群組成員資格必須正確設定，拓撲產生器才能順利完成。 您應確定執行拓撲產生器的人員具備下列許可權和群組成員資格：
    
      - 本機系統管理員成員
    
      - 網域使用者成員
    
      - 共用和檔案存放區之資料夾的完全控制權限

  - 若為 Enterprise Edition，請安裝及設定 SQL Server。為了讓 SQL Server 安裝成功，SQL Server 型伺服器必須在線上，而發行拓撲的人員必須是 SQL Server 上的本機管理員，也必須是 SQL Server 執行個體上的 SQL Server 系統管理員群組成員。

完成本主題說明的所有準備工作後，您還需要在發行拓撲前執行其他準備工作，包括安裝 Windows 作業系統和其他必要的軟體、設定 IIS 及設定 DNS。 如需這些工作的詳細資訊，請參閱執行[Lync server 2013 之伺服器的系統需求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、為[lync SERVER 2013 設定 IIS](lync-server-2013-configure-iis.md)，以及[準備 lync server 2013 的基礎結構和系統](lync-server-2013-preparing-the-infrastructure-and-systems.md)。 此外，您應該要熟悉用戶端和用戶端需求。 如需詳細資訊，請參閱[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 的硬體設定](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 的軟體安裝](lync-server-2013-software-setup.md)

  - [為 Lync Server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)

  - [針對 Lync Server 2013 設定 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [設定前端集區或 Standard Edition Server 的 Lync Server 2013 中的 DNS 記錄](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

