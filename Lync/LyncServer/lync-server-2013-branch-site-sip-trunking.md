---
title: Lync Server 2013：分支網站 SIP 中繼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 955e920138021941db0e75832d56d06499738edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的分支網站 SIP 中繼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

在某些情況下，您可能需要在選取的分支網站上執行分散式 SIP 中繼。 若要判斷分支網站是否需要 SIP 幹線，請參閱[如何在 Lync Server 2013 中實現 sip 中繼？](lync-server-2013-how-do-i-implement-sip-trunking.md)。

如需在分支網站中部署 SIP trunks 之支援拓撲選項的詳細資料，請參閱[Lync Server 2013 中的分支網站復原解決方案](lync-server-2013-branch-site-resiliency-solutions.md)。

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>分支網站 SIP 中繼需求分析範例

當您決定要部署分支網站 SIP 幹線時，您必須執行特定網站的成本分析。 例如，在雷蒙德、華盛頓及紐約的分支網站中有中央網站的企業，都應該進行分析，判斷是否要將 SIP 主幹從紐約網站實施到本機服務提供者。

若要判斷位於紐約的分散式 SIP 主幹是否經濟高效，請找出哪個直接撥入式撥號（已有）號碼將使用 SIP 幹線，並分析紐約的呼叫次數，而不是雷德蒙者（425）。 您可以在中央網站上終止分支網站。 例如，雷德蒙的中央網站可以主持紐約分支網站的編號。 如果實施分散式 SIP 幹線的成本低於這些通話的成本，請考慮在紐約分支網站實施 SIP 主幹。

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支網站 SIP 幹線需求

在部署 SIP 幹線（而不是閘道）之間選擇，就會根據每個選項的公用交換電話網絡（PSTN）長途電話費用之間的差異而定。 如果您部署分支網站 SIP 幹線，您也必須判斷復原能力和頻寬需求。 如果您分支網站與中央網站之間的連結有彈性且頻寬充足，您可以部署 SIP 主幹或閘道。 您不需要在分支網站上部署 Survivable 分支裝置。 如果您分支網站與中央網站之間的連結沒有復原能力，請部署 Survivable 分支裝置，或使用分支網站上的閘道或 SIP 幹線來部署 Survivable 分支伺服器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

