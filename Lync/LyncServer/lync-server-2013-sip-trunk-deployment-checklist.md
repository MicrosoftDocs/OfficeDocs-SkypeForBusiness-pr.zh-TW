---
title: 'Lync Server 2013: SIP 主幹部署檢查表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08beaff401b8f261d311ad0d05a07f5221131864
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的 SIP 主幹部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

您可以部署 SIP 主幹之前，您和您的服務提供者必須各自的 SIP 主幹端點相關交換了某些基本連線資訊。

取得每個要連接的 ITSP 閘道的下列資訊：

  - IP 位址

  - 網域全名 (FQDN)

<div>


> [!NOTE]  
> 服務提供者可能會要求您連接到一個以上的 ITSP 閘道。 在此情況下，您必須在集區設定的每個 ITSP 閘道與每個中繼伺服器之間的連線。



</div>

您提供給服務供應商的資訊取決於您的 SIP 主幹連線類型：

  - 對於多重通訊協定標籤切換 (MPLS) 或私人網路連線，授與 ITSP 可公開路由的 IP 位址的路由器在周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路）。 確認閘道或工作階段界限控制器 (SBC) 在 ITSP 可以連線到這個地址。 也可讓 ITSP 中繼伺服器的 FQDN。

  - 對於虛擬私人網路 (VPN) 連線，可讓 ITSP VPN 伺服器的 IP 位址。

<div>

## <a name="certificate-considerations"></a>憑證考量

若要判斷您是否需要憑證，SIP 主幹，請洽詢 ITSP 有關通訊協定支援：

1.  如果 ITSP 僅支援傳輸控制通訊協定 (TCP)，您不需要憑證。

2.  如果 ITSP 支援傳輸層安全性 (TLS)，則 ITSP 必須提供您的憑證。

<div>


> [!NOTE]  
> SIP 適用於搭配即時傳輸通訊協定 (RTP) 或安全即時傳輸通訊協定 (SRTP)，管理中 Voice over Internet Protocol (VoIP) 通話的實際語音資料的通訊協定。



</div>

</div>

<div>

## <a name="deployment-process"></a>部署程序

若要實作 SIP 主幹連線的 Lync 伺服器端，請遵循下列步驟：

1.  使用 Lync Server 拓撲產生器]，建立及設定的 SIP 網域拓撲。 如需詳細資訊，請參閱[定義和設定拓撲在拓撲產生器中的 Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)部署文件中。

2.  使用 Lync Server Control Panel，設定新的 SIP 網域的語音路由。 如需詳細資訊，請參閱部署文件中的[Lync Server 2013 中的 Configuring trunks](lync-server-2013-configuring-trunks.md) 。

3.  使用**Test-cspstnoutboundcall**指令程式，以測試連線。 如需詳細資訊，請參閱 Lync Server 管理命令介面文件或適用於 Lync Server 管理命令介面的協助。

</div>

</div>

<span> </span>

</div>

</div>

</div>

