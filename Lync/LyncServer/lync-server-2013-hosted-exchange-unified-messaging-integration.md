---
title: Lync Server 2013：主控 Exchange 整合通訊整合
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
ms.openlocfilehash: 44a66f82e9eefd9c4b68e753635abc90aea0ad5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533100"
---
# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="d40f6-102">Lync Server 2013 中的主控 Exchange 整合通訊整合</span><span class="sxs-lookup"><span data-stu-id="d40f6-102">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d40f6-103">_**主題上次修改日期：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="d40f6-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="d40f6-104">除了先前的 Lync Server 2013 發行的支援，與 Exchange 整合通訊 (UM) 的 *內部* 部署整合之外，Lync Server 2013 也會提供支援與 *主控* Exchange UM 的整合。</span><span class="sxs-lookup"><span data-stu-id="d40f6-104">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="d40f6-105">主控 Exchange UM 可讓 Lync Server 2013 為使用者提供語音訊息給您的使用者，如果您將部分或所有郵件轉移到主控 Exchange 服務供應商（如 Microsoft Exchange Online）。</span><span class="sxs-lookup"><span data-stu-id="d40f6-105">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="d40f6-106">Lync Server 2013 Enterprise Voice 使用 Exchange UM 基礎結構提供通話回應、來電通知、語音存取 (包括語音信箱) 和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="d40f6-106">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="d40f6-107">如需詳細資訊，請參閱 [整合整合通訊和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="d40f6-107">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d40f6-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d40f6-108">In This Section</span></span>

  - [<span data-ttu-id="d40f6-109">Lync Server 2013 中的主控 Exchange UM 架構和路由</span><span class="sxs-lookup"><span data-stu-id="d40f6-109">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="d40f6-110">Lync Server 2013 中的主控語音信箱原則</span><span class="sxs-lookup"><span data-stu-id="d40f6-110">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="d40f6-111">Lync Server 2013 中的主控 Exchange 使用者管理</span><span class="sxs-lookup"><span data-stu-id="d40f6-111">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="d40f6-112">Lync Server 2013 中的主控 Exchange 連絡人物件管理</span><span class="sxs-lookup"><span data-stu-id="d40f6-112">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="d40f6-113">整合主控 Exchange UM 與 Lync Server 2013 的部署程式</span><span class="sxs-lookup"><span data-stu-id="d40f6-113">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

