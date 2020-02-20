---
title: Lync Server 2013： 設定 Lync Online 客戶同盟支援
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
ms.openlocfilehash: f25a2ba7735c8ccf135d2030e7853940ef545ac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="a1896-102">在 Lync Server 2013 中設定 Lync Online 客戶同盟支援</span><span class="sxs-lookup"><span data-stu-id="a1896-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1896-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1896-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1896-104">您可以提供通訊服務的使用者在組織中任何下列的方式：</span><span class="sxs-lookup"><span data-stu-id="a1896-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="a1896-105">部署 Lync Server 2013 中您的組織 （稱為*內部部署服務*） 和設定您的組織中的 Lync 2013 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1896-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="a1896-106">設定具有裝載提供者的 Microsoft Lync Online 2010 客戶帳戶，並設定具有裝載提供者 （又稱為*線上服務*） 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a1896-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="a1896-107">如果您在組織中部署 Lync 2013，您可與一或多個 Microsoft Lync Online 2010 客戶的網域之同盟。</span><span class="sxs-lookup"><span data-stu-id="a1896-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="a1896-108">若要啟用內部部署 Lync 2013 部署的使用者與使用者的 Lync Online 2010 customer 之間的同盟，您必須設定支援的網域和使用者的 Lync Online 客戶。</span><span class="sxs-lookup"><span data-stu-id="a1896-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1896-109">這份文件說明的設定來支援與 Lync Online 2010 customer 同盟組織的程序。</span><span class="sxs-lookup"><span data-stu-id="a1896-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="a1896-110">這份文件不會說明設定以支援同盟 Lync Online 2010 customer 程序。</span><span class="sxs-lookup"><span data-stu-id="a1896-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="a1896-111">如需有關 Lync Online 服務的詳細資訊，請參閱 Lync Online 在<A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>。</span><span class="sxs-lookup"><span data-stu-id="a1896-111">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1896-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a1896-112">In This Section</span></span>

  - [<span data-ttu-id="a1896-113">與 Lync Server 2013 中的 Lync Online 客戶同盟的先決條件</span><span class="sxs-lookup"><span data-stu-id="a1896-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="a1896-114">在 Lync Server 2013 中設定 Lync Online 網域同盟支援</span><span class="sxs-lookup"><span data-stu-id="a1896-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="a1896-115">使用 Lync Server 2013 中的 Lync Online 客戶設定同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="a1896-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="a1896-116">確認與 Lync Server 2013 中的 Lync Online 客戶的通訊</span><span class="sxs-lookup"><span data-stu-id="a1896-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

