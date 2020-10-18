---
title: 前端伺服器、立即訊息及顯示狀態的技術需求
description: 前端伺服器、立即訊息及顯示狀態的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Front End Servers, instant messaging, and presence
ms:assetid: 1e2c093a-614a-4b60-8c0c-98f97e859fcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398269(v=OCS.15)
ms:contentKeyID: 48183575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eeeb638a43a9bb09c1015c010b9cb857d9944a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577109"
---
# <a name="technical-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="d80eb-103">Lync Server 2013 的前端伺服器、立即訊息及顯示狀態的技術需求</span><span class="sxs-lookup"><span data-stu-id="d80eb-103">Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d80eb-104">_**主題上次修改日期：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="d80eb-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="d80eb-105">立即訊息 (IM) 和目前狀態，永遠都是在 Enterprise Edition 前端集區和 Standard Edition server 上執行。</span><span class="sxs-lookup"><span data-stu-id="d80eb-105">Instant messaging (IM) and presence always run on Enterprise Edition Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="d80eb-106">如需支援的硬體、作業系統和資料庫軟體詳細資訊，請參閱以下：</span><span class="sxs-lookup"><span data-stu-id="d80eb-106">For information on supported hardware, operating systems, and database software, see the following:</span></span>

  - [<span data-ttu-id="d80eb-107">Lync Server 2013 的支援硬體</span><span class="sxs-lookup"><span data-stu-id="d80eb-107">Supported hardware for Lync Server 2013</span></span>](lync-server-2013-supported-hardware.md)

  - [<span data-ttu-id="d80eb-108">Lync Server 2013 中的伺服器軟體和基礎結構支援</span><span class="sxs-lookup"><span data-stu-id="d80eb-108">Server software and infrastructure support in Lync Server 2013</span></span>](lync-server-2013-server-software-and-infrastructure-support.md)

<div>

## <a name="supported-collocation"></a><span data-ttu-id="d80eb-109">支援的組合</span><span class="sxs-lookup"><span data-stu-id="d80eb-109">Supported Collocation</span></span>

<span data-ttu-id="d80eb-p102">前端伺服器角色可以和中繼伺服器組合在一起。您也可以在前端伺服器上執行監控和封存。不過，前端伺服器不能與 Edge Server 或 Director 組合。</span><span class="sxs-lookup"><span data-stu-id="d80eb-p102">The Front End Server role can be collocated with Mediation Server. You can also run Monitoring and Archiving on Front End Servers. Front End Server cannot be collocated with Edge Server or Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

