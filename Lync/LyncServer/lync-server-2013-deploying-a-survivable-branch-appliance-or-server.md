---
title: Lync Server 2013：部署 Survivable 分支裝置或伺服器
description: Lync Server 2013：部署 Survivable 分支裝置或伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558589"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-10_

復原的 Enterprise Voice 是指分支網站恢復功能，也就是在中央網站的連結無法使用的情況下，提供連續的 Enterprise Voice 服務給分支網站使用者的能力。

對於小型和中型分支網站 (具有25到1000使用者的分支網站) ，我們建議您部署 Survivable 分支裝置，它會使用內建的 PSTN 閘道或 SIP 主幹給電話服務提供者，來終止公用交換電話網路 (PSTN) 呼叫。 Survivable Branch 裝置是協力廠商裝置，包括執行 Windows Server 2008 R2 作業系統的刀片式伺服器、Lync Server 2013 登錄機、轉送伺服器軟體，以及 PSTN 閘道，全部在單一裝置底盤中。

針對具有1000至5000使用者的分支網站，且沒有任何彈性的 WAN，我們建議將 Survivable 分支伺服器連線至電話服務提供者的 PSTN 閘道或 SIP 主幹。 Survivable 分支伺服器是 Windows Server 電腦，其上已安裝註冊機構和轉送伺服器軟體。

<div>


> [!NOTE]  
> 對於具有超過5000個使用者和專用 Lync Server 系統管理員的分支網站，我們建議完整的 Lync Server 2013 部署，與中央網站的部署分開。<BR>如需針對組織中分支網站選擇最佳恢復解決方案的詳細資訊，包括必要條件和規劃考慮，請參閱規劃檔中的 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支網站恢復需求</A> 。



</div>

<div>


> [!NOTE]  
> 在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-中央網站任務](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-分支網站工作](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [在 Lync Server 2013 中為分支網站恢復設定使用者](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Lync Server 2013 的 Survivable 分支裝置或伺服器上的家庭使用者](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [附錄： Lync Server 2013 中的 Survivable 分支裝置和伺服器](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

