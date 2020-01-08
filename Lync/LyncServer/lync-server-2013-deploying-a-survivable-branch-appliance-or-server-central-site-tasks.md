---
title: 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央網站工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央網站工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

在中央網站完成本節中的工作。 如果您要部署 Survivable 分支伺服器，請略過第一個工作。

<div>


> [!IMPORTANT]
> 在您執行本節中的工作之前，必須先進行下列條件： 
> <UL>
> <LI>
> <P>Lync Server 必須在中央網站上設定。</P>
> <LI>
> <P>分支網站上的安裝技術人員必須新增至 [RTCUniversalSBATechnicians] 群組。</P></LI></UL>此外，我們建議您執行下列動作：
> <UL>
> <LI>
> <P>在每個分支網站上部署 DHCP 伺服器，以讓用戶端取得 IP 位址。</P>
> <LI>
> <P>若要在每個分支網站上部署 DHCP 伺服器的替代方案，請使用 Lync Server Management Shell Cmdlet <STRONG>CsRegistrarConfiguration-EnableDHCPServer $true</STRONG>，在 Survivable 分支裝置或 Survivable 分支伺服器上啟用 LYNC server DHCP。 如需詳細資訊，請參閱規劃檔中<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支網站復原需求</A>的「硬體和軟體需求」一節。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中將 Survivable Branch Appliance 新增到 Active Directory](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [在 Lync Server 2013 中新增分支網站至拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [在 Lync Server 2013 中定義 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

