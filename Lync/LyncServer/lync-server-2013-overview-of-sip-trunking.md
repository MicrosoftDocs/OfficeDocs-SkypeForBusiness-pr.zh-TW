---
title: Lync Server 2013：SIP 主幹連線概觀
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
ms.openlocfilehash: 340c27b3e874ea3d9f55aac2b415bd1a440aab9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹連線概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

部署 SIP 中繼可能是簡化貴組織的電訊，並準備最新的即時通訊功能的重要步驟。 SIP 中繼的主要優點之一是，您可以將貴組織的連線到中央網站的公用交換電話網絡（PSTN），而不是其前置任務、時間單位複用（TDM）中繼（通常是需要來自每個分支網站的個別幹線。

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server 中的 SIP 中繼

Lync Server 2013 SIP 中繼功能可讓您執行下列動作：

  - 企業使用者（無論是在公司防火牆內部或外部），都可以撥打由 E. 在 PSTN 上終止的以164為規範之服務提供者的服務所指定的本機通話或長途通話。

  - 任何 PSTN 訂閱者都可以撥打與該企業使用者相關聯的直接向內撥號（已連線）號碼，與公司防火牆內部或外部的企業使用者取得聯繫。

</div>

<div>

## <a name="cost-savings"></a>成本節約

與 SIP 中繼相關的成本節約可能相當重要：

  - 遠距離通話通常會透過 SIP 幹線降低成本。

  - 您可以削減易管理性成本，並減少部署的複雜性。

  - 如果您將 SIP 主幹直接連線至 ITSP，成本較低，就可以消除基本比率介面（BRI）和主要比率介面（PRI）費用。 在 TDM 中繼中，服務提供者會以分鐘為通話付費。 SIP 中繼的成本可能是以頻寬使用量為基礎，您可以使用較小的增量來購買。 （實際成本取決於您所選擇之 ITSP 的服務模型。）

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 中繼與託管 PSTN 閘道或 IP PBX

因為 SIP trunks 直接連線至您的服務提供者，所以您可以消除 PSTN 閘道及其管理成本與複雜性。 使用 SIP 幹線，只需要減少維護與管理，即可帶來巨大的成本節約。

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>擴充的 VoIP 服務

語音功能通常是部署 SIP 中繼的主要動機，但語音支援只是第一個步驟。 使用 SIP 中繼，您可以延伸 VoIP 功能並啟用 Lync Server 2013，以提供一組更豐富的服務。 例如：

  - 針對未執行 Lync Server 2013 的裝置，增強的目前狀態偵測功能可提供與行動電話的更佳整合，讓您可以查看使用者何時在行動電話上通話。

  - E9-1-1 緊急通話可讓您接聽911通話的主管機構，判斷來電者與其電話號碼的位置。

<div>


> [!NOTE]  
> 請與您的 ITSP 取得他們支援並可供您組織使用的服務清單。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

