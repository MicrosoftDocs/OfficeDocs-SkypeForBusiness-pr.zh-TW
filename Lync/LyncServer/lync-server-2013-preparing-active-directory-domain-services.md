---
title: Lync Server 2013：準備 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e1d7285d743da2270121389bbb5a510fe3b12d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="ffb28-102">為 Lync Server 2013 準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="ffb28-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffb28-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ffb28-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ffb28-104">在您部署並操作 Lync Server 2013 之前，您必須先延伸架構，然後建立及設定物件，以準備 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="ffb28-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="ffb28-105">架構延伸會新增 Lync Server 所需的 Active Directory 類別和屬性。</span><span class="sxs-lookup"><span data-stu-id="ffb28-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="ffb28-106">本節中的主題說明如何準備用來部署 Lync Server 的 AD DS，以及如何指派設定與組織單位（OU）許可權。</span><span class="sxs-lookup"><span data-stu-id="ffb28-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="ffb28-107">如需 Lync Server 所需架構變更的詳細資料，請參閱[Lync server 2013 使用的 Active Directory 架構擴充功能、類別及屬性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb28-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ffb28-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="ffb28-108">In This Section</span></span>

  - [<span data-ttu-id="ffb28-109">Lync Server 2013 的 Active Directory 基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="ffb28-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="ffb28-110">Lync Server 2013 中的 Active Directory 網域服務準備工作概觀</span><span class="sxs-lookup"><span data-stu-id="ffb28-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="ffb28-111">在 Lync Server 2013 中準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="ffb28-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="ffb28-112">在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="ffb28-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="ffb28-113">Lync Server 2013 中的授與權限</span><span class="sxs-lookup"><span data-stu-id="ffb28-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

