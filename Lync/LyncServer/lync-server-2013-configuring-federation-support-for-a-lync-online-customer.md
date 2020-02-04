---
title: Lync Server 2013：針對 Lync Online 客戶設定同盟支援
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
ms.openlocfilehash: 76582be324977d5466d234a37e4352806dd6d92f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="0e56a-102">在 Lync Server 2013 中設定 Lync Online 客戶的同盟支援</span><span class="sxs-lookup"><span data-stu-id="0e56a-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e56a-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0e56a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0e56a-104">您可以透過下列任何一種方式，為貴組織中的使用者提供通訊服務：</span><span class="sxs-lookup"><span data-stu-id="0e56a-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="0e56a-105">在您的組織中部署 Lync Server 2013 （稱為*內部部署服務*），並在您的組織中設定 lync 2013 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0e56a-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="0e56a-106">使用主機服務提供者設定 Microsoft Lync Online 2010 客戶帳戶，並設定擁有主機提供者的使用者帳戶（稱為*線上服務*）。</span><span class="sxs-lookup"><span data-stu-id="0e56a-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="0e56a-107">如果您在組織中部署 Lync 2013，您可以與一或多個 Microsoft Lync Online 2010 客戶的網域進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="0e56a-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="0e56a-108">若要在您的內部部署 Lync 2013 部署的使用者和 Lync Online 2010 客戶的使用者之間啟用同盟，您必須針對 Lync Online 客戶的網域和使用者設定支援。</span><span class="sxs-lookup"><span data-stu-id="0e56a-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e56a-109">本檔只說明設定貴組織與 Lync Online 2010 客戶支援同盟的程式。</span><span class="sxs-lookup"><span data-stu-id="0e56a-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="0e56a-110">本檔不說明將 Lync Online 2010 客戶設定為支援同盟的程式。</span><span class="sxs-lookup"><span data-stu-id="0e56a-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="0e56a-111">如需 Lync Online 服務的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>lync online。</span><span class="sxs-lookup"><span data-stu-id="0e56a-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e56a-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="0e56a-112">In This Section</span></span>

  - [<span data-ttu-id="0e56a-113">在 Lync Server 2013 中與 Lync Online 客戶進行聯盟的先決條件</span><span class="sxs-lookup"><span data-stu-id="0e56a-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="0e56a-114">在 Lync Server 2013 中設定 Lync Online 網域的同盟支援</span><span class="sxs-lookup"><span data-stu-id="0e56a-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="0e56a-115">在 Lync Server 2013 中設定與 Lync Online 客戶的同盟的使用者存取權</span><span class="sxs-lookup"><span data-stu-id="0e56a-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="0e56a-116">在 Lync Server 2013 中驗證與 Lync Online 客戶的通訊</span><span class="sxs-lookup"><span data-stu-id="0e56a-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

