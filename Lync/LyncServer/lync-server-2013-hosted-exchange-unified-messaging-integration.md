---
title: Lync Server 2013： 主控 Exchange Unified Messaging 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Unified Messaging integration
ms:assetid: f4de0165-da3b-499e-98fc-28ddd0db02d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413027(v=OCS.15)
ms:contentKeyID: 48185829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc06e8924aab2aee3ed03e8091c1373c8bd2da2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="6e09f-102">Lync Server 2013 中的主控的 Exchange Unified Messaging 整合</span><span class="sxs-lookup"><span data-stu-id="6e09f-102">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e09f-103">_**主題上次修改日期：** 2012年-09-20 個_</span><span class="sxs-lookup"><span data-stu-id="6e09f-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="6e09f-104">除了先前的 Lync Server 2013 版本的支援已提供*內部*部署的 Exchange 整合通訊 (UM)，與整合 Lync Server 2013 引進與*裝載*Exchange UM 整合的支援。</span><span class="sxs-lookup"><span data-stu-id="6e09f-104">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="6e09f-105">主控 Exchange UM 可讓 Lync Server 2013 提供語音訊息給使用者，如果您將部分或全部轉移到裝載的 Exchange 服務提供者，例如 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6e09f-105">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="6e09f-106">Lync Server 2013 Enterprise Voice 會使用 Exchange UM 基礎結構來提供來電接聽、 來電通知、 語音存取 （包括語音信箱） 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="6e09f-106">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="6e09f-107">如需詳細資訊，請參閱[整合的整合通訊與 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="6e09f-107">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e09f-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6e09f-108">In This Section</span></span>

  - [<span data-ttu-id="6e09f-109">主控 Exchange UM 架構和 Lync Server 2013 中的路由</span><span class="sxs-lookup"><span data-stu-id="6e09f-109">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="6e09f-110">Lync Server 2013 中的主控的語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="6e09f-110">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="6e09f-111">Lync Server 2013 中主控的 Exchange 使用者管理</span><span class="sxs-lookup"><span data-stu-id="6e09f-111">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="6e09f-112">Lync Server 2013 中的託管的 Exchange 連絡人物件管理</span><span class="sxs-lookup"><span data-stu-id="6e09f-112">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="6e09f-113">部署程序的整合主控 Exchange UM 與 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e09f-113">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

