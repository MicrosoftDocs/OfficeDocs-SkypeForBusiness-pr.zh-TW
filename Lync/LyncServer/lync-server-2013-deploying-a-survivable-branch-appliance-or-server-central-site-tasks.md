---
title: 部署 Survivable 分支裝置或伺服器中心網站工作
description: 部署 Survivable 分支裝置或伺服器中心網站工作。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4460ea215d6fc80ee89f1ca9bc42f08ac5d14617
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558599"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>使用 Lync Server 2013 部署 Survivable 分支裝置或伺服器-中央網站任務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

在中央網站完成本節中的工作。 如果您要部署 Survivable 分支伺服器，請略過第一個任務。

<div>


> [!IMPORTANT]
> 在您執行本節中的工作時，必須符合下列條件： 
> <UL>
> <LI>
> <P>必須在中央網站設定 Lync Server。</P>
> <LI>
> <P>必須將分支網站的安裝技術人員加入至 RTCUniversalSBATechnicians 群組。</P></LI></UL>此外，我們建議您執行下列作業：
> <UL>
> <LI>
> <P>在每個分支網站部署 DHCP 伺服器，讓用戶端能夠取得 IP 位址。</P>
> <LI>
> <P>在每個分支網站上部署 DHCP 伺服器的替代方法，請使用 Lync Server Management Shell Cmdlet <STRONG>Set-get-csregistrarconfiguration –EnableDHCPServer $true</STRONG>，在 Survivable branch 裝置或 Survivable branch server 上啟用 LYNC server DHCP。 如需詳細資訊，請參閱規劃檔中的「適用于 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支網站恢復需求</A> 」一節中的「硬體和軟體需求」一節。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [將 Survivable 分支裝置新增至 Active Directory 中的 Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [將分支網站新增至您在 Lync Server 2013 中的拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [在 Lync Server 2013 中定義 Survivable 分支裝置或伺服器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

