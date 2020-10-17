---
title: Lync Server 2013：設定增強型9-1-1
description: Lync Server 2013：設定增強型9-1-1。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553329"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="dd9b7-103">在 Lync Server 2013 中設定增強型9-1-1</span><span class="sxs-lookup"><span data-stu-id="dd9b7-103">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd9b7-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="dd9b7-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="dd9b7-p101">增強型 9-1-1 (E9-1-1) 是緊急通知功能，會讓來電者的電話號碼與市街地址產生關聯。使用這項資訊，公共安全勤務中心 (PSAP) 可以立即派遣緊急服務人員到需要幫助的來電者所在處。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="dd9b7-107">若要支援 E9-1-1，Lync Server 2013 必須能夠正確地將位置與用戶端產生關聯，並確定此資訊是用來將緊急通話路由傳送至最近的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-107">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="dd9b7-108">如需規劃 E9-1-1 部署的詳細資訊，請參閱 [E9-1-1) In Lync Server 2013 中的 [規劃緊急 (服務](lync-server-2013-planning-for-emergency-services-e9-1-1.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-108">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dd9b7-109">Lync Server 2013 只支援美國境內的 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-109">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="dd9b7-110">若要部署 E9-1-1，您必須設定與合格的 E9-1-1 服務提供者的 SIP 連線，或者將緊急位置識別號碼 (ELIN) 閘道部署至以公用交換電話網路 (PSTN) 為基礎的 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-110">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="dd9b7-111">如需詳細資訊，請參閱 <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">E9-1-1) 和轉送伺服器（Lync server 2013）中的增強 9-1-1 (</A>。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-111">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="dd9b7-112">如需設定主幹連線的詳細資訊，請參閱 <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">在 Lync Server 2013 中使用媒體旁路設定主幹</A>。</span><span class="sxs-lookup"><span data-stu-id="dd9b7-112">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd9b7-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="dd9b7-113">In This Section</span></span>

  - [<span data-ttu-id="dd9b7-114">在 Lync Server 2013 中設定 E9-1-1 語音路由</span><span class="sxs-lookup"><span data-stu-id="dd9b7-114">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="dd9b7-115">在 Lync Server 2013 中建立位置原則</span><span class="sxs-lookup"><span data-stu-id="dd9b7-115">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="dd9b7-116">在 Lync Server 2013 中設定 E9-1-1 的網站資訊</span><span class="sxs-lookup"><span data-stu-id="dd9b7-116">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="dd9b7-117">在 Lync Server 2013 中設定位置資料庫</span><span class="sxs-lookup"><span data-stu-id="dd9b7-117">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="dd9b7-118">在 Lync Server 2013 中設定 advanced E9-1-1 功能</span><span class="sxs-lookup"><span data-stu-id="dd9b7-118">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

