---
title: Lync Server 2013：如何執行 SIP 主幹？
description: Lync Server 2013：如何執行 SIP 中繼？。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10882adc0bff573868dcd07268ed0446385d895c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553149"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>如何在 Lync Server 2013 中實施 SIP 主幹？

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-18_

若要執行 SIP 主幹，您必須透過轉送伺服器路由傳送，該伺服器可充當 Lync Server 2013 用戶端與服務提供者和 transcodes 媒體（必要時）之間的通訊會話 proxy。

每個轉送伺服器都具有內部網路介面和外部網路介面。 內部介面連接至前端伺服器。 外部介面一般稱為閘道介面，因為傳統上它是用來將轉送伺服器連接到公用交換電話網路 (PSTN) 閘道或 IP-PBX。 若要執行 SIP 主幹，您可以將轉送伺服器的外部介面連接至 ITSP 的外部 edge 元件。

<div>


> [!NOTE]  
> ITSP 的外部 Edge 元件可以是工作階段界限控制器 (SBC)、路由器或閘道。



</div>

如需有關轉送伺服器的詳細資訊，請參閱 [Lync server 2013 中的轉送伺服器元件](lync-server-2013-mediation-server-component.md)。

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中式與分散式 SIP 主幹的比較

*集中式* SIP 主幹會將所有 Voice over Internet Protocol (VoIP) 流量，包括分支網站流量（透過您的中央網站）。 集中式部署模型是簡單、經濟划算的，通常是以 Lync Server 2013 實施 SIP 主幹的建議方法。

*分散式* SIP 主幹是一種部署模型，您可以在其中執行一或多個分支網站上的本機 SIP 主幹。 VoIP 流量會從分支網站直接路由傳送至服務提供者，而不需要透過中央網站。

只有下列情況才必須使用分散式 SIP 主幹：

  - 分支網站需要 survivable phone connectivity (例如，如果 WAN 停機) 。 應該針對每個分支網站來分析此需求;您的部分分支可能需要冗余和容錯移轉，但其他分支可能不需要。

  - 兩部中央網站之間需要恢復功能。 您必須確定 SIP 主幹會在每個中央網站終止。 例如，如果您有都柏林和 Tukwila 中央網站，且兩者都只使用一個網站的 SIP 主幹，如果主幹中斷，其他網站的使用者將無法進行 PSTN 通話。

  - 分支網站與中央網站位於不同的國家/地區。 基於相容性與法規考量，每個國家/地區至少要有一個 SIP 主幹。 以歐盟地區為例，若未在中心點上進行本機終止，通訊就只能侷限在國家/地區的範圍。

根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹路由傳送所有使用者，或者您可以選擇透過分支網站的 SIP 主幹路由傳送部分使用者。 若要分析自身需求，請回答下列問題：

  - 每個網站有多大 (，也就是有多少使用者已啟用企業語音) ？

  - 各網站上的哪些直接向內撥號 (DID) 號碼來電數最多？

在考量應部署集中式或分散式 SIP 主幹時，必須進行成本效益分析。 在某些情況下，即便並非必要，選擇分散式部署模型可能較有利。 在完整的集中式部署中，所有分支網站流量都透過 WAN 連結路由傳送。 與其為 WAN 連結所需的頻寬支付高額費用，您可能寧可使用分散式 SIP 主幹。 例如，您可能想要在具有同盟的中央網站的分支網站上部署 Standard Edition server，或使用小型閘道部署 Survivable Branch 裝置或 Survivable Branch Server。

<div>


> [!NOTE]  
> 如需有關分散式 SIP trunk 的詳細資訊，請參閱 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支網站 SIP</A>主幹。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支援的 SIP 主幹連線類型

Lync Server 支援 SIP 主幹的下列連線類型：

  - Multiprotocol Label Switching (MPLS) 是可將資料從一個網路節點導向及承載到另一個網路節點的私人網路。MPLS 網路的頻寬會與其他訂戶共用，並且會為每個資料封包指派一個標籤，用以區別不同訂戶的資料。此連線類型不需要虛擬私人網路 (VPN)。可能的缺點是，過多的 IP 流量可能會干擾 VoIP 作業，除非 VoIP 流量享有優先權。

  - 不含其他流量的私人連線 (例如租用的光纖連線或 T1 線路) 通常會是最可靠而安全的連線類型。此連線類型可提供最高的通話承載能力，但通常也最昂貴。此連線類型不需要 VPN。私人連線適用於通話量大或安全性與可用性需求很高的組織。

  - 網際網路是最經濟的連線類型，但可靠性也最低。 Internet connection 是唯一需要 VPN 的 Lync Server SIP 主幹連線類型。

<div>

## <a name="selecting-a-connection-type"></a>選取連線類型

您的企業最適合使用的 SIP 主幹連線類型，端視您的需求與預算而定。

  - 對中型或較大的企業而言，MPLS 網路通常能提供最大的效益。它可以低於特殊私人網路的費率提供所需的頻寬。

  - 大型企業可能需要私人光纖連線、T1、T3 或更高階的連線 (歐盟地區為 E1、E3 或更高階連線)。

  - 對於具有低通話數量的小型企業或分支網站，透過網際網路的 SIP 主幹可能是最佳選擇。 不建議中型或較大的網站使用此連線類型。

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>頻寬需求

您的實作所需的頻寬量，取決於您的話務量 (您必須能夠支援的並行通話數量)。您必須將頻寬可用性納入考量，以充分使用您花錢購買的最大容量。您可以使用下列公式計算 SIP 主幹的最大頻寬需求：

SIP 主幹最大頻寬 = 同時通話數上限 x (64 kbps + 標頭大小)

<div>


> [!NOTE]  
> 標頭大小上限為 20 個位元組。



</div>

</div>

<div>

## <a name="codec-support"></a>轉碼器支援

Lync Server 2013 僅支援下列編解碼器：

  - G.711 a-law (主要使用於北美以外的地區)

  - G.711 µ-law (使用於北美地區)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>網際網路電話語音服務提供者

SIP 主幹連線之服務提供者端的實作方式，會根據 ITSP 而不同。 如需部署資訊，請連絡服務提供者。 如需認證 SIP 主幹服務提供者的清單，請參閱 [Microsoft 整合通訊開啟互通性計畫網站](https://go.microsoft.com/fwlink/?linkid=287029)。

如需 Microsoft 認證 SIP 主幹提供者的詳細資訊，請連絡 Microsoft 代表。

<div>


> [!IMPORTANT]  
> 您必須使用 Microsoft 認證服務提供者，以確定 ITSP 支援所有周遊 SIP 主幹的功能 (例如，設定和管理工作階段，以及支援所有延伸的 VoIP 服務)。Microsoft 技術支援未延伸至使用非認證提供者的設定。如果您目前使用未獲得 SIP 主幹認證的網際網路服務提供者，則可以選擇繼續使用該提供者做為 ISP，並使用 Microsoft 認證的提供者進行 SIP 主幹作業。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

