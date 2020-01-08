---
title: Lync Server 2013：主控 Exchange 整合通訊整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Unified Messaging integration
ms:assetid: f4de0165-da3b-499e-98fc-28ddd0db02d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413027(v=OCS.15)
ms:contentKeyID: 48185829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a743e79434a521f0bba43e9ad4103625e9720844
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="0b1ff-102">Lync Server 2013 中的主控 Exchange 整合通訊整合</span><span class="sxs-lookup"><span data-stu-id="0b1ff-102">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b1ff-103">_**主題上次修改日期：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="0b1ff-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="0b1ff-104">除了支援先前的 Lync Server 2013 發行已提供以與 Exchange 整合訊息（UM）的*內部*部署部署之外，Lync server 2013 也提供與*託管*Exchange UM 整合的支援。</span><span class="sxs-lookup"><span data-stu-id="0b1ff-104">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="0b1ff-105">如果您將部分或全部傳送到託管的 Exchange 服務供應商（例如 Microsoft Exchange Online），則在託管 Exchange UM 可讓 Lync Server 2013 提供語音訊息給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="0b1ff-105">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="0b1ff-106">Lync Server 2013 企業語音使用 Exchange UM 基礎結構，以提供通話應答、通話通知、語音存取（包括語音信箱）及自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="0b1ff-106">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="0b1ff-107">如需詳細資訊，請參閱整合式整合[訊息和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1ff-107">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0b1ff-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="0b1ff-108">In This Section</span></span>

  - [<span data-ttu-id="0b1ff-109">Lync Server 2013 中的主控 Exchange UM 架構和路由</span><span class="sxs-lookup"><span data-stu-id="0b1ff-109">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="0b1ff-110">Lync Server 2013 中的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="0b1ff-110">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="0b1ff-111">Lync Server 2013 中的主控 Exchange 使用者管理</span><span class="sxs-lookup"><span data-stu-id="0b1ff-111">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="0b1ff-112">Lync Server 2013 中的主控 Exchange 聯絡人物件管理</span><span class="sxs-lookup"><span data-stu-id="0b1ff-112">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="0b1ff-113">整合主控 Exchange UM 和 Lync Server 2013 的部署程序</span><span class="sxs-lookup"><span data-stu-id="0b1ff-113">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

