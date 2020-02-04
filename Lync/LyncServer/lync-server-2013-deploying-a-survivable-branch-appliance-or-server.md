---
title: Lync Server 2013：部署 Survivable Branch Appliance 或 Survivable Branch Server
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
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-10_

彈性企業語音指的是分支網站復原功能，也就是，在中央網站連結無法使用的情況下，提供連續的企業語音服務來分支網站使用者。

針對中小型及中型分支網站（有25至1000個使用者的分支網站），我們建議您部署 Survivable 分支裝置，這將會使用其內建 PSTN 閘道或 SIP 主幹來終止公用交換電話網絡（PSTN）通話服務提供者。 Survivable 分支裝置是協力廠商裝置，其中包含執行 Windows Server 2008 R2 作業系統、Lync Server 2013 註冊機構、中繼伺服器軟體和 PSTN 閘道的刀片伺服器，全都在單一裝置主機殼中。

針對1000至5000使用者且沒有彈性 WAN 的分支網站，我們建議將 Survivable 分支伺服器連線至 PSTN 閘道或 SIP 幹線至電話服務提供者。 Survivable 分支伺服器是 Windows Server 電腦，其中安裝了註冊機構和轉送伺服器軟體。

<div>


> [!NOTE]  
> 對於超過5000個使用者和專用 Lync Server 系統管理員的分支網站，我們建議使用完整的 Lync Server 2013 部署，並與中央網站不同。<BR>如需針對貴組織中的分支網站選擇最佳復原方案的詳細資料，包括先決條件及規劃考慮，請參閱規劃檔中<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支網站復原需求</A>。



</div>

<div>


> [!NOTE]  
> 駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央網站工作](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Server - 分支網站工作](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [在 Lync Server 2013 中為分支網站恢復設定使用者](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [在 Lync Server 2013 中將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Lync Server 2013 中的附錄：Survivable Branch Appliance 和 Survivable Branch Server](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

