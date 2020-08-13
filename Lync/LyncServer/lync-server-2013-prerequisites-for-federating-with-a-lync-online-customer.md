---
title: Lync Server 2013：與 Lync Online 客戶進行同盟的必要條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa1dbaf69aecc7977737317cccc4c6ac6bb07d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="eebc9-102">在 Lync Server 2013 中與 Lync Online 客戶進行同盟的必要條件</span><span class="sxs-lookup"><span data-stu-id="eebc9-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eebc9-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="eebc9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="eebc9-104">若要與 Lync Online 2010 客戶同盟，您應該已在組織中完成 Lync Server 2013 的初始部署和設定。</span><span class="sxs-lookup"><span data-stu-id="eebc9-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="eebc9-105">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="eebc9-105">This includes the following:</span></span>

  - <span data-ttu-id="eebc9-106">在您的組織中部署至少一部 Standard Edition server 或單一 Enterprise Edition 前端集區。</span><span class="sxs-lookup"><span data-stu-id="eebc9-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="eebc9-107">如需部署內部伺服器的詳細資訊，請參閱部署檔中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="eebc9-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="eebc9-108">啟用 Lync Server 2013 的內部使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="eebc9-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="eebc9-109">如需詳細資訊，請參閱部署檔或作業檔中的[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="eebc9-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="eebc9-110">部署至少一部 Edge Server，以及支援外部使用者存取所需的其他元件。</span><span class="sxs-lookup"><span data-stu-id="eebc9-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="eebc9-111">如需詳細資訊，請參閱部署檔中的[管理 Lync Server 2013 的同盟與外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="eebc9-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="eebc9-112">在組織內啟用同盟支援，並設定適當的方法來控制同盟網域的存取。</span><span class="sxs-lookup"><span data-stu-id="eebc9-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="eebc9-113">如需詳細資訊，請參閱 Operations 檔中的在 lync server [2013 中啟用或停用遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)和[管理您組織2013的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="eebc9-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="eebc9-114">為組織中的使用者啟用外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="eebc9-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="eebc9-115">如需詳細資訊，請參閱在 Lync Server 2013 和部署檔或作業檔[中，將外部使用者存取原則指派給啟用 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。</span><span class="sxs-lookup"><span data-stu-id="eebc9-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

