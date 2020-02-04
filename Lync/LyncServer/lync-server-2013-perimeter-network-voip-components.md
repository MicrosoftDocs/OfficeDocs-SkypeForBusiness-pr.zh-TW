---
title: Lync Server 2013：周邊網路 VoIP 元件
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
ms.openlocfilehash: cb8e14228bb927f857aa5e9801f579653eb35fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="0bffa-102">Lync Server 2013 的周邊網路 VoIP 元件</span><span class="sxs-lookup"><span data-stu-id="0bffa-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bffa-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0bffa-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0bffa-104">在個別或會議呼叫中使用整合通訊用戶端的外部呼叫者，依靠邊緣伺服器與同事進行語音通訊。</span><span class="sxs-lookup"><span data-stu-id="0bffa-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="0bffa-105">在邊緣伺服器上，Access Edge 服務提供來自您組織防火牆以外的 Lync 使用者呼叫的 SIP 信號。</span><span class="sxs-lookup"><span data-stu-id="0bffa-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="0bffa-106">A/V 邊緣服務可讓您能夠遍歷 NAT 和防火牆。</span><span class="sxs-lookup"><span data-stu-id="0bffa-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="0bffa-107">使用來自企業防火牆外部之整合通訊（UC）用戶端的來電者，都依賴于個人和電話會議的 A/V 邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="0bffa-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="0bffa-108">A/V 驗證服務已 collocated，並為 A/V 邊緣服務提供驗證服務。</span><span class="sxs-lookup"><span data-stu-id="0bffa-108">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="0bffa-109">嘗試連線至 A/V 邊緣服務的外部使用者必須具備 A/V 驗證服務所提供的驗證權杖，才能進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bffa-109">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

