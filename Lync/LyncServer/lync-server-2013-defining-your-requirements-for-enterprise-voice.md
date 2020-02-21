---
title: Lync Server 2013： 定義 Enterprise Voice 的需求
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
ms.openlocfilehash: 6bd6b93941404f60fe8b7ff936dc9a982fe59220
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>定義 Lync Server 2013 中的 Enterprise Voice 的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-08-07_

本主題概要說明您必須先需區域、 網站及您的拓撲中的網站和方式的重要部署 Enterprise Voice 時之間的連結的考量。 如需可協助您進行這些決策的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的進階 Enterprise Voice 功能的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)。

<div>

## <a name="sites-and-regions"></a>網站和地區

首先，找出您要部署 Enterprise Voice 和這些網站隸屬於網路地區的拓撲中的站台。 明確而言，請考量您要如何為各個網站提供公用交換電話網路 (PSTN) 連線。 就管理性與物流的考量而言，這些網站的所屬地區可能會是決定性因素。 決定其中閘道會部署在本機上，其中將部署 Survivable Branch Appliance (Sba)，其中您可以設定 SIP 主幹 （本機或在中央網站） 網際網路電話語音服務提供者 (ITSP)。

</div>

<div>

## <a name="network-links-between-sites"></a>網站間的網路連結

您也必須考慮您預期的網路連結您的中央網站和其分支站台之間的頻寬使用量。 如果您有，或計劃部署，可恢復的 WAN 連結之間的網站，建議您部署的閘道，以提供使用者在這些網站上的本機直接向內撥號 (DID) 終止每個分支網站。 如果您有彈性的 WAN 連結，但 WAN 連結的頻寬可能受限，請為該連結設定通話許可控制。 如果您不具備可恢復的 WAN 連結，裝載少於 1000 位使用者在您的分支網站，而且不具有本機受過訓練的 Lync Server 系統管理員可以使用，我們建議您將部署 Survivable Branch Appliance 分支網站。 如果您主控 1000年到 5000 分支網站的使用者之間，缺少可恢復的 WAN 連線，並有經過訓練的 Lync Server 系統管理員可以使用，我們建議您部署 Survivable Branch Server 小型分支網站閘道。 如果您有支援媒體旁路的閘道對等，也請考慮對受限的連結啟用媒體旁路。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的進階 Enterprise Voice 功能的網路設定](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

