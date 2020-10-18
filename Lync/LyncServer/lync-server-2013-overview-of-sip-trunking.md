---
title: Lync Server 2013： SIP trunk 的簡介
description: Lync Server 2013： SIP 主幹的簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6132cc16d8aaeee4b27355ea8676672a0a5df93d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577259"
---
# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

部署 SIP 主幹可以大幅簡化組織的電信通訊，並可利用最新的即時通訊增強功能。SIP 主幹最重要的優點之一，是可將組織連線合併至中央網站的公用交換電話網路 (PSTN)，而其前身分時多工 (TDM) 主幹卻通常需要每個分支網站各一個主幹。

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server 中的 SIP 主幹

Lync Server 2013 SIP 主幹功能可讓下列專案：

  - 公司防火牆內外的企業使用者皆可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。

  - 任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。

</div>

<div>

## <a name="cost-savings"></a>節省成本

與 SIP 主幹相關聯的成本節約可能相當大：

  - 長途通話通常會透過 SIP 主幹降低成本。

  - 您可以削減管理成本，並降低部署的複雜度。

  - 基本速率介面 (BRI) 和主要速率介面 (PRI) 費用，可在您將 SIP 主幹直接連接至您的 ITSP 時，降低成本。 在 TDM trunk 中，服務提供者會在一分鐘內收取通話的費用。 SIP 主幹的成本可能是根據頻寬使用量而定，您可以更小、更經濟的增量購買。  (實際成本取決於您所選擇之 ITSP 的服務模型。 ) 

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>與裝載 PSTN 閘道或 IP-PBX 的 SIP Trunk

由於 SIP 主幹直接連線至您的服務提供者，所以您可以省去您的 PSTN 閘道及其管理成本和複雜性。 使用 SIP 主幹可縮短維護和管理，從而導致大量成本節約。

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>擴充的 VoIP 服務

語音功能常常是部署 SIP 主幹的主要動機，但語音支援只是第一步。 透過 SIP trunk，您可以擴充 VoIP 功能，並讓 Lync Server 2013 提供一組更豐富的服務。 例如：

  - 未執行 Lync Server 2013 之裝置的增強顯示狀態偵測，可提供與行動電話的更好整合，讓您能看到使用者何時接聽行動電話。

  - E9-1-1 緊急電話可讓接聽911呼叫的授權者判斷來電者的電話號碼的位置。

<div>


> [!NOTE]  
> 請與您的 ITSP 取得支援的服務清單，並可為您的組織啟用這些服務。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

