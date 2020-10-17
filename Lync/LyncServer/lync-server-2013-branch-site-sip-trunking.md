---
title: Lync Server 2013：分支網站 SIP 主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1c9e4c5c8ca64e1b7f2014821cc61fa2655c9f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535190"
---
# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的分支網站 SIP 主幹

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

在某些情況下，您可能需要在選取的分支網站上執行分散式 SIP 主幹。 若要判斷分支網站是否需要 SIP 主幹，請參閱 [如何在 Lync Server 2013 中實施 sip](lync-server-2013-how-do-i-implement-sip-trunking.md)主幹的資訊？。

如需在分支網站中部署 SIP 主幹時支援的拓撲選項的詳細資訊，請參閱 [Lync Server 2013 中的分支網站恢復解決方案](lync-server-2013-branch-site-resiliency-solutions.md)。

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>分支網站 SIP 主幹需求分析範例

當您決定要部署分支網站 SIP 主幹時，您必須執行網站特定的成本分析。 例如，在華盛頓州的中央網站與位於紐約市的分支網站的企業，應進行分析，以判斷是否要從新的紐約網站執行 SIP 主幹給本機服務提供者。

若要判斷紐約的分散式 SIP 主幹是否成本效益，請找出使用 SIP 主幹的「直接向內撥」)  (，並分析紐約的呼叫數目，以撥打 Redmond (425) 以外的區域。 您可以在中央網站上終止分支網站。 例如，Redmond 中央網站可以主控紐約分支網站的數目。 若實施分散式 SIP 主幹的成本低於這些通話的成本，請考慮在紐約分支網站實施 SIP 主幹。

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支網站 SIP 主幹需求

部署 SIP 主幹（而非閘道）的選擇是以公用交換電話網路 (PSTN) 長途電話計費每個選項之間的差異為基礎。 如果您部署分支網站 SIP 主幹，您也需要判斷您的恢復能力和頻寬需求。 如果分支網站與中央網站之間的連結具備彈性，且具有足夠的頻寬，您可以部署 SIP 主幹或閘道。 您不需要在分支網站上部署 Survivable 分支裝置。 如果分支網站與中央網站之間的連結無法復原，請部署 Survivable 分支裝置，或使用分支網站上的閘道或 SIP 主幹來部署 Survivable 分支伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

