---
title: Lync Server 2013：SIP 主幹部署檢查表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的 SIP 主幹部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

您和您的服務提供者必須交換一些有關各 SIP 幹線端點的基本連線資訊，才能部署 SIP 主幹。

針對您要連接的每個 ITSP 閘道，取得下列資訊：

  - IP 位址

  - 完全合格的功能變數名稱（FQDN）

<div>


> [!NOTE]  
> 服務提供者可能會要求您連線到一個以上的 ITSP 閘道。 在這種情況下，您必須在每個 ITSP 閘道與池中的每個轉送伺服器之間設定連線。



</div>

您提供給服務提供者的資訊視 SIP 中繼連線類型而定：

  - 針對多協定標籤切換（MPLS）或私人網路連線，請為 ITSP 提供周邊網路中路由器的公用路由 IP 位址（也稱為 DMZ、網路隔離區域和遮罩子網）。 確認 ITSP 上的閘道或會話邊界控制器（SBC）可以達到這個位址。 也提供 ITSP 轉送伺服器的 FQDN。

  - 針對虛擬私人網路（VPN）連線，請提供 ITSP VPN 伺服器的 IP 位址。

<div>

## <a name="certificate-considerations"></a>憑證考慮

若要判斷您是否需要 SIP 中繼的憑證，請諮詢您的 ITSP 關於通訊協定的支援：

1.  如果您的 ITSP 只支援傳輸控制通訊協定（TCP），則不需要證書。

2.  如果您的 ITSP 支援傳輸層安全性（TLS），則 ITSP 必須提供您的憑證。

<div>


> [!NOTE]  
> SIP 可與即時傳輸通訊協定（RTP）或安全即時傳輸通訊協定（SRTP）搭配使用，以透過網際網路通訊協定（VoIP）通話管理實際語音資料的通訊協定。



</div>

</div>

<div>

## <a name="deployment-process"></a>部署程式

若要實現 SIP 中繼連線的 Lync Server 端，請遵循下列步驟：

1.  使用 Lync Server 拓撲建立器建立及設定 SIP 網域拓撲。 如需詳細資訊，請參閱在部署檔中，在[Lync Server 2013 的拓撲建立程式中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

2.  使用 Lync Server [控制台] 設定新 SIP 網域的語音路由。 如需詳細資訊，請參閱部署檔中的[Lync Server 2013](lync-server-2013-configuring-trunks.md)中的 [設定 trunks]。

3.  使用**Test CsPstnOutboundCall** Cmdlet 來測試連線性。 如需詳細資訊，請參閱 lync server 管理命令介面檔或 Lync Server 管理命令介面的說明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

