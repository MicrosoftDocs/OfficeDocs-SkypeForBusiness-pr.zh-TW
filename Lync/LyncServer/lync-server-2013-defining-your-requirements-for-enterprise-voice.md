---
title: Lync Server 2013：定義您的 Enterprise Voice 需求
description: Lync Server 2013：定義您的 Enterprise Voice 需求。
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
ms.openlocfilehash: 77547262816f0ad29ae905ff22974d8f48c21b95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545389"
---
# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中定義您的 Enterprise Voice 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

本主題概述您需要對拓撲中的網站與連結之間的考慮，以及當您部署企業語音時，這些網站的重要性。 如需協助您進行這些決策的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的「高級 Enterprise Voice 功能」網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) 。

<div>

## <a name="sites-and-regions"></a>網站和地區

首先，識別您的拓撲中的網站，您將在其中部署企業語音和這些網站所屬的網路地區。 明確而言，請考量您要如何為各個網站提供公用交換電話網路 (PSTN) 連線。 就管理性與物流的考量而言，這些網站的所屬地區可能會是決定性因素。 決定要在本機部署閘道的位置，Survivable 分支裝置 (Sba) 部署所在的位置，以及您可以在本機或在中央網站) 設定 SIP 主幹 ( (ITSP) 。

</div>

<div>

## <a name="network-links-between-sites"></a>網站間的網路連結

您也需要考慮您期望在中央網站與其分支網站之間之網路連結的頻寬使用量。 如果您有或想要在網站之間部署彈性的 WAN 連結，建議您在每個分支網站上部署閘道，以提供本機直接向內撥號 (已) 使用者在這些網站上終止。 如果您有彈性的 WAN 連結，但 WAN 連結的頻寬可能受限，請為該連結設定通話許可控制。 如果您沒有可恢復的 WAN 連結，請在分支網站上裝載低於1000的使用者，而且沒有本機訓練有素的 Lync Server 系統管理員，我們建議您在分支網站上部署 Survivable 分支裝置。 如果您在分支網站上主持1000和5000使用者、缺乏彈性的 WAN 連線，且有訓練有素的 Lync Server 系統管理員，我們建議您在分支網站上部署 Survivable 分支伺服器搭配小型閘道。 如果您有支援媒體旁路的閘道對等，也請考慮對受限的連結啟用媒體旁路。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的高級 Enterprise Voice 功能的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

