---
title: Lync Server 2013： 周邊網路 VoIP 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93962357e276d8d4eb69813386bd845cad5acb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="449e6-102">Lync Server 2013 的周邊網路 VoIP 元件</span><span class="sxs-lookup"><span data-stu-id="449e6-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="449e6-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="449e6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="449e6-104">外部來電者使用整合的通訊用戶端進行個別或會議通話自信地仰賴 Edge Server 與同事的語音通訊。</span><span class="sxs-lookup"><span data-stu-id="449e6-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="449e6-105">在 Edge Server 中，[Access Edge service 提供 SIP 訊號的呼叫從您的組織防火牆外的 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="449e6-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="449e6-106">A/V Edge Service 可以讓媒體周遊 NAT 和防火牆。</span><span class="sxs-lookup"><span data-stu-id="449e6-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="449e6-107">從公司防火牆外使用整合通訊 (UC) 用戶端的來電者，會依賴 A/V Edge Service 來進行個別通話和電話會議。</span><span class="sxs-lookup"><span data-stu-id="449e6-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="449e6-p102">A/V 驗證服務會和 A/V Edge Service 配置在一起，並為後者提供驗證服務。嘗試連接至 A/V Edge Service 的外部使用者，需要 A/V 驗證服務提供的驗證 Token 才能接通電話。</span><span class="sxs-lookup"><span data-stu-id="449e6-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

