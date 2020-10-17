---
title: Lync Server 2013： SIP 主幹部署檢查清單
description: Lync Server 2013： SIP 主幹部署檢查清單。
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
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559039"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的 SIP 主幹部署檢查表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

在您部署 SIP 主幹之前，您和服務提供者必須交換某些有關您各自 SIP 主幹端點的基本連線資訊。

針對您要連接的每個 ITSP 閘道取得下列資訊：

  - IP 位址

  - 網域全名 (FQDN)

<div>


> [!NOTE]  
> 服務提供者可能要求您連接至多個 ITSP 閘道。 在此情況下，您必須設定每個 ITSP 閘道與集區中的每個轉送伺服器之間的連線。



</div>

您提供給服務提供者的資訊取決於您的 SIP 主幹連線類型：

  - 若為多協定標籤切換 (MPLS) 或私人網路絡連線，請將您周邊 (網路中路由器的可公開路由的 IP 位址（也稱為 DMZ、網路隔離區域及遮罩式子網) ）提供給 ITSP。 確認 ITSP 中 (SBC) 的閘道或會話邊界控制器可以聯繫至此位址。 也為 ITSP 提供轉送伺服器的 FQDN。

  - 對於虛擬私人網路 (VPN) 連線，請將 VPN 伺服器的 IP 位址提供給 ITSP。

<div>

## <a name="certificate-considerations"></a>憑證考慮

若要判斷您是否需要憑證以進行 SIP 主幹，請與您的 ITSP 相關的通訊協定支援：

1.  如果您的 ITSP 只支援傳輸控制通訊協定 (TCP) ，您不需要憑證。

2.  如果您的 ITSP 支援傳輸層安全性 (TLS) ，則 ITSP 必須為您提供憑證。

<div>


> [!NOTE]  
> SIP 可搭配即時傳輸通訊協定 (RTP) 或安全即時傳輸通訊協定 (SRTP) ，用來管理 Voice over Internet Protocol 中實際語音資料的通訊協定 (VoIP) 通話。



</div>

</div>

<div>

## <a name="deployment-process"></a>部署程式

若要執行 SIP 主幹連線的 Lync Server 端，請遵循下列步驟：

1.  使用 Lync Server 拓撲產生器，建立及設定 SIP 網域拓撲。 如需詳細資訊，請參閱部署檔中的在 [2013 拓撲產生器中定義及設定拓撲](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 產生器中的拓撲。

2.  使用 Lync Server 控制台，設定新 SIP 網域的語音路由。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013](lync-server-2013-configuring-trunks.md) 中設定主幹。

3.  使用 **Test-CsPstnOutboundCall** Cmdlet 來測試連線性。 如需詳細資訊，請參閱 lync server 管理命令介面檔或 Lync Server 管理命令介面的說明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

