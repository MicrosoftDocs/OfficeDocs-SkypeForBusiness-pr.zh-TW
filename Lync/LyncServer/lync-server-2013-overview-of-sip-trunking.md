---
title: SIP 主幹連線的 Lync Server 2013： 概觀
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
ms.openlocfilehash: e71a1f02fda14c2bcbb54aaec5e12307421090e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹連線概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

部署 SIP 主幹可以大幅簡化組織的電信通訊，並可利用最新的即時通訊增強功能。SIP 主幹最重要的優點之一，是可將組織連線合併至中央網站的公用交換電話網路 (PSTN)，而其前身分時多工 (TDM) 主幹卻通常需要每個分支網站各一個主幹。

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server 中的 SIP 主幹

Lync Server 2013 SIP 主幹功能可讓下列：

  - 公司防火牆內外的企業使用者皆可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。

  - 任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。

</div>

<div>

## <a name="cost-savings"></a>節省成本

SIP 主幹相關聯的成本節省可能相當可觀：

  - 撥打的長途電話通常更省錢透過 SIP 主幹。

  - 您可以管理成本，並降低部署複雜性。

  - 如果您的 SIP 主幹直接連線到在大幅降低成本 ITSP 可以消除基本速率介面 (BRI) 與主要 rate interface (PRI) 費用。 中 TDM 主幹服務提供者的呼叫依收費分鐘。 SIP 主幹的成本可能會根據您可以購買較小，更經濟增量的頻寬用量。 （實際成本取決於您選擇 ITSP 的服務模型）。

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>相對於 PSTN 閘道或 IP PBX 主控的 SIP 主幹

SIP 主幹直接連接到服務供應商，因為您可以省去您 PSTN 閘道、 其管理成本和複雜度。 使用 SIP 主幹可能會導致大量成本節省透過減少的維護和管理。

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>擴充的 VoIP 服務

語音功能通常會部署 SIP 主幹的主要動機但語音支援只是第一個步驟。 使用 SIP 主幹，您可以擴充 VoIP 功能，並啟用 Lync Server 2013 提供一組更豐富的服務。 例如：

  - 增強型目前狀態偵測未執行 Lync Server 2013 的裝置可以更密切整合與行動電話，讓您查看使用者在行動電話上時。

  - E9-1-1 緊急通話可讓人員接聽 911 通話至判斷他/她的電話號碼的來電者的位置。

<div>


> [!NOTE]  
> 請連絡 ITSP 並索取他們支援您的組織可以啟用的服務的清單。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

