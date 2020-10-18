---
title: Lync Server 2013：啟用 Kerberos 驗證的必要條件
description: Lync Server 2013：啟用 Kerberos 驗證的必要條件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579919"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="a6dd6-103">在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件</span><span class="sxs-lookup"><span data-stu-id="a6dd6-103">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6dd6-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a6dd6-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a6dd6-105">在啟用 Kerberos 驗證之前，請確定您已完成所有必要的設定和基礎結構準備工作：</span><span class="sxs-lookup"><span data-stu-id="a6dd6-105">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="a6dd6-106">已擴充 Lync Server 2013 的 Active Directory 架構。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-106">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="a6dd6-107">已完成 Lync Server 2013 的 Active Directory 樹系準備。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-107">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="a6dd6-108">已完成 Lync Server 2013 的 Active Directory 網域準備工作。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-108">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="a6dd6-109">已成功安裝中央管理存放區及可供使用。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-109">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="a6dd6-110">已使用拓撲產生器建立及發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-110">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="a6dd6-111">已定義及部署需要 Web 服務的伺服器和角色，包括前端伺服器、Standard Edition 伺服器及 Director。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-111">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="a6dd6-112">Internet Information Services (IIS) 會以建議的角色服務設定及部署，以支援 Lync Server 2013 中的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-112">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="a6dd6-113">符合先決條件後，您應該準備好建立一或多個帳戶，以供部署的 Kerberos 驗證使用之 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-113">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="a6dd6-114">每個部署應至少建立一個 Kerberos 驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-114">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="a6dd6-115">不過，您可以為每個網站各建立一個帳戶，以在該網站提供本機 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-115">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="a6dd6-116">每個網站只能指定一個 Kerberos 驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="a6dd6-116">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

