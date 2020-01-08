---
title: Lync Server 2013：啟用 Kerberos 驗證的先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="2a21b-102">在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件</span><span class="sxs-lookup"><span data-stu-id="2a21b-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a21b-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2a21b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2a21b-104">在啟用 Kerberos 驗證之前，請務必完成所有必要的設定和基礎結構準備：</span><span class="sxs-lookup"><span data-stu-id="2a21b-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="2a21b-105">Active Directory 架構已針對 Lync Server 2013 進行延伸。</span><span class="sxs-lookup"><span data-stu-id="2a21b-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="2a21b-106">Lync Server 2013 的 Active Directory 林準備已完成。</span><span class="sxs-lookup"><span data-stu-id="2a21b-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="2a21b-107">Lync Server 2013 的 Active Directory 網域準備已完成。</span><span class="sxs-lookup"><span data-stu-id="2a21b-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="2a21b-108">中央管理儲存區已成功安裝且可供使用。</span><span class="sxs-lookup"><span data-stu-id="2a21b-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="2a21b-109">已使用拓撲建立器建立併發布拓撲。</span><span class="sxs-lookup"><span data-stu-id="2a21b-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="2a21b-110">已定義並部署需要 Web 服務的伺服器和角色，包括前端伺服器、標準版伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="2a21b-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="2a21b-111">Internet Information Services （IIS）已使用建議的角色服務進行設定和部署，以支援 Lync Server 2013 中的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="2a21b-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="2a21b-112">在符合先決條件之後，您應該準備好建立一個或多個帳戶供 Web 服務使用，以用於您的部署的 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="2a21b-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="2a21b-113">至少，您必須為每個部署建立一個 Kerberos 驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a21b-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="2a21b-114">不過，您可以為每個網站建立一個帳戶，在網站上提供本機 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="2a21b-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="2a21b-115">您只能針對每個網站指定一個 Kerberos 驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="2a21b-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

