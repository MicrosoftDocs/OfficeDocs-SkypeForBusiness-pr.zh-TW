---
title: Lync Server 2013：還原 Lync Server 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4612fb48c2e526fa501ebc5f7342d7797ca47b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511600"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a>在 Lync Server 2013 中還原 Lync Server 集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

您的 Lync Server 部署可能包含下列任一類型的集區：

  - 前端伺服器

  - 中繼伺服器

  - 常設聊天室伺服器

  - Edge Server

如果整個集區經歷中斷，請針對集區中的每個成員伺服器執行下列程式。

  - 若為前端集區，請先還原後端伺服器，然後還原每一部前端伺服器。 如需詳細資訊，請參閱在 lync server [2013 中還原 Enterprise Edition 後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) 及 [還原 lync server 2013 中的 enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

  - 若是所有其他類型的集區，則請還原每個成員伺服器。 如需詳細資訊，請參閱 [在 Lync server 2013 中還原 Enterprise Edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

</div>

<span> </span>

</div>

</div>

</div>

