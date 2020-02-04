---
title: Lync Server 2013：定義 Enterprise Voice 的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中定義 Enterprise Voice 的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

本主題概述您需要的考慮，包括您在拓撲中的區域、網站和連結，以及當您部署企業語音時這些專案的重要資訊。 如需協助您做出這些決定的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 [網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)]。

<div>

## <a name="sites-and-regions"></a>網站和區域

首先，請在您的拓撲中找出您要部署企業語音的網站，以及這些網站所屬的網路區域。 具體來說，請考慮您將如何提供公用的交換電話網絡（PSTN）連線至每個網站。 出於易管理性和後勤原因，這些網站所屬的區域可以是決定因素。 決定要在本機部署閘道的位置，將部署 Survivable 分支裝置（SBAs），以及您可以將 SIP trunks （本機或在中央網站）設定為網際網路電話服務提供者（ITSP）。

</div>

<div>

## <a name="network-links-between-sites"></a>網站之間的網路連結

您也需要考慮您在中央網站與其分支網站之間的網路連結上預期的頻寬使用量。 如果您有或想要在網站之間部署彈性 WAN 連結，建議您在每個分支網站部署一個閘道，以針對這些網站上的使用者提供本機直向內撥打電話（已結束）。 如果您有彈性 WAN 連結，但 WAN 連結上的頻寬可能受到限制，請設定該連結的 [呼叫許可控制]。 如果您沒有可復原的 WAN 連結，請在分支網站中主持少於1000個使用者，而且沒有當地訓練有素的 Lync Server 管理員可用，我們建議您在分支網站上部署 Survivable 分支裝置。 如果您是在分支網站上的1000和5000使用者之間主持、缺乏強健的 WAN 連線，且已提供訓練有素的 Lync Server 管理員，我們建議您在分支網站上部署 Survivable 分支伺服器與小型閘道。 如果您有支援媒體旁路的閘道對等，也可以考慮在受限制的連結上啟用媒體旁路。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 [高級企業語音功能] 的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

