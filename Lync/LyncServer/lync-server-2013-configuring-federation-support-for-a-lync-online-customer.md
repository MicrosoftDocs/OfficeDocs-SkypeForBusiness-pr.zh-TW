---
title: Lync Server 2013：設定 Lync Online 客戶的同盟支援
description: Lync Server 2013：為 Lync Online 客戶設定同盟支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b5e7995e686a9492b3a4be98a92b848716cacf9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548419"
---
# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="92249-103">在 Lync Server 2013 中為 Lync Online 客戶設定同盟支援</span><span class="sxs-lookup"><span data-stu-id="92249-103">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92249-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="92249-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="92249-105">您可以利用下列任何方式，為組織中的使用者提供通訊服務：</span><span class="sxs-lookup"><span data-stu-id="92249-105">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="92249-106">在您的組織中部署 Lync Server 2013 (稱為 *內部部署服務*) 並設定組織中的 lync 2013 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="92249-106">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="92249-107">設定具有裝載提供者的 Microsoft Lync Online 2010 客戶帳戶，並設定具有裝載提供者 (稱為 *線上服務*) 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="92249-107">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="92249-108">如果您在組織中部署 Lync 2013，您可以與一或多個 Microsoft Lync Online 2010 客戶的網域同盟。</span><span class="sxs-lookup"><span data-stu-id="92249-108">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="92249-109">若要在您的內部部署 Lync 2013 部署和 Lync Online 2010 客戶的使用者之間啟用同盟，您必須設定對網域和 Lync Online 客戶之使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="92249-109">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92249-110">本檔只會說明設定組織以支援與 Lync Online 2010 客戶同盟的程式。</span><span class="sxs-lookup"><span data-stu-id="92249-110">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="92249-111">本檔不會說明設定 Lync Online 2010 客戶以支援同盟的程式。</span><span class="sxs-lookup"><span data-stu-id="92249-111">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="92249-112">如需 Lync Online 服務的詳細資訊，請參閱 Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A> 。</span><span class="sxs-lookup"><span data-stu-id="92249-112">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92249-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="92249-113">In This Section</span></span>

  - [<span data-ttu-id="92249-114">在 Lync Server 2013 中與 Lync Online 客戶進行同盟的必要條件</span><span class="sxs-lookup"><span data-stu-id="92249-114">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="92249-115">在 Lync Server 2013 中設定 Lync Online 網域的同盟支援</span><span class="sxs-lookup"><span data-stu-id="92249-115">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="92249-116">在 Lync Server 2013 中設定與 Lync Online 客戶同盟的使用者存取權</span><span class="sxs-lookup"><span data-stu-id="92249-116">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="92249-117">在 Lync Server 2013 中驗證與 Lync Online 客戶的通訊</span><span class="sxs-lookup"><span data-stu-id="92249-117">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

